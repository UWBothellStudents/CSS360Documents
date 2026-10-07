# Software Engineering Difficulties

## What Are We Solving?

In *The Mythical Man-Month, The Tar Pit*, Fred Brooks spends an entire chapter making one argument: **software is inherently hard.** <a href="#references"><sup>[1]</sup></a> Before we talk about tools, processes, or techniques, you need to understand *why* Software Engineering is hard. 

In his 1986 follow-up essay, "No Silver Bullet," Brooks sorts the difficulties of software engineering into two kinds: **essential** difficulties, inherent to the nature of software itself, and **accidental** difficulties, caused by the limitations of the tools and technology we use. His central argument is that accidental difficulties can be shrunk or solved by better technology, and by 1986 most of them already had been. <a href="#references"><sup>[4]</sup></a>

The difficulties Brooks describes are incomplete as it ignores the difficulties caused by the humans and organizations building the software. Better technology doesn't fix a team that can't make a decision. We're calling these **organizational difficulties**, and we treat them as a third, parallel category:

| Category | Root cause | Fixed by better tools? | Fixed by a better process? |
| ----- | ----- | ----- | ----- |
| **Essential** | The nature of software itself | No | No — Brooks argues these never fully go away |
| **Accidental** | The limitations of our current tools and technology | Yes, in principle | Sometimes |
| **Organizational** | The nature of humans working (together) on software | No | Largely, yes |

This distinction matters: essential difficulties get mitigated, never solved. Accidental difficulties get solved by tools & techniques. Organizational difficulties get solved by process, techniques, and leadership practice. We need to recognize which kind of problem we're facing before we can pick the right fix.

# Part 1: Essential Difficulties

### **1\. Complexity**

Software systems have more distinct interacting parts than almost anything else humans build, and that complexity grows non-linearly with size. Unlike a bridge, no two parts of a large program are quite alike, and there's little repetition to exploit for simplification. <a href="#references"><sup>[4]</sup></a>

* **1.1 *Complexity makes software hard to test.*** Complex software produces untestable code, unreliable tests, or just bad tests. Without good tests, regressions go undiscovered, features go unverified, and the whole system becomes fragile.  
* **1.2 *Complexity makes software hard to change safely.*** Fixing one bug can create several others ("whack-a-mole").   
* **1.3 *Complexity makes large systems hard to know.*** No single person can hold the whole system in their head. This leads to redundant or incompatible code being added because no one realizes a solution already exists.  
* **1.4 *Complexity makes correctness and security hard to reason about.*** As interacting parts grow, so does the number of execution paths through them, far outpacing anyone's ability to check each one by hand. A system can pass every test a team thinks to run and still hide an edge case or race condition that surfaces only later. Security compounds this: vulnerabilities rarely live in one place, but emerge from how several reasonable pieces interact.

### **2\. Conformity**

Conformity is about the fact that, at any given moment, software has to fit into a pile of pre-existing arbitrary stuff it had no say in designing: other systems' formats, legacy protocols, business rules, legal requirements, an org chart. These constraints aren't imposed by anything as clean as physics or logic, they're arbitrarily imposed by history and human institutions. A software engineer has to reconcile multiple systems that disagree for no principled reason. <a href="#references"><sup>[4]</sup></a>

* **2.1 *Conformity makes it hard to keep requirements logical and consistent.*** The requirements aren't illogical because they keep changing; they're illogical because they were never derived from any coherent underlying principle in the first place. They're an artifact of messy, poorly documented human institutions.  
* **2.2 *Conformity makes it hard to keep designs elegant and consistent.*** A system gets stitched together to satisfy several unrelated external constraints at once, each patch matching a different legacy system, business rule, or institutional quirk it had to conform to. None of the patches agree with each other stylistically.  
* **2.3 *Conformity makes it hard to implement systems cleanly.*** Instead, conformity makes us "put lipstick on a pig." Some legacy systems or arbitrary constraints can't be replaced, so a team spends effort disguising the mismatch instead of fixing it. Nothing about the constraint improves; it's just made presentable enough to ship around.

