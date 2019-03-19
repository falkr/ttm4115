# Delivery T2

In this delivery you should reveal some details on the design of your system. The design should cover the main functionality of the system and include the most important critical details. Obviously, once you implement the system, there may turn up more details. The kitchen timer was an idealized example for this. Each team created decent state machines that documented the important details of the kitchen timer. The subsequent implementation could then focus more on the details how to implement specific actions in Python, but the overall logic was settled. 

Some technical hints on the delivery:

- Team delivery, one document per team
- Please use the file name **ttm4115-2019-t2-team-XX.pdf**
- Include the team name on each page, in the footer or header


## Updated Deployment Diagram

Create a deployment diagram of the system. You can copy the one from T1 and adapt it to any changes in plans. Also, take into account what you have learned about components and state machines and about communication. Usually a deployment diagram should fit on a single page.

## Sequence Diagrams

Prepare sequence diagrams for the main use cases of the system. As you have learned in the team activities, it is hard to cover all details on sequence diagrams, and they may loose their value once we make them too complicated. Instead, cover the most important scenarios in an effective way. Use fragments (alt, opt,...) where they make sense, but also consider to just cover the same use case with several sequence diagrams that show a different scenario, dependent for instance on user choices.

How much? Depends of course on your layout. If There fit two diagrams on a page, most of your use cases should be covered within 4 pages. Use your own judgement.

## State Machines

Create state machines for the components in the system. 

* Build state machines, as introduced in the lecture notes. (This does not require to build the state machines in Python with STMPY.)
* If a state machine is large, spread it on several pages by referring to states by name.
* Work on the layout. A nice diagram is important, also for you to understand it.

How to select which state machines to build: Of course, make the state machine for components that coordinate several interactions and that are complicated. Usually, there should be one or two such components in the system. Optionally add state machines for simpler components. In total, you should have about 4 pages of state machines. (It is difficult to give a guideline; be reasonable.) If you only have trivial machines, make sure that your system handles message losses and works with acknowledgements and timeouts.




