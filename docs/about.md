---
layout: page
title: About
permalink: /about/
---
Mingjie Li

## Education

- Ph.D. Computer Science and Technology, Tsinghua University, 2018–present[^advisor]
- B.Eng. Computer Science and Technology, Tsinghua University, 2014–2018[^head-teacher]

- The 2019 Summer School on Research in Computing Education, Trondheim, June 17-21 2019

## Publications

- **Mingjie Li**, Zeyan Li, Kanglin Yin, Xiaohui Nie, Wenchi Zhang, Kaixin Sui, and Dan Pei. Causal Inference-Based Root Cause Analysis for Online Service Systems with Intervention Recognition. In Proceedings of the 28th ACM SIGKDD Conference on Knowledge Discovery and Data Mining (KDD ’22), August 14–18, 2022, Washington, DC, USA. ACM, New York, NY, USA, 11 pages, doi: 10.1145/3534678.3539041
- **Mingjie Li**, Minghua Ma, Xiaohui Nie, Kanglin Yin, Li Cao, Xidao Wen, Zhiyun Yuan, Duogang Wu, Guoying Li, Wei Liu, Xin Yang, and Dan Pei. Mining Fluctuation Propagation Graph Among Time Series with Active Learning. In: Strauss, C., Cuzzocrea, A., Kotsis, G., Tjoa, A.M., Khalil, I. (eds) Database and Expert Systems Applications (DEXA 2022). Lecture Notes in Computer Science, vol 13426, Springer, Cham, 2022, doi: 10.1007/978-3-031-12423-5_17
- Zeyan Li, Nengwen Zhao, **Mingjie Li**, Xianglin Lu, Lixin Wang, Dongdong Chang, Xiaohui Nie, Li Cao, Wenchi Zhang, Kaixin Sui, Yanhua Wang, Xu Du, Guoqiang Duan, and Dan Pei. Actionable and Interpretable Fault Localization for Recurring Failures in Online Service Systems. In Proceedings of the 30th ACM Joint European Software Engineering Conference and Symposium on the Foundations of Software Engineering (ESEC/FSE '22), November 14-18, 2022, Singapore, Singapore. ACM, New York, NY, USA, 13 pages, doi: 10.1145/3540250.3549092
- Xianglin Lu, Zhe Xie, Zeyan Li, **Mingjie Li**, Xiaohui Nie, Nengwen Zhao, Qingyang Yu, Shenglin Zhang, Kaixin Sui, Lin Zhu, and Dan Pei. Generic and Robust Performance Diagnosis via Causal Inference for OLTP Database Systems. 2022 22nd IEEE International Symposium on Cluster, Cloud and Internet Computing (CCGrid), 2022, 655-664, doi: 10.1109/CCGrid54584.2022.00075
- Qingyang Yu, Xiaoying Bai, **Mingjie Li**, Qiyuan Li, Tao Liu, Zeyin Liu, and Dan Pei. Performance Modeling and Anomaly Location of Large Microservice Systems Based on Trace Control Flow Analysis. Ruan Jian Xue Bao/Journal of Software, 2022, 33(5): 1849–1864 (in Chinese), doi: 10.13328/j.cnki.jos.006209
- Xiaoying Bai, Dan Pei, **Mingjie Li**, and Shanshan Li. The DevOps Lab Platform for Managing Diversified Projects in Educating Agile Software Engineering. 2018 IEEE Frontiers in Education Conference (FIE), San Jose, CA, USA, 2018, pp. 1-5, doi: 10.1109/FIE.2018.8658817.
- Xiaoying Bai, **Mingjie Li**, Dan Pei, Shanshan Li, and Deming Ye. Continuous delivery of personalized assessment and feedback in agile software engineering projects. In Proceedings of the 40th International Conference on Software Engineering: Software Engineering Education and Training (ICSE-SEET '18). Association for Computing Machinery, New York, NY, USA, 2018, 58–67. doi: 10.1145/3183377.3183387
- Xiaoying Bai, Shanshan Li, **Mingjie Li**, and Deming Ye. Exploration on software engineering practial teaching based on agile development. Experimental Technology and Management, 2018, 35(4): 6-11. doi: 10.16791/j.cnki.sjg.2018.04.002

## Unpublished Works

I spent plenty of time on the works below.
However, they are not ready to be published.

- Mingjie Li, Xiaoying Bai, Minghua Ma, and Dan Pei. DockerMock: Pre-Build Detection of Dockerfile Faults through Mocking Instruction Execution. 2021. [arXiv:2104.05490](https://arxiv.org/abs/2104.05490)
- Survey on The Software Engineering Course. 2020. [along with this site](/assets/report/2020软件工程课程情况调查.pdf)
- Survey on The Project of Software Engineering Course. 2019. [along with this site](/assets/report/2019软件工程作业情况调查.pdf)

## Experience

### Teaching Assitant of Software Engineering. 2016–present

The routine of the Software Engineering course is described in the paper published in ICSE-SEET 2018.
Following are some special works.

#### 2020

Conducted a survey.

Recreated an Android example project for GitLab CI.

#### 2019

Conducted a survey and interviews.

Created example projects for GitLab CI and CD in our platform.
Following are the covered frameworks
- Django
- Express
- Flask
- Golang
- React.js
- Spring Boot (created since 2018)

#### 2018

Leading another team of 4, applied GitLab CI instead of Jenkins and used Kubernetes to deploy services and Kafka to record running logs.
@gjz010 did the most in this version.

#### 2017

Leading a team of 4, used [Jenkins](https://www.jenkins.io) and Docker to enable a Continuous Integration process.

#### 2016

Deming Ye and I set up a platform to support the team project, integrating [GitLab](https://about.gitlab.com), [Codeface](https://github.com/siemens/codeface), and [SonarQube](https://www.sonarqube.org).
Implemented a module to count and analyze students’ development process, which is later included in the paper published in ICSE-SEET 2018.

### Organizer of AIOps Challenge 2020

The [AIOps Challenge 2020](http://iops.ai/competition_detail/?competition_id=15&flag=1) aims at fault localization for micros services. 
Competitors are required to locate the root cause metrics with the help of trace data and topology of Dockers and virtual machines. 

I developed the following tools, as well as discussion and solving various problems.

- A [judger](https://github.com/NetManAIOps/aiops2020-judge) to evaluate the competitors' answers.
- A [syncer](https://gitee.com/limjcst/mysql-sync) to copy data from the database in the private cloud to that in the public cloud.
- A [piper](https://gitee.com/limjcst/log-pipe) to play the monitor data from the database into the Kafka, pretending to be "real time".

[^advisor]: Xiaoying Bai was my advisor. However, she had her job transferred in 2019. Dan Pei is my advisor since 2020.
[^head-teacher]: Shanshan Li was my head teacher.
