---
title: Accelerate Innovation & Maximize Business Value with Serverless Apps [SRV212]
tags:
    - serverless
    - session
    - customer story
---
{{< youtube XUkhubMFVZI >}}

pluses
* streamlined devops, codepipeline
* supports a lot of languages
* tag direct costs to projects

considerations:
* know what specialties are
* certain languages not supported
* need to deal with cold starts, concurrent read/writes, etc.
* migration from non-aws requires focus and commitment

* kinesis firehose to watch for inbound connections faster than humans could do, and then try to shut down (ex. using "i am not a robot")
    * the serverless firehose can take that logging stream, analyze, and store it
    * example used was bots trying to auth
    * another example was comcast logins from a partner that had a retry bug (like hbo login using comcast)
        * blowing up traffic w/requests, serverless prevented other services from having performance hits

* comcast primetime tv has huge scale issues (like firing off recordings, people turning it on, etc.)
* comcast netflix had huge requirements for logins/auth, so they had to make a VPC that could handle those requests,
as well as could talk to the on prem systems

