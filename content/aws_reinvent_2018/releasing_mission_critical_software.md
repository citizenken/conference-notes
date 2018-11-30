# How Amazon releases Mission-critical Software
* executes thousands of deploys at any give second
* 99.996% of deploys execute without problems
* always pushing to 100%

* much of what enables Amazon do do ^ is in our tooling

### Tech and cultural landscape at Amazon
* two pizza teams
* 8 engineers is still the average size at Amazon
    * communication cost is expensive
* end to end ownership
* Amazon is a "federation of startups"
    * given a domain, most decisions are the teams
    * teams pick tech stack, ratio of roles, own service end to end
* Amazon's service oriented architecture
    * services have public contract
    * only way other services talk to you
    * allows for constant refactoring behind the contract
* Local dev environment is the wild west
    * Agile-ish
    * "The Process" the release/debug process/etc. will ensure you don't cut corners
    * iterate as quickly as you can
    * your host is a service
        * local service running is easy
        * local dev can interact with other services out in the different environments that you have
* With all these services, mangement is tough
    * tolling helps organize all of that
    * focus on foundational tools, the building blocks first
        * ex. S3, EC2, then more complex serices on top
    * internal marketplace
        * share tooling/practices/solutions
        * wait for the best of the ^ ideas to bubble to the top
        * the best are then devloped on top of and "funded," resources are allocated

* their pipelines are aggressively pessimistic
    * to prevent changes from getting stuck in the process, ie. integration stuff lasting around
    * being harsh on changes makes sure that only the best
* Git in Amazon
    * Called Gitfarm
        * replication for free
        * finetuned access control, file by file, etc.
        * code search on commit
        * CodeCommit has many of those features




### Tooling philosophy
### Code review, build and the pre-mortem
* rules on top of commits to mainline based
    * rules like compliance as early as possible
    * certain files require certain reviewers

* build process
    * global dependency closure
        * parent POMs?
        * ex. 1 version of Spring for the whole company
        * hyper aware of who is using what
            * ex. if a dependency is compromised, easy to remove that version
    * unit testing
    * static analysis
* the pre-mortem
    * "correction of errors"
        * document all the bad ways the software could cause problems
            * what is the worst thing that could happen
            * how do we mitigate it
            * how do we fix it
    * don't do this process all the time
    * large changes
    * sensitive code areas
### Pipelining and deployment
* 3 envs
    * test env: wild west
    * integration: configured and looks like prod <- interesting
        * called public contracts for dependent services
        * prevents having a unique env
    * production
* rules around releasing w/regions and AZs to prevent widespread failures
* picture: columns are stages of the release pipeline, depth is the tests that are running
