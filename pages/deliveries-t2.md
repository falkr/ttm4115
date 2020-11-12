# Delivery T2

In this delivery you should reveal some details on the design of your system. The design should cover the main functionality of the system and include the most important critical details. Obviously, once you implement the system, there may turn up more details. The kitchen timer was an idealized example for this. Each team created decent state machines that documented the important details of the kitchen timer. The subsequent implementation could then focus more on the details how to implement specific actions in Python, but the overall logic was settled. 

Some technical hints on the delivery:

- Team delivery, one document per team
- Please use the file name **ttm4115-2020-t2-team-XX.pdf**
- Include the team name on each page, in the footer or header


## Plans for UI Components

Your system will be fully virtual, that means, not contain any specific hardware or sensors.
Instead, you should create [GUI components](tools-gui.html) that simulate the hardware components.
Please include a list of all GUI components you intend to create for your system, and provide a first sketch of them.


## Updated Deployment Diagram

Create a deployment diagram of the system. You can copy the one from T1 and adapt it to any changes in your plans. 

* Take into account what you have learned about components, state machines and about communication.
* Include the GUI components outlined above.
* Identify components that include state machines.

**Hints:**

* Usually a deployment diagram should fit on a single page.
* Use landscape format if you want.


---
type: table
file: files/rubrics/deployment.mw
class: rubric
caption: '<a href="learning-grading.html#grading-criteria">Read more about these criteria...</a>'
---

* Tips for [diagram layout](unit-modeling-diagram-tips.html)
* Syntax for [deployment diagrams](prep-modeling.html)
* Level of detail: Details that are included matter, and are not accidental.

## Sequence Diagrams

Prepare sequence diagrams for the main use cases of the system. As you have learned in the team activities, it is hard to cover all details on sequence diagrams, and they may lose their value once we make them too complicated or too comprehensive. Therefore, cover the most important scenarios in an effective way. Use fragments (alt, opt,...) where they make sense, but also consider to just cover the same use case with several sequence diagrams that show different scenarios, dependent for instance on important alternatives and exceptions.

The level of detail should be so that it helps you to convey the overall system interactions, help you to create the state machines and uncover critical situations that require clarifications.

How much? Depends of course on your layout. If two diagrams fit on a page, most of your use cases should be covered within 4 pages. Use your own judgment.


---
type: table
file: files/rubrics/interactions.mw
class: rubric
caption: '<a href="learning-grading.html#grading-criteria">Read more about these criteria...</a>'
---

* [Syntax for interactions](prep-interactions.html).
* Pay attention that you select which scnarios to show so that it not only provides coverage, but also helps to understand.
* It is, in principle, possible to not use any combined fragments. They should be applied where they help.
* If you don't find any implied scenarios, make sure your system is suitable for the course and not overly simplifying reality. If despite this there are no implied scenarios, add a comment.


## State Machines

Create state machines for selected components in the system.

* State machines must be syntactically correct.
* State machines must be complete.
* State machines must be implementable in STMPY (in principle), but you don't have to implement them yet.


---
type: table
file: files/rubrics/statemachines.mw
class: rubric
caption: '<a href="learning-grading.html#grading-criteria">Read more about these criteria...</a>'
---

* [Syntax for state machines](prep-statemachines.html).
* A wrong use of control states would be when variables are used to keep track of information that is more suitable for control states. See [here](unit-statemachines-data.html).
* The state machine should be consistent with respect to states and transition and the requirements. For instance, it does not end up in a deadlocked state or ignore an event unless the requirements are okay with this.


## Overall Delivery

At this stage, you should also have a look at the overall quality of the delivery, that means, how the individual parts are connected. 

---
type: table
file: files/rubrics/overall.mw
class: rubric
caption: '<a href="learning-grading.html#grading-criteria">Read more about these criteria...</a>'
---

# Reflection and Request for Feedback

In the last part of the delivery, please add a section in which you reflect about how well you have answered the individual criteria from above. 

## Your Own Assessment

* For each ot the criteria tables, mark for the different criteria rows which level you think you have achieved. 
* Below the table, add a short comment on your choice.
* Comment on what you think could further be improved.
* Comment on what you think is solved nicely.
* Comment also if you think that the criteria are not covering a performance well.


## Request for Feedback

For each of the criteria tables, tell us what you wonder about most, that means, ask explicitly for the points you are most unsure, or items you want to have tips for.
