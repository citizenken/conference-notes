---
title: Advanced Continuous Delivery Best Practices [DEV317]
tags:
    - CD
    - devops
    - codepipeline
    - session
---
{{< youtube Jnl29J3RJQ4 >}}

cd best practices
* VCS
* automated builds
* automated deployments
* deploy to > 1 instances (HA, spread load)
* unit tests
* integration tests (selenium, functional, syntentic users)
* deliver
* op
Tools in the talk - AWS specific
* monitoring - cloudwatch
* sns - notifications
* lambda
* aws codedeploy/codepipeline for delivery
* DEV309 - serverless + containers codedeploy/codepipeline

Add saftey to rolling deployments
* check health
* ensure minimum instances
* rollback

Canaries
* segment environment
* test
* use codepipeline wait for approval step
    * deploy to a segment
    * fire lambda that enters meta data into dashboard
    * triggers another lambda that monitors if enough usage has happened, time has passed, no errors have happened
    * send approval to the pipeline

