Coinbase SRE talk
* SRE and DevOps
    * actually work nicely together

### Key Insights
    1. measure and improve human, organizational and machine systems
        * measure everything always
    2. SRE is a move from reactive to proactive event mgmt
        * eliminate toil and eliminate them
            * toil = manual operational work that doesn't scale
    3. Provide organizational back pressure mechanism
        * delay features to clean up tech debt
        * don't deploy new code until the app is more reliable
        * push back to teams/the org
        * feedback loop

How to convert ppl
* set early expectations
    * have to get C-level buy in
    * takes time

Coinbase
* how do we improve reliability if we don't know where we're reliable today
* installed service-level instrumentation
* used "Four Golden Signals" to determine where to start that instrumentation initiative
    * latency
        * direct impact on customer experience
        * where and how you measure it is important
            * load balancer? server-side? client-side for round trip?
    * traffic
        * transactions per second
        * direct relationship with business value
        * most companies/services have a threshold above which we don't know what happens
    * errors
        * typically expressed as a ratio, errors/time
            * helps set a nice target for improvement
        * easily digestible
        * another direct impact on customer experience
        * goal is not to eliminate errors, but find an acceptable error rate
    * saturation
        * how close are you to total available
        * how much DU and memory usage
        * its an issue everywhere at all time

* Golden Signals can apply to human organizations, like teams
    * burnout <- saturation
    * good SRE should be able to track this as well
    * blockers <- latency
    * how many tickets in a sprint <- traffic
    * humans error <- errors

* start somewhere, a best guess, and iterate from there
    * a spreadsheet
        * column for services, then one for each golden signal, and what that service uses for that signal
    * define "done"
        * ex. per-service dashboard in datadog for timeseries chart for each indicator
        * document describing the different indicators and why they are important
    * a spec document is important
        * helps guide implementation
        * where do you want to instrument? client/load balancer/etc.
        * why indicator matters
        * what it tells you
        * where you're going with it
        * having this documentation embedded in the tool is critical so it stays up to date
    * once we have some of these things defined, then we can define SLIs/promises
        * plain-language statements, easy to parse, easy to understand
        * plenty of potential stateholders <- bring them onboard at this point
        * we do all this so we can keep promises, with customers, etc.

* more on promises
    * Thinking in Promises by Mark Burgess
    * promises have two parties
    * promises can be human/machine, machine/machine, etc.
        * cross-functional team members can add more insight to different types of promises
    * example promises
        * your service promises to respond to client within 50ms
        * a service you depend on promises that its error rate will be < 1%
        * on-call promises they will engage an incident within 15 minutes
    * When are promises done?
        * promises are done when they have a monitor alert
        * forecasting - your tooling should be able to analyze and look historically to predict failures
            * ID stuff that runs the risk of breaking a promise and fix before it breaks promises
    * when promises are broken...
        * its inevitable, so plan for that inevitability
        * it builds trust

* blame-less post-mortems
    * let the data do the talking
    * requires 3 things
        1. good instrumentation
        2. good understanding of what you're measuring
        3. process for interpreting

* interpreting incidents
    * build a shared language
    * practice communication
    * understand that incidents and outages are broken promises
    * creates domain-specific language with no ambiguity, quickly

* measure incident response
    * quantify and measure the quality of ryour incident responses
    * quantitative: time to detect, time to engage, time to fix
    * qualitative: quality of communication
        * it is clear who to talk to
        * do we have all the stakeholders documented

* RECAP
    * why SRE?
        * why gets your buy in
    * get instrumentation started
        * spreadsheet, documents
    * promise enumeration
        * document clearly what our promises is
    * measure response when promises are broken
    * gains
        * transparancy
        *

