# Airport Gate Control System

You should design the controller that resides within an airport gate turnstile. A communication diagram for the logic is shown below. (We haven't formally introduced this type of diagram, but you can read it similar to a deployment diagram. The blue arrows symbolize messages sent between the components.)

---
type: figure
source: figures/interactions/airport.png
caption: "A communication diagram for the controller and its connected components."
---


* The controller is connected to the turnstile, the LEDs, a display, the scanner and a backend server. All units communicate with the messages listed at the respective links.
* The scanner detects boarding passes automatically and reads the data. It only uses one message `request` towards the controller once it detects a boarding pass.
* The turnstile is locked by default. This means that its arms cannot move. With the message `unlock` the turnstile gets unlocked, so that a person can turn it and pass through. When a person passes through, the turnstile is turned once. As a confirmation that the person went through, the turnstile sends message `passed` back to the controller. Once turned, the turnstile will lock automatically again. In case no person passed through and the controller needs to lock the turnstile again, it can send the message `lock`.
* The backend can decide if a boarding pass is valid or not, using message `request`. 
  * If the boarding pass is valid (message `ok`), the turnstile gets unlocked, the green LED lights up and the passenger passes. A passing passenger is then reported to the backend via `boarded`. 
  * If the boarding pass is not valid (message `no`), the red LEDs light, and the turnstile stays locked. A message is shown to the display.
  * If the passenger does not pass the turnstile, the passenger is not reported as boarded to the backend.
* The turnstile is unlocked for 3 seconds. If the passenger does not react within that time and pass through the turnstile, it is locked again.
* The display shows the message “Scan your boarding pass” by default (message `scan`). When the passenger may pass, the display shows “Welcome aboard” (message `welcome`). If passing is denied, the display shows an error message “Please contact the counter for help” (message `help`).


**Delivery and Process:** Create a single Word document with all your diagrams and answers combined. 


## Task 1: Selected Scenarios
Design three separate sequence diagrams that include all components. These diagrams should document three different, selected scenarios, not the entire behavior possible. (Read the hints below before you start.)

* Diagram **Boarding Success** should document a successful boarding process. 
* Diagram **Valid Pass No Entry** should document a passenger with a valid boarding card that does not pass the turnstile. 
* Diagram **Invalid Pass No Entry** should document a passenger with an invalid boarding card.

**Hints:** 

* Sort the lifelines of the sequence diagrams in the order `scanner` - `controller` - `backend` - `turnstile` - `led` - `display`.
* Do not use any fragments in this task, just messages and lifelines.
* Use copy-paste to copy parts that are similar on the diagrams.



## Task 2: State Machine Design

Design a state machine for the controller based on the sequence diagrams. 

* Use the sequence diagrams as input.
* Focus on the lifeline for the controller.
* For eahc incoming message, declare a transition into a new state, and add as effects any messages the controller needs to send. 
* Add timers and corresponding actions and triggers as needed.

Some help for starting:

---
type: figure
source: figures/interactions/airport-help.png
---


## Task 2: Turnstile - Controller

We now want to consider the interaction between the turnstile and the controller.

* From the two diagrams **Boarding Success** and **Valid Pass No Entry**, extract only the lifelines for the controller and the turnstile, and the messages between these two, `unlock`, `lock`, and `passed`.
  * You get two partial diagrams. 
  * Place the controller to the left, the turnstile to the right. This makes it easier to compare solutions.
* Using a suitable combined fragment, create a **single** diagram that covers both cases. 

Your sequence diagrams contain a situation that is called **mixed initiative**.

* Create another sequence diagram that shows the situation.
* Explain the situation, that means, what is happening at the airport and with the passenger and all relevant components involved?
* Is this a severe problem? Also look at your state machine. 
* How can you fox this situation?


## Solution, Delivery and Reflection

* The example solution is [here](files/airport-system-solution.pdf).
* Of course, don't look at it before you created your own solution.
* Add a new section *Reflection* to your document and compare your solution.
  * Is there any significant difference?
* Deliver your final document on Blackboard.



# Feedback on T1

Via MS Teams you will receive all feedback documents from the others to your delivery T1. 
Work through all of them and update your original T1.

* You will resubmit most of T1 in T3.
* You may adjust it to follow any changes in you project.



# Checklist

 

### Blackboard

- Deliver the reflection over your solutions in comparison to the ones provided.

### MS Teams

- Ask for feedback in general
- Report any errors with the provided solution
- Discuss, with me or other teams

### Team Reflection for This Unit 

* Add another section to the team reflection document, just like every week. 

### Individual Reflection

* Fill out the <a href="https://forms.office.com/Pages/ResponsePage.aspx?id=cgahCS-CZ0SluluzdZZ8BSxiepoCd7lKk70IThBWqdJUQUQxNEVLOTBZMDZGNkJBM1Y2NjZCTzhWSi4u" class="arrow">individual reflection survey</a>.
* Copy the answers into a document that you maintain on your own.
* Add any additional observations to your reflection diary.