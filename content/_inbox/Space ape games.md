2023-11-21
Tags: #company #interview

![[cropped-space-ape-games_logo_vert_orange_w.webp]]

Games company
Based on Oxford street
Started in 2012
100+ employees
Partnered with Supercell from 2017

#### People:

![[Pasted image 20231121154419.jpg]]
**Joe Burridge** - Recruiter from November 2023

![[Pasted image 20231121154407.jpg]]
**Louis McCormack** - Head of Platform
Worked at Space Ape Games for almost 10 years, started as Lead DevOps Engineer
Education unknown

![[Pasted image 20231121154356.jpg]]
**Andy Sorrell** - Senior Programmer since 2012 (11 years and 6 months)
Based in Shenzen, Guangdong province
Formerly a project manager at Goldman Sachs
Briefly worked in Guildford and Borehamwood
University of Hertfordshire


#### Github:

https://github.com/spaceapegames

#### Games:

**Chrome Valley customs** -
4.5 Starts on Play Store
Released Jun 2023

Match three game framed around earning money to customise a car in a garage for different jobs, you need to make money for the old guy to require.

**Beatstar** -
Rhythm game with loot-box mechanics

- Fastlane
- Transformers Earth Wars
- Rival Kingdoms
- Samurai Siege

#### Articles:
[We Ditched our On-Call Rota](https://medium.com/spaceapetech/we-ditched-our-on-call-rota-fae4bf948f3)
Don't alert out of hours for tickets that can wait till morning e.g. high CPU alert
Focus on key metrics for players - Request Success Service Level Objective (SLO) and Concurrently Connected Users (CCU)
Stabilised Client and Server code
Company wide escalation procedure
Invest heavily in load testing prior to launch
Gaining experience

[Bursting To Lambda](https://medium.com/spaceapetech/when-autoscaling-just-isnt-enough-60666554b322)
Problems of scaling are largely resolved by Serverless compute
But, high-performance, latency sensitive workloads are not a good fit
There is a break even point where Lambda becomes more expensive than EC2
But what if we could *burst* to Lambda
Single container running on Fargate and Lambda, with an application load balancer that redirects to Lambda when the Fargate request limit is recieved



- https://medium.com/spaceapetech/jenkins-pipelines-25ebc1980600
- https://medium.com/spaceapetech/custom-aws-config-rules-20d7995561a8
- https://medium.com/spaceapetech/attaining-maximum-performance-with-automated-tests-b758fb9bdce8
- https://medium.com/spaceapetech/serverless-for-devops-teams-39202dba2ce


#### Tech I know they use
Redis - message broker
Wavefront
DynamoDB - noSql for AWS
Fargate
Lambda
Maven
Containers - Docker, K8s
protobuf


#### Known interview questions
What is a struct
What was your development process




---
# References

https://spaceapegames.com/