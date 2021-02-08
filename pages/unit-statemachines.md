# State Machines

Until now, you have learned about all the features that we need for state machines, but you have not yet created one on your own.


Revisit the [preparation material on how to create state machines](unit-statemachines-creation.html).
Assign one in the group who guides a brief summary through the points, and discuss any things that you may need clarification for. 

This is just to ensure that you remember the proceedings as you will need them today.


# Errors in State Machines

Before we create our own state machines, let's criticize some others and find mistakes in them first.

For each of the state machines, formulate a short sentence (or two) that describe what's wrong with them. 
Collect these sentences in a text document while you work, then submit them as a form given below.

 
### State Machine 1

---
type: figure
source: figures/statemachines/stm-e-1.png
caption: ""
---


### State Machine 2

---
type: figure
source: figures/statemachines/stm-e-2.png
caption: ""
---


### State Machine 3

---
type: figure
source: figures/statemachines/stm-e-3.png
caption: ""
---


### State Machine 4

---
type: figure
source: figures/statemachines/stm-e-4.png
caption: ""
---


### State Machine 5

---
type: figure
source: figures/statemachines/stm-e-5.png
caption: ""
---


### State Machine 6

---
type: figure
source: figures/statemachines/stm-e-6.png
caption: ""
---

:delivery: Delivery your diagnostics on the state machines in [this form](https://forms.office.com/Pages/ResponsePage.aspx?id=cgahCS-CZ0SluluzdZZ8BSxiepoCd7lKk70IThBWqdJUQ0ZTRFVIODBUNlNTRzFEUU02VUJVMTc0Mi4u).


# Getting Started: Bus Stop

You should build the state machine for a bus stop signal light. 
It is intended for bus stops where busses only halt when there are passengers, and which are located so that it is difficult for a bus driver to see passengers when they approach. It may also be that they need to get off a larger road, but can stay on that road if there are not passengers. The solution is a signal light that passengers can activate at the buss top and which is better visible for the approaching bus. 


---
type: figure
source: figures/statemachines/bus-1.png
caption: "Sketch of the bus stop."
---


Here are the detailed functional requirements:

* Passengers waiting at the bus stop can press a button, upon which the signal lamp switches on.
* The bus driver can switch the light off via a radio message `bus`.
* The light switches off 10 minutes after it was pressed, even if no bus came.
* If a passenger presses the button and the light is already on, it stays on, but the 10 minutes timer starts again with 10 minutes.

Use the following elements:

* actions `lamp_on()`, `lamp_off()`, `start_timer('t', 600000)`
* triggers `button`, `bus`, `t`
* states `on`, `off`, and an initial state

You can ignore for now that the system may be switched off, so you need no final state.

## Create a State Machine, Individually


* Use some time to find a first solution each one on your own. 
* Use pencil and paper.


## Create a State Machine, Together

* Compare your solutions, one at a time.
* Starting again with an empty screen, whiteboard or paper, design the state machine once again, together.
* Play through this simple scenario, and correct your state machine if necessary.


## Solution

* Once you are happy with your solution, have a look at [my solution](files/bus-stop.pdf).
* Compare the solutions in detail. (If you find that my solution has any flaws, please discuss on MS Teams!)
* Prepare a document where you show your solution and mine side-by-side, and compare.
* Reflect about your process towards this machine.
  * What did you get right immediately? 
  * What was difficult? 
  * Were there misunderstandings?
  
:delivery: Store your document from above in the Teams folder for this unit. Use filname `ttm4115-2020-bus-stop-team-XX.docx`


# Kitchen Timer

You should build the state machine for the following device:

---
type: youtube
video: Gnjg16f6DhY
---

It's a kitchen timer. It has 4 LEDs and a button. When the button is pressed, the first LED is switched on, and the plug provides electricity, for instance for a coffee machine. After 15 minutes, the LED is switched off and the plug is turned off. Whenever the button is pressed when an LED is already on, the next LED is switched on and time timer is set to 30, 45, or 60 minutes, respectively. If all LEDs are on, and the button is pressed, all LEDs and the plug are switched off.

You can ignore that the LED of the segment that is currently active is blinking, just assume it lights all the time.

Use the following actions:

* `start_timer('t',... )` This starts a timer with name `t`. The second argument is the time, given as seconds. If a timer is already active, the timer is simply restarted with the new, updated timeout. 
* `stop_timer('t')`. Stops a timer. If no such timer exists or has already timed out, nothing happens.
* `set_leds(1, 0, 0, 0)`. Control all of the four LEDs at the same time. `1` means on, `0` means off. Here, the first LED is switched on, the others are off.
* `set_power(True)` switches the power on (True) or off (False)

You can assume that whenever the button is pressed, the state machine will receive a signal with the name `switch`.

## Create a State Machine, Individually


* Use some time to find a first solution each one on your own. 
* Use pencil and paper.


## Create a State Machine, Together

* Compare your solutions, one at a time.
* Starting again with an empty screen, whiteboard or paper, design the state machine once again, together.
* Play through this simple scenario, and correct your state machine if necessary.


## Solution

* Once you are happy with your solution, have a look at [my solution](files/kitchen-timer.pdf).
* Compare the solutions in detail.
* If you find that my solution has any flaws, please discuss on MS Teams!
* Prepare a document where you show your solution and mine side-by-side, and compare.
* Reflect about your process towards this machine. 
  * What did you get right immediately? 
  * What was difficult? 
  * Were there misunderstandings?


:delivery: Store your document from above in the Teams folder for this unit. Use filename `ttm4115-2020-kitchen-timer-team-XX.docx`.


# Team Reflection for This Unit 

* Add another section to the team reflection document, just like last week.
* How did the roles work today? 


# Individual Reflection

* Fill out the <a href="https://forms.office.com/Pages/ResponsePage.aspx?id=cgahCS-CZ0SluluzdZZ8BSxiepoCd7lKk70IThBWqdJUQUQxNEVLOTBZMDZGNkJBM1Y2NjZCTzhWSi4u" class="arrow">individual reflection survey</a>.
* Copy the answers into a document that you maintain on your own.
* Add any additional observations to your reflection diary.