### **3\. Changeability**

Software is expected to change constantly because it's "soft" (unlike a building or a bridge)  and cheap to change (relative to hardware). It absorbs the changing requirements everyone else refuses to deal with. Changeability is about the fact that, over time, the ground keeps moving, and software is expected to move with it, repeatedly, indefinitely, at a pace no other engineered artifact tolerates. Whatever requirements you land on today will be different, again, before you know it. <a href="#references"><sup>[4]</sup></a>

* **3.1 *Changeability makes it hard to invest in user-facing work.*** Dependencies, platforms, and frameworks keep moving whether or not the product's own requirements do, so a team has to spend cycles just keeping pace with an environment that refuses to hold still. None of that work is optional, and none of it ships anything a user would notice or want; it's the cost of standing still relative to everything moving around you.     
* **3.2** ***Changeability makes systems hard to keep stable.*** This is about a single structure destabilizing as changes accumulate on top of each other over time: each new patch stacked on the last increases the odds that touching anything topples the whole structure. It's like a Jenga Tower of instability.

### **4\. Invisibility**

Software has no inherent geometric or spatial representation. You can't walk around it or see it the way you can a building. This makes communication, review, and reasoning about it much harder. <a href="#references"><sup>[4]</sup></a>

* **4.1 *Invisibility makes it hard to communicate mental models*.** Because there's no shared physical artifact to point to, each team member builds their own internal picture of how the system works. Without something concrete to check those pictures against, they silently drift apart, producing systems where each person's piece "works" against their own mental model but fails to cohere with everyone else's, a failure that's often invisible until integration.  
* **4.2 *Invisibility makes it hard to recognize good software*.** You can't visually inspect software the way you can inspect a building's craftsmanship. What counts as "good code" varies by team, domain, and context, and is genuinely disputed even among experienced engineers. <a href="#references"><sup>[11]</sup></a>

# Part 2: Accidental Difficulties

Brooks's essential/accidental distinction isn't "complexity vs. no complexity." The distinction is about where the complexity comes from.

**Essential** difficulty is inherent in the problem domain itself. No amount of good design or practices remove the qualities from software that make it difficult.

**Accidental** difficulty is complexity we introduce ourselves, through our tools, habits, and choices while building the solution. None of the following are inherent to a problem: duplicated logic, tangled dependencies, leaky abstractions, a deployment that only works on one engineer's laptop. Those difficulties are a byproduct of how we built it.

Accidental difficulties aren't caused by the nature of software, and they're not caused by the humans building it. They're caused by the limitations of the tools and technology available at a given moment. As Brooks argues, these can be shrunk or eliminated by better technology. This course spends real time on the tools that save us time by reducing friction.

We can summarize Brooks's point this way: *the hardest problems in software engineering are problems of understanding requirements, managing complexity, dealing with change, coordinating people, and designing correct conceptual models — and better tools don't remove those.* Brooks names four essential difficulties that produce this hardness: **Complexity**, **Conformity**, **Changeability**, and **Invisibility**. <a href="#references"><sup>[4]</sup></a>

But that doesn't mean tools are beside the point. It means tools earn their place by attacking a different layer of the problem: the friction of actually doing the mechanical work of writing, tracking, sharing, running, and deploying code. Each difficulty below is, in some sense, the "accidental cousin" of one of Brooks's essential difficulties. They illustrate the same underlying hardness, but showing up as a mechanical annoyance rather than a conceptual one. Every tool covered in this course exists because someone got tired of hitting one of these.

## Incorrect Syntax and Buggy Code

*Accidental cousin of: Complexity*

Software is essentially complex: a real system has more interacting parts than any one person can hold in their head at once. That complexity doesn't go away just because you have a good editor. But without integrated tooling, that essential complexity gets compounded by completely avoidable friction: no syntax checking as you type, no autocomplete, no fast way to search or refactor across a large codebase, no integrated debugger. Mistakes that a tool could catch instantly are instead caught late, sometimes not until production. Debugging is hard enough when you understand the system; it's brutal when the bug is intermittent, or when, as in the days before automatic memory management, a program slowly leaks memory until it crashes hours later for no obvious reason.

