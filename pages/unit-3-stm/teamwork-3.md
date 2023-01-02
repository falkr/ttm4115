# Kitchen Timer

You should build the state machine for the following device:

---
type: youtube
video: Gnjg16f6DhY
---

It's a kitchen timer. It has 4 LEDs and a button. When the button is pressed, the first LED is switched on, and the plug provides electricity, for instance for a coffee machine. After 15 minutes, the LED is switched off and the plug is turned off. Whenever the button is pressed when an LED is already on, the next LED is switched on and time timer is set to 30, 45, or 60 minutes, respectively. If all LEDs are on, and the button is pressed, all LEDs and the plug are switched off. You can ignore that the LED of the segment that is currently active is blinking, just assume it lights all the time.


<iframe src="https://ntnu.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=9bfe4a96-4f9a-44ac-879a-af79009d2a1a&autoplay=false&offerviewer=true&showtitle=false&showbrand=false&captions=false&interactivity=all" height="540" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay"></iframe>


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

