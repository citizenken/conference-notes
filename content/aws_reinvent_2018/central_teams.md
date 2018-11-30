---
title: "Role of Central Teams in DevOps Organizations [DEV70]"
tags:
    - session
    - devops
    - culture
---
{{< youtube xA1qPQg3WTc >}}

* small companies have small Teams

* as it grows, central teams develop (ex. tools, platfomrm, infra)

* becomes a "fractal" of central teams
    * different BUs have central teams that talk to a central time

* moving from traditional dev/ops/qa model to full end-end ownership

* with DevOps teams, why do we need central teams?

* most devops teams, while their work is different, they have the same software development lifecycle

* how many different implementations of monitoring/building tooling/etc. across a company?
    * His opinion: as few as possible

* Central teams create these common workflows and processes and abstract a lot of the process stuff away from devs

* no central team mandate at Netflix
    * no one has to use their tooling
    * challenge, but also a value, because they are providing the best-of-breed solution
        * rate of adoption becomes important metric
        * is our stuff being used? if not, lets find out whats going wrong

* what are you optimizing?
    * availability, velocity, efficiency
    * need to align with the other teams on these factors
    * ex. startups velocity is more important vs. bigger companies who care about availability

* leader or fast follower? central teams need to determine that
    * dangers of getting too far ahead or too far behind
    * to far ahead of teams? can lead to churn amongst internal customer, too many different solutions too fast
    * to far behind? customers will make their own solutions/shadow IT

* happy medium between leading/follower of treads amongst teams
    * work with pioneering teams to understand what their solution is early, evaluate scalability
    * once there is an inflection point, that other teams want to use the solution, that can be a good time to move to a central team

* Build or buy?
    * when do you build a bespoke solution instead of leveraging an existing one? This is their decision model:
        1. look at AWS, see if there is something
        2. look at other 3rd parties
        3. look at opensource. Even if it only statisfies like, 80% of use cases, might still be interesting, because you can contribute upstream
        4. roll it your own if there is really no other solution

two opensource stories:
1. spinnaker - popular, good community support, Google/AWS contribution
2. OSS - failed, didn't take off

* central team invests in educaion
    * onboarding so best practices and patterns are in from the start
    * continuous education to bring existing ppl onboard

* good discoverabily for tooling resources
    * if there isn't strong discoverabily, ppl won't use your solution

* how to continuously update your customers on what's new and improved?
    * figure out what kind of avenue is effective?
        * brown bag lunches
        * newsletters
        * road shows
        * onboarding sessions/continuous sessions
    * takes all types of communitation all the time

* generalized vs. specialized needs
    * too generalized leads to least-common-denominator
    * too specific and it can't be shared well
    * solution? try to find a happy medium, then
        * make their internal tooling to be extensible
        * inner opensource

* for a long time, they had no dedicated product management
    * start out as team doing customer feedback, requirement gathering, prioritizing
    * at some point, there is a scale/complexity that PMs are needed
        * now they are trying to create a PM roll
        * not only does what they did before, but can take on more and be more focused

* finding the right engagement model
    * working directly with teams creates a customer -> provider relationship
    * working with distributed central teams makes them more partners than customers
        * they have a closer understanding to what their teams need, can help manage the general/specialized issue

* driving change
    * finding the key updates/migrations and prioritizing/pushing that
    * adoption curve
        * early, fast, no problem
        * medium once it is more mature
        * not done until that tail is done
            * current just works
            * has to decide what is good for a couple lagging teams vs. the company

* align central teams
    * many central teams
        * security, systems, data, etc.
    * have to align central teams before approaching customers prevents tons of "tiny" requests slowing things done

* "Highly aligned, loosely coupled"

* Fragmentation:
    * teams developing a solution that already exists causes fragmentation
        * accidental:
            * issue with developer awareness/outreach/discoverability
        * deliberate:
            * harder to address
            * team know a solution exists, but rejects it
            * important signal to determine shortcoming
            * could be an awareness issue
            * could be a real gap

* celebrate adoption
    * adoption is a key metric
    * when the metric is met/good, need to recognize that
* soft metrics are valuable
    * hard metrics can sometimes prevent you from seeing the forest through the trees
    * ex. customer happiness

QA
* guardrails and how that works with central teams
    * different concept than gatekeeprs
    * surface potential issues as suggestions and "are you sure you want to do that"
        * ex. spinniker from making large changes during busiest times. Are you sure?

* how do you keep teams' trust and not becoming ticket hubs?
    * constant engagement, documentation
    * ask for feedback, get an idea of what teams need, and then circle back when you address that need

* authority that enforces mandate for ?
    * sometimes, specifically in the security domain, the central teams force something
    * responsiblity that developers make good, sound decisions?
        * not using something thats java cause youre a ruby guy is not a good solution

* how do you resolve conflict?
    * tough, but still works on escalating to managers

* in early stage of devops transformation, when do you allow teams to have more freedom?
    * if the teams can handle the responsibility and trust of owning their own stuff, then they can make their own decisions apart from the central team

* what is the feedback mechanism
    * feedback isn't going to be coming in voluntarily
    * frequently reach out to teams to get feedback
        * surveys have gotten good responses in the last few years

* size of central teams as it relates to the size of the engineering teams
    * try to think of it as leverage, leverage being the ratio of value of the product vs. cost of the product
        * if they grow at the same rate, then they maintain leverage, but not providing more value
        * if they grow faster, then they lose leverage, harder to justify their grown because the ROI is impacted
        * best is slightly under the same rate, because they'll provide more value with fewer resources

* no goverance, no chargebacks
    * only have one product

* one trick for newsletters
    * distill updates as small as possible
        * the most impactful, relevant changes
    * 3-page newletters with every change gets thrown out

* do you embbed central team members in other teams?
    * central team members go work in app teams for 6/9 months, get real customer hands-on experience
    * at the same time, they bring the central team knowledge to the app team, closing gaps and awareness
    * forms stronger bonds, which helps with conflict resolution

* when to decide to scale the central team?
    * combination of the signal/happiness of customers
    * analyzing portfolio, and figure out what gaps
    * try to run lean, not making stuff that doesn't have a need
    * up to each team manager w/that decision

* w/lack of adoption, does the central team throw out their solution and supports the one that takes off?
    * no prescribed answer
    * centralize the product
    * work with the teams to decide if they want it centralized or not

* how to handle central team priorities? how do you balance the need between new tech and what customers want?
    * its a balance
    * try to be situationally aware and understand the landscape
    * understand the primary business needs
    * understand the tech trends
    * understand immediate customer needs
    * really good product managers come in here to make the hard choices
        * being deliberate and communicating it to the rest of the company

* centralized security team
    * have to work closely, because they often use the platform team to push out security changes


Ruslan Meshenberg
@rusmeshenberg