## Tracking Changes and Collaboration

*Accidental cousin of: Invisibility*

Brooks points out that software has no physical shape: you can't walk around it or point a camera at it the way you can a bridge or a building. That's the essential problem. The accidental problem is that teams often lack even a basic tool to make the history and current state of the work visible to one another, whether on one machine or across a distributed team. Without version control, a team can't safely track a project's history, revert a bad change, or see who changed what and why, and working on the same codebase at the same time means overwriting each other's work, historically "solved" with ad hoc methods like mailing patches or copying files to a shared drive, none of which scale past a couple of people. Local history alone isn't enough for a distributed team, though. Without a shared, remote place to host code, coordination happens informally, over email, over chat, or not at all, and each person's understanding of the codebase's current state quietly drifts from everyone else's, invisible until integration exposes the gap. <a href="#references"><sup>[13]</sup></a>

## Environment and Platform Differences

*Accidental cousin of: Conformity*

Code has to run somewhere, and historically that "somewhere" has been a moving target. Getting code to run consistently, whether on a teammate's machine, on a production server, or outside the narrow context it was originally designed for, has been a major source of friction for as long as software has existed. JavaScript is a good example: it was originally confined to the browser, and running it as a general-purpose, server-side language required real workarounds before that became a first-class option. <a href="#references"><sup>[15]</sup></a> "It works on my machine" is the accidental-difficulty problem in one sentence.

## Expensive, Inflexible Infrastructure

*Accidental cousin of: Changeability*

Software is essentially subject to constant pressure to change: new requirements, new scale, new users. Physical infrastructure has historically made that pressure painful to absorb, because provisioning, maintaining, and scaling physical servers is slow and capital-intensive. A team that suddenly needs more capacity has to buy and configure hardware in advance, guessing at future demand. A team whose demand shrinks is stuck paying for capacity it no longer needs. Either way, the business's need to change outpaces the infrastructure's ability to change with it. <a href="#references"><sup>[16]</sup></a>

## Dependency and Build Management

*Accidental cousin of: Complexity*

Almost no software is built entirely from scratch: every project pulls in other people's code, and that code pulls in more code, and so on. That web of dependencies is a textbook case of accidental complexity: nothing about your problem requires you to resolve a conflict between two libraries that each want a different version of a third library, yet that exact scenario, sometimes called dependency hell, has eaten more engineering hours than almost any other single category of busywork. <a href="#references"><sup>[18]</sup></a> Before modern tooling, this was handled by manually downloading files and hoping nothing broke. Reproducing a colleague's exact working setup could take an entire afternoon. The `left-pad` incident is a particularly vivid example of how a tiny transitive dependency can disrupt thousands of projects. <a href="#references"><sup>[19]</sup></a>

## Deployment and Release Automation

*Accidental cousin of: Changeability*

Writing code that works is only half the job; it also has to reach users. Before automated pipelines, shipping code was a manual, high-stakes ritual: someone copies files to a server by hand, restarts a process, and hopes nothing breaks, with no automated test gate to catch a problem before it reaches real users and no easy way to roll back if it does. That manual ritual is precisely where an essential need (software must be able to change quickly and safely) collides with the accidental difficulty of not having a repeatable way to ship that change. <a href="#references"><sup>[20]</sup></a>

## Observability in Production

*Accidental cousin of: Invisibility*

If Invisibility describes software having no physical shape, observability is where that problem gets most painful: once code is deployed and running, what is it actually doing? Without logging, monitoring, tracing, and alerting, a team's only way to find out is to wait for a user to complain, or to get paged at 2 a.m. with no idea where to even start looking. This is a different flavor of invisibility than the debugging problem covered above. That one is about understanding code while you're writing it. This one is about understanding a live system under real, unpredictable load, often across many machines at once. <a href="#references"><sup>[21]</sup></a>

## Defending Against a Hostile Environment

*Accidental cousin of: Conformity*

