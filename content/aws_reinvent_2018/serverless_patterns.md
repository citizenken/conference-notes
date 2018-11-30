Severless patterns notes:
* traits of serverless:
    1. no server or container mgmt
    2. flexible scaling (horizontal is taken care of)
    3. HA, in all AZs
    4. dont pay for idle

* lambda execution
    1. dl code
    2. state new container
    3. bootstrap the runtime (java/ruby/python, etc. environtment)
    4. run the code

    steps 1-3 are "cold start" so there is a delay, but subsequent requests use the warmed containers

* tuning function resource helps with costs and cold/warm uses
* increasing memory usage helps with costs
* store secrets in env vars, encrypted in KMS

Pattern 1:
* static files hosted on S3, cached by cloudfront
* api gateway as a backend, sitting in front of lambda, which sends data to a store (dynamodb)
* signing is cognito

* api gateway
    * edge optimiazed - sits at the end of the cloud,
        * validated json web tokens for auth
        * reform urls
        * implement securit headers
    * regional
        *
    * private
        * just available internally

* lambda@edge - edge-based processing
* cost can be broken down to the activity level (how much an order costs to process)

