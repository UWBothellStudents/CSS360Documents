# Part 2: Reading Reflections

## Summary
This section spans three different units:  
* SDLC: we finish the discussion on SDLCs by reviewing Kanban.  
* Using tools: VS Code, Git, and GitHub  
* Architecture and Design is started  

### Slide Decks
* 1.6 Kanban  
* 2.1 VS Code & Clone  
* 2.2 Vibing with Git  
* 2.3 Discord Bots  
* 3.1 Architecture  
* 3.2 Arch to Design  

### Reading
#### 1.6 Kanban
1. [Agile Project Management with Kanban | Eric Brechner | Talks at Google (](https://www.youtube.com/watch?v=CD0y-aU1sXo)[youtube.com](http://youtube.com)[)](https://www.youtube.com/watch?v=CD0y-aU1sXo)  Kanban Video (1 hour):   
2. [What is Kanban in Project Management?](https://www.atlassian.com/agile/kanban) 

#### 2.2 Vibing with Git

1. [Git — Practical Java](https://java.mrstride.com/Topics/git.html)   
2. [*Celebrating 20 Years of Git: 20 Interesting Facts From its Creator | Tower Blog*](https://www.git-tower.com/blog/git-turns-20) 


#### 3.2 Arch to Design

1. [Blessed Isolation \- Better Design](https://imwrightshardcode.com/2006/08/blessed-isolation-better-design/)  
2. [MMM Chapter 4\. Aristocracy, Democracy, and System Design](https://learning.oreilly.com/library/view/mythical-man-month-the/0201835959/ch04.xhtml)


## 1.6 Kanban

**What is Kanban?**

Kanban is a visual workflow management method that helps teams optimize and continuously improve how work is delivered. Teams visualize tasks, limit work in progress, and focus on maintaining a smooth flow of work through defined stages. Unlike approaches that rely on fixed cycles, Kanban supports continuous delivery and allows priorities to change as work progresses.

**What is a Kanban board?**

A Kanban board is a visual tool that shows work as it moves through different stages of a process. The board is typically organized into columns such as "To Do," "In Progress," and "Done," although teams can customize these stages to match their workflow. By displaying all active work in one place, the board helps teams track progress, manage capacity, and identify bottlenecks.

**What makes Kanban different from Scrum?**

Both Kanban and Scrum are Agile approaches, but Scrum organizes work into fixed-length sprints with defined roles and planned commitments. Kanban focuses on continuous flow, flexible prioritization, and limiting work in progress, allowing changes to be made at any time. Scrum often measures velocity, while Kanban emphasizes cycle time and improving workflow efficiency.

**What is the purpose of WIP limits?**

Work-in-progress (WIP) limits restrict the amount of work that can be in a particular stage at one time. Their purpose is to help teams stay focused, reduce context switching, prevent work from piling up, and keep tasks moving smoothly through the workflow. WIP limits also make bottlenecks more visible and encourage teams to finish existing work before starting new tasks.

**What is CI/DI?**  
CI/CD is a software development approach that helps teams deliver high quality software quickly and reliably through automation and continuous feedback. 

Continuous Integration (CI) is the practice of **frequently** merging code changes into a shared repository, where **automated** builds and tests verify that the new code works correctly and does not introduce defects. 

Continuous Delivery (CD) **extends** CI by **automatically** packaging and preparing software so it is always ready for release, while emphasizing repeatable processes, automation, version control, built-in quality, and continuous improvement. 

Together, CI/CD supports Agile, Kanban, and other SDLC approaches by reducing integration problems, speeding up feedback, improving collaboration, and enabling teams to deliver value to users more frequently and with greater confidence.

**More Notes**  
Kanban is a process originally designed by Taiichi Ohno in the 1940s at Toyota. It is a very simple planning system to control and manage work in its various phases of production.   
Diff from Scrum:

* There is no sprint in Kanban.   
* There is no kickoff meeting, or demo day.

Similarities to Scrum:

* While there is no Product Owner necessarily, there is a backlog that is prioritized by the project managers  
* There is a daily standup (not called a scrum meeting anymore)  
* Features can still be in the form of a User Story

Large Teams:

* A team that works on a single Kanban board should be ideally near 7\. The max is 10\.  
* Very large teams would simply have many sub-teams.

**Why does Brechner choose to assign a task to an unqualified dev when the qualified dev isn’t available?**

Brechner argues that assigning work only to the qualified developer creates a hard dependency that can weaken the team over time. Giving the task to another developer helps spread knowledge and build additional expertise within the team. This approach reduces the risk of having a single point of failure when a key team member is unavailable or leaves the project.

**What are the risks to his suggestion?**

An unqualified developer may make mistakes that slow progress or create additional problems that must be corrected later. The developer may also require significant assistance from the qualified expert, reducing that person's productivity. In some cases, the learning effort may initially cost more time than waiting for the expert to become available.

**What are the risks of not following it?**

If only the qualified developer works on a particular area, the team becomes dependent on a single person. This creates a single point of failure that can severely impact the project if that person is absent, transferred, or leaves the organization. Over time, the team becomes less resilient because critical knowledge is concentrated in one individual.

**Draw a Kanban board with “sub-lanes”.**

A Kanban board generally focuses on primary lanes to represent workflow stages. Sub-lanes show the status of work within each stage such as: *Active* (normal active state), *tracking dependency* (**better** than *blocked*), *done* (waiting to go into next primary lane, but the primary lane has reached its WIP limits).

**Can Kanban be used on large teams? How?**

Yes, Kanban can be used on large projects by dividing the work among multiple smaller teams that each manage their own Kanban board. Coordination between teams is needed when dependencies exist across parts of the system. Architecture, planning, and cross-team communication help connect the work of many teams into a larger product.

**Can Kanban be used in every "fundamental" phase of SDLC?**

Kanban can be applied to requirements, design, implementation, testing, deployment, and maintenance because it focuses on visualizing and managing workflow. Teams can create columns that match whatever phase of the SDLC they are performing. However, some very large or highly regulated projects may still benefit from additional planning and plan-driven practices, especially during extensive requirements gathering and system-level coordination.

**What is swarming?**

Swarming occurs when multiple team members temporarily focus on a bottleneck to help move work through a clogged part of the process. It is often triggered when a lane reaches its WIP limit and no more work can enter that stage. By working together to remove blockers and finish tasks, the team restores flow and prevents delays from spreading through the system.

Rough Draft Answers:

* It is "good" to assign a task to an unqualified dev because blocking until the qualified dev is available reinforces **a hard dependency** that could **cripple the team** in the future when the qualified dev leaves the team. Better to spread the skillset.   
  * One risk is that the unqualified dev makes things worse, and/or drains too much time from the qualified dev asking for help.  
  * If a team always designates work to the “qualified dev”, then the team develops a “single point of failure.” If that developer leaves for any length of time, that portion of the product is crippled\!  
      
* What are sublanes?   
  * First, consider Primary Lanes: Primary lanes vary, but could be: Backlog, Specify, Implement, Validate, (temporarily) Done  
* Sub-lanes are smaller lanes within a primary lane: 

  1\) active

  2\) Track (dependency tracking), 

  3\) done

* WIP limits prevent a bottleneck. Work In Progress. If a limit is hit, the team can “swarm” to flush out the work and then possibly adjust the WIP limits in other lanes to avoid future bottlenecks.  
  * In some teams, a Lane is reserved for specific people to work on it. For example, a Test Lane could be reserved for Testers.  
* Swarming is when others "come to the rescue" to unblock a lane that has reached its WIP limit.  
  * For example, Developers who don't traditionally test, work on tasks in the Test lane.


  
**Kanban Notes:**

* A loose process. No sprints. Continuous integration of work. Ship when appropriate. Commitments are made at a task level, not by milestone or sprint. Backlog is prioritized continuously. Estimate work by virtue of breaking tasks down into manageable chunks (1-2 days) of work. Document as necessary (to enable accurate breakdown of work). Note that a large system would need cross-team coordination.   
* Video: [Agile Project Management with Kanban | Eric Brechner | Talks at Google (youtube.com)](https://www.youtube.com/watch?v=CD0y-aU1sXo)  
* Start with a backlog, prioritize it.  
* Daily stand-up (but no other “meetings”)  
* Kanban Board: lanes of work, with the leftmost column being the backlog, then doing, then done.  
  * Customize columns, but are typically: backlog, specify/breakdown, implement, validate  
  * Each “lane” (or step) has 2 columns “active/done”  (These are sublanes. There could be 3 sublanes.)  
  * “Done” needs a definition. “Done rules”. (e.g. code review, unit test pass)  
  * WIP: Work in Progress limits. Only X many items in a lane. The board helps eliminate bottlenecks or areas of significant slowdown. (e.g. implementation is limited to the number of devs on the team). Each column gets a WIP limit to avoid overloading any one specific column; this helps establish a pace.  
* Prioritization on a physical board. Move the stickies (or magnetic cards).  
* Calculate a Velocity (how many tasks get to the done column in a week, but of course this means tasks are of the same size). The idea is that during the breakdown step, every task is broken down into tasks roughly of the same size. There are no story points. Instead it is Tasks per Day completed by the team.  
* Backlog updates as you go. No Sprint Planning.  
* If a dependency is missed, a lane gets an extra column called “Track.” The task that is awaiting the dependency is put into the Track column. A person is assigned the task and works to resolve it (creates a task that the same team does, pushes another team to complete, etc.)  
* No specific Roles (similar to Scrum). But, typical people fall into some roles. (Product Owner, scrum master, document, test, implement).  
* **Swarming**: When a lane clogs up (WIP limit reached), others on the team come help to unblock the lane.  
* For large scale: upper management divvies the work up to logical teams.  The answer was a bit hand-wavy. 

* Eric claims: to convert from Scrum to Kanban, just tell the team to add WIP limits. After a while, team will realize that Sprint Planning isn’t necessary, and other things aren’t necessary (demo, retrospective, etc.)  
* Eric claims that Kanban can scale to very large teams, afterall, they use Kanban on Windows. Does this mean Kanban is a good choice regardless of the product? Why or why not? (A: While Eric says, yes, there are reasons to believe that some products would be better using a Plan Driven process. For example, at the start of a large system-of-systems project where the requirements gathering is deep. Also, read his article, [Coordinated Agility](https://imwrightshardcode.com/2010/05/coordinated-agility/), where he discusses why planning is important, and where Agile is best applied–at the team level of \~10 people. However, as Brechner states [here](https://imwrightshardcode.com/2006/08/blessed-isolation-better-design/), Architecture bridges the gap between big products and small teams. ) 

## 2.2 Vibing with Git

Resources: 

* [Version Control Systems \- GeeksforGeeks](https://www.geeksforgeeks.org/git/version-control-systems/),   
* [https\://www\.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow)  
* [Celebrating 20 Years of Git: 20 Interesting Facts From its Creator | Tower Blog](https://www.git-tower.com/blog/git-turns-20)   
* [Git — Practical Java](https://java.mrstride.com/Topics/git.html) 

**What is the difference between Centralized and Distributed source control systems? Which one is git?**

In a Centralized Version Control System, all files and version history are stored on a single central server, and developers commit their changes directly to that server. In a Distributed Version Control System, each developer has a complete local repository with its own history and can commit changes locally before sharing them with others. Git is a Distributed Version Control System.

**What are the git stages that a file goes through when a developer makes a change and saves it? Consider local and remote repositories.**

A developer typically modifies a file in the working directory, stages it using `git add`, and then commits it to the local repository using `git commit`. To share the change with others, the developer pushes the commit to a remote repository, and other developers can retrieve those changes by pulling from the remote repository.

**What is a branch?**

A branch is a separate line of development within a Git repository that allows developers to work on features, bug fixes, or experiments without affecting the main codebase. Branches can later be merged back together when the work is complete.

**What is a branching strategy?**

A branching strategy is a set of rules that a team follows for creating, naming, using, and merging branches. It helps developers collaborate consistently and reduces confusion when multiple people are working on the same project. A popular example is GitFlow, which uses separate branches for features, releases, and hotfixes to organize development work.

**What is a Pull Request?**

A Pull Request is a request to merge changes from one branch into another, often from a feature branch into the main branch. It gives team members an opportunity to review code, discuss changes, and suggest improvements before the changes are merged.

**What is the difference between Git and GitHub?**

Git is the version control system that tracks changes and manages repositories on your computer. GitHub is a cloud-based platform that hosts Git repositories and provides collaboration features such as Pull Requests, code reviews, issue tracking, and team management.

**Extra: Trace the steps of development on a team that uses branches.**

A developer starts by switching to the `main` branch and running `git pull` to download the latest changes from the remote repository. This ensures they begin with the most current version of the project.

The developer then creates and switches to a new branch using `git checkout -b add-login-feature`. This branch provides an isolated place to work without affecting the `main` branch.

Next, the developer edits one or more files and saves their changes. Git now recognizes those files as modified. The developer stages the desired changes using `git add filename`, which places the files into the staging area.

Once the changes are staged, the developer creates a commit with `git commit -m "Add user login form"`. The commit records a snapshot of the changes in the developer's local repository.

To share the work with the team, the developer pushes the branch to the remote repository using `git push origin add-login-feature`. Other team members can now see the branch.

The developer then creates a **Pull Request (PR)**. The Pull Request asks teammates to review the code before it becomes part of the main project.

Reviewers examine the changes and may either approve them or request improvements. If changes are requested, the developer updates the files, stages them with `git add`, creates another commit with `git commit`, and pushes the updates with `git push`. The Pull Request automatically reflects the new commits.

After the Pull Request is approved, it is merged into the `main` branch. The feature or bug fix is now part of the official project.

Finally, all team members update their local copies by switching to `main` and running `git pull` so they receive the newly merged changes.

The overall workflow is:
```
Pull main  
  ↓  
Create branch  
  ↓  
Edit files  
  ↓  
git add  
  ↓  
git commit  
  ↓  
git push  
  ↓  
Create Pull Request  
  ↓  
Code Review  
  ↓  
Merge into main  
  ↓  
Team pulls updated main
```

This workflow allows multiple developers to work on different features simultaneously while keeping the `main` branch stable and organized.

## 3.1 Architecture

**What does the term "software architecture" refer to?**

Software architecture is the set of principal design decisions about a system: the high-level structure that defines its major components, their relationships, and the principles governing design and evolution. It covers structure, behavior, interaction, and non-functional properties. Because it guides future changes, "evolution" is a key word in the definition.

**When does a technical decision belong to the developer versus the architect?**

Not every design decision has architectural status; only **principal** ones do. Picking a data structure is usually just a design detail, but if, for example, the app runs on phones where memory footprint matters, the choice affects the system's goals and becomes principal. What counts as "*principal*" depends on the goals the team defines for the system.

**Explain how the two types of requirements relate to architecture.**

**Functional** requirements (*what the system does*) are mostly satisfied by the implementation. **Non-functional** requirements such as scalability, maintainability, security, and performance are largely determined by the architecture. So the high-level structure of a system affects things like performance, robustness, and distributability. A common activity is to turn a non-functional requirement into a functional one that can be built and tested.

**Why are the "ilities" (such as reliability, security, and performance) important to a product's success?**

Functional requirements are what cause a customer to want a product, but non-functional requirements (reliability, performance, security, and more) can cause a customer to stop using it. Because the "ilities" can sound vague, metrics are needed to verify them objectively. Many of them overlap in meaning, usually with a twist or slant.

**What does a block diagram do for an architecture?**

A block diagram illustrates the high-level structure of a system without detailing each component's internals. Each block is a self-contained unit, and arrows, nesting, or spatial arrangement show how blocks interact or are connected. Block diagrams focus on abstraction, modularity, and hierarchy, and are not part of UML.

**Describe the visual components of a context diagram (a Level-0 data flow diagram). What do they represent?**

In a context diagram the circle is the system being developed, the boxes are the external systems or data sources and sinks it interacts with, and the arrows are data flows. Seeing the boundary clearly shows what the team must build and which outside systems it depends on. A good diagram tells as much of the story as possible without becoming confusing.

**What is an architectural pattern?**

An architectural pattern is a reusable collection of architectural design decisions for a problem that keeps coming up. Different patterns serve different purposes, just as a castle is built for protection while a house is built for a family to enjoy. Examples include client-server, layered, microservices, and sense-compute-control.

**What is the client-server architectural pattern?**

Client-server separates the requester (client) from the provider (server) and uses a request-response model over a network. Keeping logic and data on the server helps with consistency, scalability, and maintainability, and the pattern is flexible about how clients and servers are built internally. It is the stereotypical architecture of web and networked systems.

**What is a major concern with the client-server architecture?**

Because services are centralized, a server failure can bring down every application that depends on it, making it a single point of failure. Other concerns include exposure to attacks such as man-in-the-middle and denial of service (mitigated by encryption, internal networks, and authentication), the cost of maintaining services, and latency or performance bottlenecks.

**How does a peer-to-peer (P2P) system differ from a client-server system?**

In peer-to-peer systems there is no central server, so peers communicate directly, as in BitTorrent file sharing. All P2P systems are decentralized and distributed, but not all decentralized systems are P2P. Decentralized means control is spread among many entities (such as Bitcoin), while distributed means components are spread across locations but may still be centrally controlled (such as distributed data centers).

**Describe the layered (multi-tiered) architecture?**

In a layered architecture each layer provides its own set of services and depends only on the layer directly below it, so a layer can be swapped for another implementation with the same interfaces. A common web-app stack is presentation, business, persistence, and database layers. Known pitfalls include tight coupling, inefficient communication across layers, limited flexibility, and testing challenges.

**A typical e-commerce website uses several architectural patterns together. What does this illustrate?**

Patterns are not mutually exclusive. A website is a classic client-server system that is typically layered, its presentation layer may use MVC, its persistence layer may use the Repository pattern, and some systems also adopt microservices. The code itself is usually written in an object-oriented language.

**What is the microservices architectural style? Provide one of its key benefits.**

Microservices split an application into small, loosely coupled services that each handle a specific business capability and communicate through well-defined APIs. Each can use different technologies and be scaled or updated independently, and a failure in one service (such as search) need not stop others (such as checkout). Amazon, Netflix, and Uber are well-known users, following ideas like the Bezos API mandate that teams communicate only through service interfaces.

**What type of project would a microservices architecture most likely be a poor choice?**

Microservices are overkill for small or simple applications, like a basic CRUD blog, and for early-stage startups, where the extra complexity can slow development and raise costs. They require robust infrastructure (container orchestration, monitoring, logging), make data consistency harder, and introduce network latency and failure points. Martin Fowler suggests building a monolith first and extracting microservices once the boundaries are well understood.

**Describe the sense-compute-control architectural pattern.**

Sense-compute-control (also called stimulus/response) is used when a system must react to its environment: sensors collect data, computation processes it and makes decisions, and controllers or actuators act on the environment. Typical uses are embedded systems and robotics, such as self-driving cars, drones, and smart thermostats. Concerns include sensor reliability and accuracy (fault tolerance and robustness) and strict real-time constraints.  

## 3.2 Arch to Design

**MMM Chapter 4:**   
We want an Aristocracy (an intellectual elite) to be the architect so that we have an elegant design. This does not negate the intellect & creative genius of the developers, for the architecture is just different (at a larger scale).  
Here are some salient points the author makes

* Conceptual integrity (a cohesive design that appears as one) is the the most important consideration in the system design. It would be bad to have uncoordinated ideas haphazardly clustered together.   
* The purpose of a programming system is to make a computer easy to use. The architecture of a system is the complete and detailed specification of the user interface.   
* “The separation of architectural effort from implementation is a very powerful way of getting conceptual integrity on very large projects.” It is good to have an Architect who does not do the implementation.

Implementers raise objections that are both **Real** and an **Illusion**:

1) (Real) The specifications will be too rich in function and will not reflect practical cost considerations.  
2) (Illusion) The architects will get all the creative fun and shut out the inventiveness of the implementers.  
3) (Illusion) The many implementers will have to sit idly by while the specifications come through the narrow funnel that is the architecture team.  
   1) This is one of timing and phasing. A quick answer is to refrain from hiring implementers until the specifications are complete.  

**Blessed Isolation \- Better Design**  
Architecture is the way to bridge the gap between large products and small teams. “Isolation” in this title’s context is that teams can be isolated from one another and still function nicely on a single product because the architecture bridges them together.

Documentation is needed when there are:

1) Lots of people to communicate to  
2) The time from design to implementation is large  
3) The distance between developers is not small (different floors, buildings, cities, states, continents, time zones)  
   

Design documents, or any documentation for that matter, are good when the documentation is needed. Don’t waste time. Don’t avoid doing what is necessary.

* “The whole point of architecture is to break intractable problems into little manageable ones.”

The process of creating architecture is simple:

1. Collect scenarios and requirements the product architecture must satisfy.  
2. Ensure those scenarios and requirements are clear, complete, and independent.  
3. Map scenarios and requirements to product components that will implement them.  
4. Identify interfaces between the product components.  
5. Inspect the components and interfaces for failures and vulnerabilities.  
6. Document the components and interfaces.  
7. Redesign and refactor as issues and new requirements emerge.

[**The other side of quality--Designers and architects**](https://imwrightshardcode.com/2006/02/the-other-side-of-quality-designers-and-architects/)

**The other side of quality–Designers and architects**  
The trouble is that quality and value are wrapped in perception. Even if we built a product that precisely matched the spec with zero bugs, customers and reviewers might still hate it. If it doesn’t work the way they think it should, it’s junk. If it doesn’t solve the problem the way they expect, it’s trash.  
By ***designers***, Brechner means the people involved in **defining the user experience**… the “what.” Good designers really understand the entire customer experience.  
By ***architects***, Brechner means the people involved in defining the **end-to-end implementation approach**… the “how.” 

**Customer** and **business needs** define the “why” and “when.”  
*Good designers produce a pipe dream. Good architects make it real.*  
Designers and architects must envision and describe the road map to realize customer value. This is not waterfall because you simply need to know what you want to achieve and to think through the pitfalls, not create an exhaustive document of everything.  
Designers and architects play different roles, but they share one aspect in common: broad, end-to-end scope. Their job is to think across feature boundaries, product boundaries, and even market boundaries to seize opportunities.

**1\. What does Brooks mean by "conceptual integrity," and why does he argue that it is the most important quality of a software system?**

Conceptual integrity means that all parts of a software system follow a consistent set of design principles and work together in a unified way. Brooks argues that this consistency makes a system easier to learn, understand, and use, even if it means leaving out some attractive features that do not fit the overall design.

**2\. Why does Brooks believe that the architecture of a system should be designed by one person or a small group of closely aligned people rather than by a large committee?**

Brooks believes that a small group can maintain a clear and consistent vision for the system. When too many people make architectural decisions independently, the result is often a collection of conflicting ideas that make the system harder to use and maintain.

**3\. How can software developers contribute creatively to a project even when the overall architecture has already been defined by architects?**

Developers still make many important design decisions about algorithms, data structures, module organization, and performance improvements. Working within architectural constraints often helps developers focus their creativity on solving technical problems effectively and efficiently.

**4\. What is the difference between Design and Architecture?**

Architecture focuses on the high-level structure of a software system. It defines the major components, how they interact, and the key technical decisions that guide development. Design focuses on the detailed solution within those components, including classes, algorithms, data structures, and implementation details. A team may create the architecture for the entire system first, while individual development teams design and implement the subsystems they own.

**5\.  What is the main point of the article, "Blessed isolation – Better design"?**

Architecture is the way to bridge the gap between large products and small teams. “Isolation” in this title’s context is stating that teams can be isolated from one another and still function nicely on a single product because the architecture bridges them together. 

**6\. How is architecture defined when the SDLC is Kanban?**

In a Kanban process, architecture can be developed incrementally rather than being **fully** defined upfront. **Architects establish an *initial* structure and set of guiding principles**, then refine and evolve the architecture as new requirements emerge and work items move through the Kanban workflow. The architecture remains an important roadmap, but it is treated as something that continuously adapts to feedback and learning throughout the project.

There is also the possibility of a team of architects creating the architecture fully upfront, before any implementation beings. Then, various small teams may own a (sub)system within the architecture and they use Kanban in its implementation. A small architecture team creates the overall system architecture before implementation begins.

1. A small architecture team creates the overall system architecture before implementation begins. And this architecture partitions the system into subsystems or services.  
2. Each implementation team owns one of those subsystems.  
3. Each team uses Kanban to manage and execute the detailed design and implementation of its subsystem.

The architecture team decides what pieces exist and how they fit together. The implementation teams decide how to build their assigned pieces.

**More on Architecture vs Design**  
It can be hard to define Architecture. From [Martin Fowler's article](https://martinfowler.com/architecture/), we can see several attempts at defining it:

* The shared understanding that the expert developers have of the system design.  
* The decisions you wish you could get right early in a project.  
* Architecture is about the important stuff. Whatever that is.

Architecture concerns the decisions that are *hard to change later*, while design concerns decisions that are *comparatively easy to change later*. 

Architecture is about decisions that are:

* **Expensive to reverse** — pick the wrong database or messaging system and you're looking at a painful migration, not a refactor  
* **System-wide in scope** — they constrain everything built afterward  
* **About boundaries and communication** — how do services/systems talk to each other, where do they live, what are the contracts between major pieces

Design is about decisions that are:

* **Cheaper to change** — reorganizing classes or renaming interfaces is a Tuesday afternoon, not a quarter-long migration  
* **Local in scope** — affects a module or component without necessarily rippling outward  
* **About internal structure** — how responsibilities are divided, what the class/function hierarchy looks like, how data flows within a bounded piece of code

**The line moves with context.** In a small app, choosing a design pattern (e.g., how you structure your service layer) might be the highest-leverage decision in the whole project. This Design Pattern is effectively "the architecture" for that codebase. In a large distributed system, that same decision is a rounding error (i.e. too small to be significant; too small to be considered architecture).

**Some people use a three-tier split** instead of two: 

1. *Architecture* (system/enterprise level) →   
2. *Design* (component/module level) →   
3. *Detailed design* or *implementation design* (interfaces, algorithms, class structure within a module). 