Software has to conform to a hostile external environment it didn't design: attackers, compliance requirements, and the reality that any code you didn't write yourself might have a vulnerability inside it. That same external environment increasingly holds software accountable for the personal data it collects, stores, and shares, whether or not the team building it ever stopped to ask if it should. Historically this conformity was handled manually and inconsistently. Secrets like API keys and passwords were hardcoded directly into source files, dependencies were never checked against known vulnerabilities, and if security reviews happened, they came right before a release rather than continuously throughout development. Privacy fared no better: user data was often collected by default, logged in plaintext, retained indefinitely, and shared with third parties without any consistent review of whether that access was necessary or even intended. <a href="#references"><sup>[22]</sup></a>

## Boilerplate and Repetitive Coding

*Accidental cousin of: Complexity*

A significant share of programming time doesn't go into design or problem-solving at all: it goes into mechanical, repetitive scaffolding, like writing the same setup code for the tenth time, looking up syntax or API signatures you've used before but forgotten, and writing routine tests that follow a predictable pattern. None of this is the essential difficulty of software; it doesn't come from the problem being solved, it comes from the mechanics of expressing a solution in code. That makes it exactly the kind of difficulty tools are good at removing: unlike complexity or changeability, boilerplate is genuinely fair game for automation. Studies of GitHub Copilot provide evidence that AI assistance can reduce the time required for some programming tasks. <a href="#references"><sup>[17, 23]</sup></a>

# Part 3: Organizational Difficulties

These show up once you add schedules, teams, and organizations to the essential and accidental difficulties above. But underneath both of the difficulties in this section sits something even more basic: people. We humans make mistakes, communicate poorly, learn slowly, forget, have egos, experience stress, have emotions, and don't always get along with other humans. Call these **Inherent Human Traits**. These are no more optional than complexity is optional in a problem domain. No process, methodology, or tool eliminates them; the best any organization can do is manage the friction they produce. That friction shows up in two recognizable forms: individuals misjudging things on their own, and groups of individuals colliding with each other.

## 5\. The Estimation Trap

Organizations consistently misjudge how long software takes to build, and how much it truly costs. We fall into this trap at all stages: at the start of a project, when trying to recover a project that's already behind, and over the full life of the system. <a href="#references"><sup>[8]</sup></a>

* **5.1 *Poor estimates*.** Initial estimates are systematically optimistic. Engineers tend to estimate as if everything will go right, and first-order estimates often account only for coding time while ignoring the rest of the work (integration, testing, documentation, meetings). Once given, estimates calcify into commitments before anyone has enough information to reliably make them.  
* **5.2 *Late delivery*.** People procrastinate and a rushed, late-night delivery can be wrought with defects. When a project falls behind, the intuitive fix of throwing more people at it backfires. But it is imperative to remember Brooks's Law, "Adding people to a late project makes it later." <a href="#references"><sup>[2]</sup></a> Communication overhead scales combinatorially with team size, and new members need ramp-up time before they're net-productive, both of which are easy to hand-wave away under deadline pressure.  
* **5.3 *High maintenance costs*.** Most software costs are in maintenance, not creation. Beginners tend to think of "building" as the whole job, and estimates tend to reflect that same blind spot. In reality, most of a system's life (and most of its total cost) is spent being modified by people who didn't write it. And while patching buggy code is a real cost to be faced, most maintenance costs come from enhancing features. <a href="#references"><sup>[27 - Facts 41-42]</sup></a>  
* **5.4 *Requirements are discovered,*** *not specified*. Customers often don't know exactly what they want until they see something wrong. Translating tacit human knowledge into a formal spec is itself hard intellectual work: it is not just a translation step. <a href="#references"><sup>[4]</sup></a>

## 6\. Decision-Making

Software is built inside human organizations, and how decisions get made, communicated, and challenged is often as consequential to the outcome as the technical decisions themselves.

