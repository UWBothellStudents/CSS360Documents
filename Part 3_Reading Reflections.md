# Quiz 3: Reading Reflections

## Summary
This section's overall theme is **Project Management** as we examine techniques to gather requirements, create an archtiecture, brainstorm features, how to estimate costs, and how to test.  We look at using UML to draw architecture--to remove software's invisibility characteristic.  

### Slide Decks

* 3.3 System Models  
* 3.4 Brainstorming & Estimation  
* 3.x Requirements   
* 3.5 Project Management & Testing

### 3.3 System Models

#### Overview:

* [Unified Modeling Language (UML) Diagrams \- GeeksforGeeks](https://www.geeksforgeeks.org/system-design/unified-modeling-language-uml-introduction/)   
* [Agile Models Distilled: Potential Artifacts for Agile Modeling](https://agilemodeling.com/artifacts.htm)   
* Examples: [Examples of UML diagrams \- use case, class, component, package, activity, sequence diagrams, etc.](https://www.uml-diagrams.org/index-examples.html)   
* Sommerville: Chapter 5: [Software Engineering, 10th GLOBAL Edition](https://dn790001.ca.archive.org/0/items/bme-vik-konyvek/Software%20Engineering%20-%20Ian%20Sommerville.pdf) 


#### Data Flow Diagram

* [What is DFD (Data Flow Diagram) \- GeeksforGeeks](https://www.geeksforgeeks.org/software-engineering/what-is-dfddata-flow-diagram/)   
* [Data Flow Diagram (DFD)s: An Agile Introduction](https://agilemodeling.com/artifacts/dataFlowDiagram.htm) 

#### Sequence Diagram

* [Sequence Diagram Tutorial \- Complete Guide with Examples | Creately](https://creately.com/guides/sequence-diagram-tutorial/)   
* [UML Sequence Diagrams: An Agile Introduction](https://agilemodeling.com/artifacts/sequenceDiagram.htm)    
* [UML sequence diagrams overview of graphical notation \- lifeline, message, execution specification, interaction use, etc.](https://www.uml-diagrams.org/sequence-diagrams.html) 

#### Class Diagram

* [UML Class Diagrams: An Agile Introduction](https://agilemodeling.com/artifacts/classDiagram.htm)   
* [UML Class Diagram \- GeeksforGeeks](https://www.geeksforgeeks.org/system-design/unified-modeling-language-uml-class-diagrams/)   
* [UML Class Diagram Tutorial](https://www.visual-paradigm.com/guide/uml-unified-modeling-language/uml-class-diagram-tutorial/) 

#### Activity Diagram 

* [https\://www\.geeksforgeeks.org/system-design/unified-modeling-language-uml-activity-diagrams/](https://www.geeksforgeeks.org/system-design/unified-modeling-language-uml-activity-diagrams/)   
* [Activity Diagram \- Activity Diagram Symbols, Examples, and More](https://www.smartdraw.com/activity-diagram/) 

#### Use Case Diagram

* [Use Case Diagram \- Unified Modeling Language (UML) \- GeeksforGeeks](https://www.geeksforgeeks.org/system-design/use-case-diagram/)   
* [UML Use Case Diagrams: An Agile Introduction](https://agilemodeling.com/artifacts/useCaseDiagram.htm)   
* [Use case diagram \- Wikipedia](https://en.wikipedia.org/wiki/Use_case_diagram) 

#### State Diagram

* [State Machine Diagrams | Unified Modeling Language (UML) \- GeeksforGeeks](https://www.geeksforgeeks.org/system-design/unified-modeling-language-uml-state-diagrams/)   
* [UML State Machine Diagrams: An Agile Introduction](https://agilemodeling.com/artifacts/stateMachineDiagram.htm) 

	  
#### **EXTRA**:  
##### Network Diagram

* [Network Diagrams: An Agile Introduction](https://agilemodeling.com/artifacts/networkDiagram.htm)   
* [Computer network diagram \- Wikipedia](https://en.wikipedia.org/wiki/Computer_network_diagram) 

##### Entity Relationship Diagram

* [ER Diagram Symbols: Complete Guide to Notations & Meanings](https://www.we-notes.com/component-breakdown-decoding-er-diagram-symbols/) 

### 3.4 Brainstorming & Estimation

* [Dev schedules, flying pigs, and other fantasies – I.M. Wright’s “Hard Code”](https://imwrightshardcode.com/2001/06/dev-schedules-flying-pigs-and-other-fantasies/)   
* [Project buffer overflow – I.M. Wright’s “Hard Code”](https://imwrightshardcode.com/2018/11/project-buffer-overflow/)

### 3.5 Project Management and Testing

* [The Mythical Man-Month. | Chapter 2](https://learning.oreilly.com/library/view/mythical-man-month-the/0201835959/ch02.xhtml)   
* [Calling the Shot | Chapter 8 | Mythical Man-Month](https://learning.oreilly.com/library/view/mythical-man-month-the/0201835959/ch08.xhtml)   
* [Hatching a Catastrophe | Chapter 14 | Mythical Man-Month](https://learning.oreilly.com/library/view/mythical-man-month-the/0201835959/ch14.xhtml) 

	**Optional**:

* [JUnit — Practical Java](https://java.mrstride.com/frameworks/junit.html)   
* [Practice: Test Guidelines — Practical Java](https://java.mrstride.com/frameworks/good_tests.html) 


# 3.3 System Modeling with UML 
These questions come from the 3.3 Slide deck.

**Why do software teams create system models?**

Software is largely invisible, so models take the "invisible" out of it by turning ideas into graphical representations people can see and discuss. They help the team understand the problem and the system to be built, and they convey that understanding to others such as customers and developers.

**A system model usually leaves out many details of the real system. Why is this considered a strength?**

A model is an abstract view of the system, so it deliberately omits detail. Leaving details out reduces noise and confusion and keeps attention on what is important to understand.

**Which statement best describes UML (Unified Modeling Language)?**

UML is a standardized set of diagram types, semantics, and notations for modeling systems, designed to support object-oriented analysis and design. It includes 14 diagram types, grouped into structural diagrams (such as class diagrams) and behavioral diagrams (such as use case, sequence, activity, and state machine diagrams).

**What is the main purpose of a context diagram?**

A context diagram shows the single system of focus at the center, with the external entities and the data that cross the system boundary. Knowing the boundary tells you what you will develop and what you will depend on other systems for. It is like a high-level (Level 0) DFD.

**Which of the following is true of a Data Flow Diagram (DFD)?**

A DFD models how data moves through a system between processes, data stores, and external entities, as if you were "interviewing the data." It is not a process diagram: it has no conditionals or logic and does not define an order, although order can often be inferred. DFDs can be drawn at multiple levels, from Level 0 (the context diagram) down to more detailed levels.

**What does an Entity-Relationship Diagram (ERD) describe?**

An ERD describes the logical structure of the data: the entities, their attributes, and the relationships between entities. It models the data itself, not classes or behavior, and the physical structure may differ to address performance and maintenance. It is widely used in database design.

**What does a state diagram (state machine diagram) show?**

A state diagram shows the states of a system, process, or object and the events that cause it to transition from one state to another. For example, a safe might move between wait, open, and lock states. Transition labels follow the pattern: action \[condition\] / resulting action.

**How does a UML class diagram differ from an ERD?**

A class diagram models the static structure of software, including both data (attributes) and behavior (methods), and uses relationships such as association, aggregation, composition, and inheritance. An ERD models only data and its relationships, usually for database design. The two are complementary tools, not interchangeable.

**In a UML class diagram, what is the difference between composition and aggregation?**

Both are "has-a" relationships, but they differ in ownership. In composition (filled diamond) the part cannot exist independently, so if the whole is destroyed the part is destroyed too, such as a hash map and its hash table. In aggregation (open diamond) ownership is shared, so the parts live on if the whole goes away, such as students in a course section that is cancelled.

**What is a UML use case diagram primarily used to show?**

A use case diagram shows the interactions between a system and its external actors (people or other systems). Actors are drawn as stick figures outside the system boundary, and use cases (the tasks) are drawn as ovals inside it. It is typically used during requirements analysis to identify the functionality the system should offer, with relationships such as include and extend linking use cases.

**In a UML activity diagram, what do a fork and a join represent?**

A fork splits the flow into actions that can happen in parallel, where the order does not matter. A join synchronizes those parallel actions so the flow continues only when they are done. Choices are shown separately with a decision and merge.

**Which statement correctly describes how to read a UML sequence diagram?**

Read it from top to bottom, because time moves downward, not left to right. Each participant has a vertical lifeline, activation bars show when it is actively working, and horizontal arrows show messages in order, with solid arrows for requests and dashed arrows for replies. Closed arrowheads indicate synchronous calls and open arrowheads asynchronous ones.

**Why do analysts often use several different types of models for the same system?**

Different models are complementary: each captures a different kind of information, such as data flow, data structure, interactions, or behavior. Together they give a more complete picture than any single model could. Which approach a given model belongs to matters less than knowing that many models exist.

**A student's sequence diagram for a trip to Hawaii includes the arrows "Fly to Hawaii" and "Drive to hotel." Why is this a poor sequence diagram?**

It mixes messages with physical activities and state changes. A sequence diagram is about communication between participants, such as "Give ID" or "Provide reservation information," and should answer who communicates with whom, what is exchanged, and in what order. Activities like flying or driving belong in an activity diagram, a use case scenario, or a written narrative.

**How do classical structured analysis and object-oriented analysis differ in their view of a system?**

Classical structured analysis emphasizes that process and data are separate, and uses process-oriented models such as DFDs, ERDs, and state transition diagrams. Object-oriented analysis unifies data and behavior around objects, using UML diagrams such as class, use case, sequence, and activity diagrams. The boundaries between the approaches are blurry, so the key point is knowing the focus of each.


# 3.4 Brainstorming & Estimation

**Dev Schedules, Flying Pigs**  
Development scheduling succeeds when it prioritizes risk management over rigid deadlines, focuses on critical features first, and avoids the myth of precise time estimations. Teams and customers benefit most when the process emphasizes quality and coherence over arbitrary dates.

1. Dev estimations are flawed.  
2. Effective project planning costs are T-shirt sized  
3. Projects schedule high priority features first so that cuts can be made to low-pri items later  
4. **Scheduling is less about hitting feature deadlines and more about managing risks.**  
5. A risk-managed approach leads to delivering high-quality, essential features that truly satisfy customer needs.  
6. Customer-centric focus fosters better team collaboration, morale, and decision-making

**Project Buffer Overflow**  
To estimate, use historical completion rate.  
Accurate estimation requires using historical data, trusting calculated timelines, and applying only necessary buffers. Avoid unrealistic promises and overcommitment by focusing on scope management and maintaining professional, data-driven planning. This approach builds trust with customers and management while preventing burnout and disappointment.

1. Commit to deliverables when you can ensure the scope and timeframe are realistic and achievable  
2. Use historical data and avoid wishful thinking  
3. Break features into small tasks and use a team’s velocity to estimate completion date  
4. Avoid “magical” buffers  
5. Three kinds of buffers:  
   1. Buffer of work: to keep everyone productive at all times. Good to have.  
   2. Time buffer: added to time estimates. Bad because it avoids addressing the real problem–bad estimates.  
   3. Last-mile buffer: accounts for variations and end-of-game delays. Historical data shows that it takes time to account for last-minute “hijinks” that invariably pop up.

## Flying Pigs

**1\. Why does Wright argue that detailed feature-by-feature schedule estimates are largely a fantasy, and what experience does he use to support that claim?**

Wright argues that software development contains **too much uncertainty** for precise feature-level estimates to be reliable. He bases this view **on practical experience**, claiming that beyond very small or highly repetitive tasks, developers often cannot accurately predict how long implementation will take.

**2\. What is the purpose of the "hard/medium/easy" estimation scale, and how does it differ from assigning specific dates to individual features?**

The purpose of the scale is to provide a rough assessment of effort while **acknowledging uncertainty.** Unlike specific feature dates, it helps teams reason about capacity and risk without creating a false sense of precision.

**3\. Wright claims that development scheduling is primarily about risk management rather than time management. What risks does he believe a schedule should help a team manage?**

Wright believes schedules should help teams manage the **risk that we won't deliver the right features with the right quality at the right time.** His approach focuses on protecting critical functionality rather than attempting to predict exact completion dates for every feature.

**4\. Do you agree with Wright's statement that "the only dates that count are project dates" and not feature dates? In what situations might feature-level dates still be valuable?**

Milestones are generally more important because they keep attention focused on **overall product success** rather than individual tasks. However, feature-level dates can still be useful when *coordinating dependencies* among teams or tracking particularly high-risk work.

**5\. According to Wright, how can feature deadlines actually make a project more likely to fail, even though deadlines are intended to improve accountability?**

Wright argues that developers who feel pressure to hit feature deadlines may hide problems instead of communicating risks early. This reduces management's ability to respond to emerging issues and can lead to lower quality, increased stress, and larger schedule slips later.

**6\. If you were managing a modern Agile team using tools such as GitHub and Scrum boards, which parts of Wright's approach would you adopt and which parts would you reject? Why?**

One might put emphasis on prioritizing must-have features, communicating risk early, and avoiding false precision in estimates. One could reject the idea that feature dates are largely irrelevant because Scrum boards, sprint goals, and backlog planning benefit from shorter-term commitments that help teams coordinate work while still accommodating uncertainty.

## IMW Buffer Overflow

**1\. Wright argues that most traditional estimation buffers are unnecessary. What are the three types of buffers he describes, and why does he believe only one of them is actually needed?**  
1\) a work buffer that keeps engineers supplied with ready-to-start tasks; 2\) an estimation buffer that compensates for poor estimates, and; 3\) a final delivery buffer that accounts for last-minute variation and surprises. He argues that if estimates are based on historical completion data, only the final delivery buffer is necessary because the other two exist primarily to compensate for poor planning or inaccurate estimation practices.

**2\. How does Wright propose using historical team data to estimate future work, and what assumptions must be true for this approach to succeed?**  
He recommends calculating a team's historical task completion rate and then estimating a feature by dividing its expected number of tasks by that rate. This approach assumes that work is consistently broken into reasonably similar-sized tasks, that the team has reliable historical data, and that future work resembles the work used to establish the completion rate.

**3\. Wright repeatedly tells readers to "believe the estimate." Why does he think teams and managers struggle to trust estimates that are based on historical data?**  
He believes people often distrust data-driven estimates because they want to believe they can work faster, work harder, or somehow achieve a better outcome than their historical performance suggests. He argues that this optimism leads managers and engineers to second-guess valid estimates instead of accepting what the data indicates about likely completion dates.

## 3.x Requirements

**Functional Requirement:**

* Describe functionality from the **user’s perspective**.  
* Focus on **what the system should do** (functional behavior).

**Non-Functional Requirements (NFRs)**:

* Describe **quality attributes** (performance, security, scalability, usability).  
* Often apply to the **system as a whole**, not a single user interaction.  
* Example: *The system must respond within 2 seconds under peak load*.

User Stories

1. Non-Functional: As a business owner, I want my product to scale to 20k users.  
2. Non-Functional: As a user, I want the app to be responsive (no lag greater than 500ms).  
3. **Design Constraint:** As a system architect, I want the application to use a Redis cache for shared data so that distributed servers can access frequently used information efficiently.  
4. Functional: As a customer, I want to reset my password through email verification so that I can regain access to my account if I forget my password.

**RE: Design Constraint**

This is neither a functional nor a non-functional requirement. It specifies an implementation decision. The system's users do not care whether Redis is used; they care about the resulting performance. This statement constrains the design. 

The user story leans towards a non-functional requirement by stating "distributed servers can access frequently used information efficiently". The word *efficiently* should be replaced with a metric.  

**Constraint:** "The system shall use Redis." (implementation choice)  
**Functional requirement:** "The system shall provide an API for storing and retrieving cached data."  
**Non-functional requirement:** "The API shall return responses within 100 ms for 95% of requests."

## 3.5 Project Management & Testing

### The Mythical Man-Month (Chapter 2)

Brooks argues that software projects are frequently underestimated because people are overly optimistic about how smoothly work will proceed. He explains that while project cost may be measured in man-months, project progress cannot be accelerated simply by adding people because of communication and training overhead. People underestimate testing and integration work. He states Brook's Law: adding manpower to a late software project often makes it even later.

* People incorrectly assume that *effort* and *elapsed time* are interchangeable.  
* Adding more people into a development process does not increase the speed of development. In fact, it can sometimes slow things down because of added communication requirements, coordination, and ramp-up time.  
* Task Division Challenges: Plenty of tasks cannot be broken down, distributed, and done in parallel. For example, 9 women cannot give birth to a baby in 1 month.  
* People ought to use historical productivity data to improve estimates  
* The myth is: more people equals fast work.  
* Brooks’ Law: *“Adding manpower to a late software project makes it later.”*  
* Software projects often suffer from optimism about deadlines and underestimate unforeseen complexities. Brooks emphasizes the importance of contingency planning and realistic scheduling.  
* The Second-System Effect: Brooks warns that engineers often over-design their second system, incorporating excessive features learned from their first project, leading to bloated, delayed, and overly complex systems.

**A somewhat controversial or extreme claim**

The most famous and controversial claim from the chapter is:

> "Adding manpower to a late software project makes it later."

This claim, which later became known as **Brooks's Law**, runs counter to the common-sense belief that adding more workers should always help a project finish sooner. Brooks argues that onboarding and communication costs can outweigh any productivity gains from the additional personnel.

**Arguable given today's software engineering**

Software projects today are often organized around smaller autonomous teams and modular architectures that can make parallel development more practical. Nevertheless, Brooks's core observation about onboarding costs, communication overhead, and the limits of dividing knowledge-intensive work remains widely accepted.

**Q\&A**

1. **Brooks argues that two things are not interchangeable. What are those? Why does that impact estimation?**  
   Brooks argues that **effort and elapsed time** are not interchangeable. A project requiring 12 man months of effort cannot necessarily be completed by 12 people in one month because many tasks must be performed sequentially and because additional people create communication and coordination overhead, which makes schedule estimation more complex. There is also no direct relationship between Effort and Productivity, especially when we consider the broad range of people and their experience. It can be a huge effort to implement a relatively small feature; it may take a long time to discover a fix to a relatively small bug.

2. **Is Brooks's Law still 100% valid today? When is it more or less applicable?**  
   Brooks's Law is not 100% valid in every situation today, but its core insight remains relevant. It is most applicable when new developers must be trained, when work is highly interconnected, or when the project is already in trouble, and it is less applicable when work can be divided into largely independent tasks and new team members can contribute immediately.

3. **Is optimism still the primary source of inaccurate estimates? What might also contribute to inaccuracies?**  
   Optimism continues to be a major source of estimation error because people tend to assume that work will proceed without significant obstacles. Other contributors include changing requirements, technical debt, hidden complexity, incomplete requirements, organizational dependencies, staffing changes, and pressure from stakeholders to commit to aggressive schedules.

4. **Brooks argues that testing is the most mis-scheduled part of programming. How much proportional time does Brooks schedule for Coding vs Testing?**  
   Brooks argues that testing is often severely underestimated and suggests that ***coding typically accounts for about one-sixth*** of the schedule, while component testing and system testing together account for roughly half, while planning accounts for the remaining third. His recommendation was intended to counter the common assumption that coding is the majority of the work.

5. **What modern Testing technique do we use to help address the amount of time spent testing after development is done?**  
   Today, Testing and Development are done hand-in-hand, together with the deliverable. Furthermore, automated testing work can be done even before coding. This modern approach, automated testing, is coupled with Continuous Integration and Continuous Delivery (CI/CD) pipelines. By running unit tests, integration tests, and regression tests continuously throughout development, teams can discover defects earlier and reduce the large testing phase that traditionally occurred after coding was completed.

6. **If a project is behind schedule today, what actions should be tried before adding more developers, and how do those actions compare with Brooks's recommendations?**  
   Before adding developers, teams should identify bottlenecks, reduce scope, remove low value features, automate repetitive work, improve requirements clarity, and focus effort on the highest risk tasks. For heaven's sake, one could even consider moving the delivery date. Teams will always try to improve efficiency, but this doesn't always mean "working smarter." Often times the best way to improving efficiency is to automate\! People's level of efficiency is limited.

### Calling the Shots (Chapter 8)

**Summary** 

Brooks examines the challenge of software estimation and argues that reliable schedules must be based on empirical data rather than optimism or intuition. He reviews productivity data from several software projects and observes that programming effort grows nonlinearly with system size, that *coding itself represents only a fraction of total project work*, and that communication overhead and organizational complexity significantly affect productivity. Brooks's central message is that meaningful estimation requires collecting and **analyzing historical project** data because software development is too complex to estimate accurately through judgment alone. 

**A somewhat controversial or extreme claim**

One of the more striking claims in the chapter is that productivity can vary dramatically based on communication demands and project structure, with some studies showing programmers producing several times more output in low-communication environments than in highly coordinated projects. The implication that communication overhead can overwhelm the benefits of additional personnel can feel extreme to those who assume larger teams naturally produce software faster.

**What might be different or arguably wrong today?**

Brooks relies heavily on lines of code and instruction counts as measures of software size, whereas contemporary teams often think in terms of features, business value, user outcomes, or flow metrics. Many organizations today are skeptical of long-range software estimates and instead favor iterative forecasting approaches used in Agile and Lean development.

**Questions to Discuss**

1. **What is Brooks's argument for how software estimation should be done?**  
   Brooks argues that software estimation should be based on empirical evidence from past projects rather than intuition, optimism, or management pressure. He believes organizations should collect productivity and schedule data so future estimates can be grounded in actual experience rather than wishful thinking.  
2. **If coding represents only a fraction of total project effort, why do managers and stakeholders often focus so heavily on coding productivity?**  
   Coding is the most visible part of software development, making it easier to observe and measure than activities such as requirements analysis, design, testing, integration, communication, and project coordination. As a result, stakeholders often overestimate the impact of coding speed and underestimate the effort consumed by all the supporting work required to deliver a successful system.  
3. **How relevant are Brooks's observations about communication overhead now that teams have tools such as GitHub, Microsoft Teams, and modern collaboration platforms?**  
   Brooks's observations remain highly relevant because communication challenges arise from coordination and dependencies, not just the mechanics of exchanging information. Modern tools make communication faster and more transparent, but large teams still face significant overhead when aligning decisions, integrating work, and managing shared understanding.  
4. **Does the widespread use of Agile methodologies make software estimation easier, or does it simply change the way uncertainty is managed?**  
   Agile generally does not eliminate estimation difficulty; instead, it changes how uncertainty is handled by emphasizing short iterations, frequent feedback, and continual replanning. Rather than attempting to predict an entire project accurately upfront, Agile teams focus on improving forecasts as new information becomes available.

### Hatching a Catastrophe (Chapter 14)

**Summary**

Brooks argues that major project delays rarely result from a single disaster; instead, they emerge gradually through the accumulation of many small schedule slips that are ignored or underestimated. He emphasizes the importance of defining sharp, measurable milestones because vague notions such as "almost finished" obscure real progress and conceal delays. Brooks advocates the use of critical-path and PERT-style scheduling to **make dependencies visible**, identify which delays truly matter, and prevent teams from rationalizing lost time. Just making the chart can be of more value than the chart itself. He also discusses the organizational tendency to **hide problems from management**, stressing that leaders need reliable status information without automatically intervening. He recommends disciplined tools and process to **expose early warning signs** before a project becomes *a year late* "one day at a time."

Critical Path: The longest path in a project. If it is delayed, the entire project is delayed.

PERT: the Project Evaluation and Review Technique is a valuable tool for effective project management. It helps teams visualize the sequence of tasks, understand dependencies, and identify the critical path for timely project completion. It is a diagram showing: Tasks, Dependencies between tasks, Expected durations, and Critical paths through the project. It can look like an activity sequence diagram. 

The following PERT diagram shows that BOTH Database Design and UI Design need to be complete before Integration Testing begins. A delay in either impacts the release.
```
             ┌─> Database Design ──┐

Requirements ┤                     ├─> Integration Testing ──> Release

             └─> UI Design ────────┘
```

Brooks concludes with the claim that time dedicated to being a watchdog (an early warning system) can contribute more to overall project success than doing programming tasks. A few people dedicated to schedule visibility and coordination can prevent catastrophic project delays while a few additional programmers may add only marginal productivity. 

**What might be different or arguable today?**

Several aspects of the chapter can be questioned from a modern software engineering perspective:

1. **Heavy reliance on PERT and centralized planning.** Brooks views detailed dependency tracking and milestone management as the primary defense against schedule slippage. Modern Agile, Scrum, and Lean approaches often favor shorter iterations, continuous delivery, and empirical measurement over large upfront network schedules.

2. **Dedicated plans-and-controls groups.** Today's teams often distribute project visibility through tools such as GitHub, Azure DevOps, Jira, automated testing pipelines, dashboards, and observability systems. Many organizations would see a separate, dedicated team doing project-control function work to be bureaucracy causing information lag.

3. **The "hustle" concept.** While Brooks argues that great teams need reserve effort and urgency, modern engineering organizations are more sensitive to burnout. Many teams would argue that sustainable pace generally outperforms a culture of continual extra effort, especially over multi-year projects.

That said, the chapter's central warning about gradual schedule erosion remains surprisingly relevant. Anyone who has watched technical debt, deferred defects, or delayed pull requests accumulate has seen Brooks's "one day at a time" phenomenon in action. 

1. **Brooks argues that projects become late through many minor delays rather than major disasters. Is this still the dominant cause of software schedule failure today?**  
   Yes. While modern projects also face challenges such as changing requirements, technical debt, and organizational complexity, many schedule failures still result from the accumulation of small delays that seem insignificant individually but become substantial over time. 

2. **Are sharp, binary milestones a better measure of progress than modern Agile metrics such as story points, velocity, or burndown charts?**  
   Sharp, binary milestones are often better for determining whether a specific deliverable has actually been completed. But Agile metrics provide better visibility into trends, team capacity, and ongoing progress that is good for predicting future work and delivery dates. In practice, many teams benefit from using both approaches together.

3. **Do you think Brooks is correct in today's world when he says having a dedicated planning and controls function can contribute more to success than assigning those same people to development work?**  
   Partially. Brooks's argument still applies to large, complex projects where coordination failures can be more damaging than a lack of coding capacity, but modern tools have reduced the need for a separate planning and controls organization. The underlying need for visibility and coordination remains important.   
     
4. **How does Brooks use the word "Hustle" in the article? How does hustle impact culture and the development process?**  
   Brooks uses "hustle" to describe the habit of *acting sooner, working harder*, and maintaining reserve effort so that teams can *absorb everyday disruption*s without falling behind schedule. A culture of hustle can increase responsiveness and *accountability*, but if taken too far it can also contribute to stress, burnout, and unsustainable work practices.   
   

