---
layout: post
title:  "资源分配与排队论"
date:   2021-05-09 11:00:00 +0800
categories: SEP math
---
<script type="text/javascript" src="/assets/js/mathjax-config.js"></script>
<script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.5/MathJax.js?config=TeX-AMS-MML_HTMLorMML"></script>

2018年，软件工程课程的教学平台基于 Kubernetes (K8s) 重新搭建，学生提交的代码会在 GitLab CI 中构建Docker镜像、测试、并部署到 K8s 上。
运行教学平台服务的容器、学生创建的容器、执行CI任务的容器分别运行在不同的服务器上。

CI 任务由 GitLab CI Runner 调度，共39支队伍使用了公共的 CI Runner。
CI 任务服务器的初始配置是 4核；
初始配置 Runner 的`concurrent`参数为50，使得允许的并发任务数量超过队伍（开发团队）数量。
在学生陆续配置好 CI 后，CI 任务量增加，且出现大量由系统原因引起的失败。
当通过 Runner 的`cpu_request`参数为每个 CI 任务分配一个核后，CI 任务由系统原因引起的失败大为减少。
另一方面，通过增加 CI 服务器可以提升并发处理能力、减少 CI 任务等待时间。

那么，**执行 CI 任务的服务器应该配置多少资源？**

排队论给出了一个解决思路。

假定 CI 任务的到达时间间隔服从参数为$\lambda$的指数分布，CI 任务的完成时间服从参数为$\mu$的指数分布；记允许的 CI 任务最大并发量为$K$。
使用 M/M/K 模型刻画 CI 任务的到达与完成情况，仅当$\rho = \frac{\lambda}{K \mu} < 1$时稳态存在，反之 CI 任务的等待队列会不断增长。
M/M/K 模型给出等待概率为$P_{Wait}$，即 CI Runner 接收到新的 CI 任务后无法立即执行、需要等待服务器资源的概率 ，其计算公式如下

$$A = \frac{\rho^{K} K^K}{K!} \frac{1}{1 - \rho}, B = \sum_{i = 0}^{K - 1} \frac{(K \rho)^i}{i!}, P_{Wait} = \frac{A}{A + B}$$

R 语言的计算代码如下
```R
wait.probability <- function(rho, K) {
  rho <- rho * K
  if (rho >= K) {
    1
  } else {
    A <- (rho ** K) / (K - rho) / factorial(K - 1)
    r <- 1 : (K - 1)
    B <- sum(rho ** r / factorial(r)) + 1
    A / (A + B)
  }
}
```

使用 CI 高峰期（检查作业前）的 CI 任务到达时间与完成时间进行估计，有

$$\lambda = 0.037,\mu = 0.0096$$

当$K=8$时，$P_{Wait} = 5\%$。
更多细节见[分析报告](/assets/report/2018-CI-Runner-性能分析.pdf)。

上述分析被用来指导后续课程 CI 任务服务器的资源配置。
利用泊松流的可加性，并假定每支队伍的 CI 任务是服从相同参数的泊松流，估计新学期的 CI 任务到达时间间隔服从参数为$\lambda^{\prime} = \frac{N}{39} \lambda$的指数分布，其中$N$为队伍数量。
继而选择使$P_{Wait} \le 5\%$的容量$K$作为 CI 任务服务器的 CPU 核数。

很难说这样的估计是否有效，但终究为决策提供了点依据。