* **6.1 *Lack of alignment and poor communication*.** How a decision is made or communicated can produce discontent, noncompliance, or even malfeasance. When authority is unclear or unaccepted, individuals may "go rogue," creating tension between individual autonomy and team alignment.  
* **6.2 *No decision-making process*.** A team that cannot converge on a decision it actually supports ends up in continued debate, analysis paralysis, or divided effort. No decision can be a worse outcome than a mediocre decision made and committed too quickly.  
* **6.3 *Disconnect between business drivers and engineering reality*.** Leadership often discounts or defers hard technical trade-offs in favor of business priorities, treating engineering concerns as negotiable rather than as constraints. The result is a gap between what the organization believes about its system and what's actually true of it, one that stays invisible until it surfaces as a missed deadline, an outage, or a decision made on bad information.  
* **_6.4 Schedule pressures lead to disaster_**. Deadlines set for organizational or political reasons rather than engineering reality are a common and consequential example of software engineering breaking down. This leads to corner-cutting, burnout, and often worse outcomes than an adjusted, realistic schedule would have produced. <a href="#references"><sup>[6, 7]</sup></a>

## 7\. Ambient Culture 

Culture is the accumulated, ambient pattern of how people treat each other on a team, day after day, independent of any single decision. A team can nail every estimate and it can still be a miserable, unsustainable place to work if the culture is toxic. The below are corrosive cultures that lead to disengagement, low quality, and attrition. 

* **7.1 *Lack of Accountability****.* In a *blame culture* <a href="#references"><sup>[24]</sup></a> the team searches for a person to blame instead of a cause to fix. Blame culture encourages people to hide mistakes, hedge their estimates, and to neglect or delay reporting problems when they're still cheap to fix. Some organizations have structures and cultures that diffuse accountability across multiple teams and systems such that there is no one responsible. <a href="#references"><sup>[25]</sup></a> There is a common understanding, "everyone's problem is no one's problem." These cultures punish honesty or let ownership evaporate into the crowd.  
* ***7.2 Lack of Motivation**.* A culture that recognizes individual heroics over team outcomes teaches people to optimize for visible, creditable, single-author wins: the late-night save, the clever rewrite, the flashy feature. Gone to the wayside is the unglamorous work of maintainability, mentoring, and making other people's work easier. Poor incentive structures produce undesirable behavior: people decline to share credit, take credit for others' work, or withhold help/information from teammates because a colleague's success is treated as a personal loss.  
* ***7.3 Lack of Trust**.* A culture of low trust treats people as instruments to be monitored rather than peers to be relied on. Micromanagement signals a default assumption of distrust, which pushes people toward covering themselves rather than doing good work. Developers often have the clearest view of technical reality, but raising an unwelcome truth to leadership carries real career risk, so warnings go unspoken or get softened past the point of usefulness. Appearances of an uneven assignment to interesting projects, promotions, or visibility lead people to distrust leadership's judgment. An absence of fair meritocracy can lead to assertions of favoritism, racism, and other forms of discrimination. And a team that isn't inclusive quietly narrows itself, losing perspectives before they're ever voiced. <a href="#references"><sup>[26]</sup></a>

<a id="references"></a>
# References

