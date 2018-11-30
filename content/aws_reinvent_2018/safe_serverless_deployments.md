---
title: "Best Practices for Safe Deployments on AWS Lambda and Amazon API Gateway [SRV343]"
---

* flexible schema much easier to deal with when using serverless
    * don't need to deal with updates
* lambda@the edge is like lamdba, but at the edge of your network, so it can do smarter routing to resources for ex.
    * for ex. feature flags to give beta version to a particular company
* when you update a lambda, it creates an immutable version ID
    * Aliases can be defined and linked to version IDs
    * Allows for ex. evens to go to particular versions
    * allows for weight between versions
        * ex. prod points 95% of invocations @ v1, 5% @ v2, for canary testing
        * invocations are distributed in a round-robin fashion
    * in SAM, can configure deployment strategy to funtions
        * allows automated weight manipulation
        * if no errors, keep ramping up (10 percent, increasing every 10 minutes for ex.)
        * requires monitoring
            * hooks and alarms (Cloudwatch alarm)
            * suggests to link canary metrics to customer action rather than just infrastructure
            * pre and post traffic functions that calls back to code deploy to accept/reject version

* similar weights can be added to API gateway to send traffic to certain API

Life stages of Lambda development

V1:
* User manually configures the function in the UI
    * doesn't allow multiple users
    * not saved outside of the UI
V2:
* Something in git changes, that updates the lambda
V3:
* Similar to V2, but has multiple environments, with testing before prod
V4:
* similar to V3, but the testing portion is build out into canary deployments
* pre traffic hooks can fail deployments, so customers don't see any errors
* once the canaries are happy, 100% of traffic is on the new version

Why would we move to serverless when things are working currently
* serverless is easy to create a sandbox environment for external developer to play with
    * just define another SAM configuration
* more scalable because it's there automatically
* no idle capacity
* no server admin

* best practices
    * function duration
    * control your retries
    * know your limits
    * use versioning
    * amazon cloudwatch - insert logging statements!
    * protect your Lambda functions with IAM roles
        * even like allowing only access to certain fields in a dynamo table
    * plan for dependencies when setting timeout value
    * test test test - best way to turn functions is by testing


* evaluating the move to serverless is a good time to review current design and architecture
    * ie. why use postgres if most queries are just lookups

* serverless and databases
    * know your data
    * know the available cost model and match it to your needs
    * tests at scale
    * encryption
    * secure your flow - IAM roles
* lessons learned from journey to serverless
    * think microservices
    * canary deployments
    * cold start
        * not as much of a problem as ppl say
        * aws adjusts cold starts over life of the function, learns about it
        * review design if cold starts are impacting you, ie. function runs once a day
    * yes/no functions
        * keep functions simple
    * events source
    * distributed tracing
    * environmental variables
* include this kind of stuff ^ in your MVP

Why does Capital One use Go?
* Go's native concurrency is a boon for network applications that live and die on concurrency
* modern apps are designed to be cloud-native and to take advantage of loosely coupled cloud services









