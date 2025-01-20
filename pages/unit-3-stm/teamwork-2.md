# Getting Started: Bus Stop

You should build the state machine for a bus stop signal light. 
It is intended for bus stops where busses only halt when there are passengers, and which are located so that it is difficult for a bus driver to see passengers when they approach. It may also be that they need to get off a larger road, but can stay on that road if there are not passengers. The solution is a signal light that passengers can activate at the bus top and which is better visible for the approaching bus. 


---
type: figure
source: figures/bus-1.png
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

* Once you are happy with your solution, have a look at [our solution](files/bus-stop.pdf).
* Compare the solutions in detail. (If you find that my solution has any flaws, please discuss on MS Teams!)
* Prepare a document where you show your solution and mine side-by-side, and compare.
* Reflect about your process towards this machine.
  * What did you get right immediately? 
  * What was difficult? 
  * Were there misunderstandings?
  
:delivery: Store your document from above in the Teams folder for this unit. Use filname `ttm4115-bus-stop-team-XX.docx`


---
type: nav
next: ["Kitchen Timer", "teamwork-3.html"]
---