1. Brooks, F. P. [Chapter 1. "The Tar Pit."](https://learning.oreilly.com/library/view/mythical-man-month-the/0201835959/ch01.xhtml) *The Mythical Man-Month: Essays on Software Engineering*, Anniversary Edition.  
2. Brooks, F. P. [Chapter 2. "The Mythical Man-Month."](https://learning.oreilly.com/library/view/mythical-man-month-the/0201835959/ch02.xhtml) *The Mythical Man-Month: Essays on Software Engineering*, Anniversary Edition.  
3. Brooks, F. P. [Chapter 4. "Aristocracy, Democracy, and System Design."](https://learning.oreilly.com/library/view/mythical-man-month-the/0201835959/ch04.xhtml) *The Mythical Man-Month: Essays on Software Engineering*, Anniversary Edition.  
4. Brooks, F. P. [Chapter 16. "No Silver Bullet—Essence and Accident in Software Engineering."](https://learning.oreilly.com/library/view/mythical-man-month-the/0201835959/ch16.xhtml) *The Mythical Man-Month: Essays on Software Engineering*, Anniversary Edition. (*Or see this shorter [summary](https://blog.acolyer.org/2016/09/06/no-silver-bullet-essence-and-accident-in-software-engineering/).*)  
5. Brooks, F. P. [Chapter 17. "No Silver Bullet" Refined.](https://learning.oreilly.com/library/view/mythical-man-month-the/0201835959/ch17.xhtml) *The Mythical Man-Month: Essays on Software Engineering*, Anniversary Edition.  
6. I.M. Wright. [*Right on schedule – I.M. Wright’s “Hard Code”*](https://imwrightshardcode.com/2009/09/right-on-schedule/)  
7. I.M. Wright. [Marching to death – I.M. Wright’s “Hard Code”](https://imwrightshardcode.com/2004/12/marching-to-death/)  
8. I.M. Wright. [I would estimate – I.M. Wright’s “Hard Code”](https://imwrightshardcode.com/2008/09/i-would-estimate/)  
9. The Blog: [Revisiting The Facts and Fallacies of Software Engineering](https://blog.codinghorror.com/revisiting-the-facts-and-fallacies-of-software-engineering/)  
10. The Book: [Facts and Fallacies of Software Engineering](https://learning.oreilly.com/library/view/facts-and-fallacies/0321117425/)  
11. [*"The 11 Aspects of Good Code"*](https://www.pathsensitive.com/2023/07/the-11-aspects-of-good-code.html)  
12. [*5 Reasons Why You Should Continuously Update Your Product*](https://nextbigideaclub.com/magazine/ericries-5-reasons-continuously-update-product/5110/)  
13. [*Celebrating 20 Years of Git: 20 Interesting Facts From its Creator | Tower Blog*](https://www.git-tower.com/blog/git-turns-20)  
14. [*What is a kanban board? | Atlassian*](https://www.atlassian.com/agile/kanban/boards)  
15. [*What is Node.js? JavaScript on the Server Explained \- DEV Community*](https://dev.to/satyasootar/what-is-nodejs-javascript-on-the-server-explained-3i1c)  
16. [*The NIST Definition of Cloud Computing | NIST*](https://www.nist.gov/publications/nist-definition-cloud-computing)  
17. [*Peng et al., "The Impact of AI on Developer Productivity: Evidence from GitHub Copilot"*](https://arxiv.org/pdf/2302.06590) *(Feb 2023, which is nearly outdated already given how fast AI has progressed)*  
18. [*Dependency hell \- Wikipedia*](https://en.wikipedia.org/wiki/Dependency_hell)  
19. [*How one developer just broke Node, Babel and thousands of projects in 11 lines of JavaScript — The Register*](https://www.theregister.com/2016/03/23/npm_left_pad_chaos)  
20. [*Continuous Integration — Martin Fowler*](https://martinfowler.com/articles/continuousIntegration.html)  
21. [*Chapter 6: Monitoring Distributed Systems — Google Site Reliability Engineering*](https://sre.google/sre-book/monitoring-distributed-systems/)  
22. [*OWASP Top Ten Web Application Security Risks — OWASP Foundation*](https://owasp.org/www-project-top-ten/)  
23. [*Research: Quantifying GitHub Copilot's Impact on Developer Productivity and Happiness — The GitHub Blog*](https://github.blog/news-insights/research/research-quantifying-github-copilots-impact-on-developer-productivity-and-happiness/)  
24. [*Google SRE \- Blameless Postmortem for System Resilience*](https://sre.google/sre-book/postmortem-culture/)  
25. [*Diffusion of responsibility \- Wikipedia*](https://en.wikipedia.org/wiki/Diffusion_of_responsibility)  
26. [*Building Trust Within Your Team: The Cornerstone of High-Performance Leadership*](https://www.strategypeopleculture.com/blog/why-is-trust-important-in-leadership/)  
27. [*Facts and Fallacies of Software Engineering*](https://learning.oreilly.com/library/view/facts-and-fallacies/0321117425/bk01-toc.html)
