# State Machines


## Kitchen Timer

You should build the state machine for the following device:

---
type: youtube
video: Gnjg16f6DhY
---

It's a kitchen timer. It has 4 LEDs and a button. When the button is pressed, the first LED is switched on, and the plug provides electricity, for instance for a coffee machine. After 15 minutes, the LED is switched off and the plug is turned off. Whenever the button is pressed when an LED is already on, the next LED is switched on and time timer is set to 30, 45, or 60 minutes, respectively. If all LEDs are on, and the button is pressed, all LEDs and the plug are switched off.

You can ignore that the LED of the segment that is currently active is blinking, just assume it lights all the time.

Use the following actions:

* `start_timer('t', x min)` This starts a timer with name `t`. The second argument is the time, given as seconds. If a timer is already active, the timer is simply restarted with the new, updated timeout. 
* `stop_timer('t')`. Stops a timer. If no such timer exists or has already timed out, nothing happens.
* `set_leds(1, 0, 0, 0)`. Control all of the four LEDs at the same time. `1` means on, `0` means off. Here, the first LED is switched on, the others are off.
* `set_power(True)` switches the power on (True) or off (False)

You can assume that whenever the button is pressed, the state machine will receive a signal with the name `switch`.

1. Use individual time so that everyone can sketch a proposal on paper.
2. Compare your solutions in your team, and discuss any alternatives.
3. Build a complete suggestion in draw.io.
4. Do a peer review between teams: 

* Team **7** reviews the diagram of Team **10**.
* Team **8** reviews the diagram of Team **11**.
* Team **9** reviews the diagram of Team **12**.
* Team **10** reviews the diagram of Team **13**.
* Team **11** reviews the diagram of Team **14**.
* Team **12** reviews the diagram of Team **15**.
* Team **13** reviews the diagram of Team **16**.
* Team **14** reviews the diagram of Team **17**.
* Team **15** reviews the diagram of Team **18**.
* Team **16** reviews the diagram of Team **21**.
* Team **17** reviews the diagram of Team **7**.
* Team **18** reviews the diagram of Team **8**.
* Team **21** reviews the diagram of Team **9**.

Comments by adding UML note elements, and use the following colors:

* **red** for errors where the state machine does not work or is clearly violating the desired behavior.
* **yellow** for ambiguous cases.
* **green** for general comments or recommendations or questions.

5. Receive the reviewed state machine, store a version of it in PDF.
6. Have a look at an <a href="https://www.iik.ntnu.no/ttm4115/lectures/lecture-4/solution-for-kitchen-timer/" rel="noopener" target="_blank">example solution</a>, and figure out if there any meaningful differences. Describe differences and how your state machine can be matched with the given one. This reflection should be ca. half a page, or more if necessary.
7. Reflect over the process. What did you observe while creating the state machines? This is a reflection, you can address everything you find noteworthy. Use another half page ore more for this reflection.


You should now have three PDF pages:

* Your original state machine, including annotations by another team
* The improved state machine
* A short reflection.


## Car Lock

You should design the controller of a car lock. The controller is one of several modules in the car, which are connected via a CAN-bus, that sends signals between the modules. 
The controller gets input from the remote car key, which can send the commands *key_unlock* and *key_lock*. (The necessary encryption and security mechanisms are implemented between the car key and the key component, but not detailed here.) The controller send the signals *unlock* and *lock* to the lock component. It can also detect if the car door was opened or closed, via the signals *door_opened* and *door_closed*. Below is a diagram that illustrates all components and the CAN bus. 


<div class="mxgraph" style="max-width:100%;border:1px solid transparent;" data-mxgraph="{&quot;highlight&quot;:&quot;#0000ff&quot;,&quot;lightbox&quot;:false,&quot;nav&quot;:true,&quot;resize&quot;:true,&quot;toolbar&quot;:&quot;zoom&quot;,&quot;edit&quot;:&quot;_blank&quot;,&quot;url&quot;:&quot;https://drive.google.com/uc?id=1ZX0ZxYLXXpE4ZLAdk7D39M1mdFLEcA7T&amp;export=download&quot;}"></div>
<script type="text/javascript" src="https://www.draw.io/embed2.js?&fetch=https%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1ZX0ZxYLXXpE4ZLAdk7D39M1mdFLEcA7T%26export%3Ddownload"></script>


The following are the functional requirements for the controller:

- When the button *Unlock* is pressed, the door is unlocked.
- When the button *Lock* is pressed, the door is locked.
- Assume that the controller starts in a state where the door is closed and the lock is locked.  

The following signals are sent between the components via the CAN-bus:

- From Remote Key Controller to Car Lock Controller: `key_unlock` `key_lock`
- From Car Lock Controller to Door Controller: `unlock` `lock`
- From Door Controller to Car Lock Controller: `door_opened` `door_closed`

To send a signal, use method `send_signal('...')` with the signal name as argument. 
To react on the reception of a signal, simply write that signals as the trigger of a transition.

Design a state machine in draw.io for the Car Lock Controller that keeps track of the state of the door and the lock, and that implements the functional requirements from above.

Now, add the following functional requirement and create another version of the state machine. (Edit as a copy of the sheet.)

- If a door is unlocked but not opened, it is locked again after 60 seconds.


This time, we do not do a peer review, but you can get an example solution from the blackboard in front. Again, you should produce 3 PDFs. 1 with the first solution, then one with the second solution. Add a page of reflection as before, when you compare with the example solution. Also, apply corrections to your solution.

## The Headphone Story

This is an additional task if we have time left. 


You work as a summer intern at a computer company during the spring of 2007. You get the task to develop a controller for a mysterious remote control for some headphone stuff or so. Everyone is busy. A product manager drops by, and tells you:

    “The controller should translate button clicks into specific commands, depending on how often the user clicks. A single click should generate signal ’switch’. I think they use that for switching between playing and pausing. A double click should send signal ’next’. And if the user clicks three times in a row they need signal ’back’. That’s all I know. I have to go. Oh... the guys from the X-department gave me a diagram how it should be integrated. Here.” 

<img src="https://www.iik.ntnu.no/ttm4115/wp-content/uploads/2018/02/Screen-Shot-2018-02-12-at-10.14.53-1024x270.png" alt="" width="750" height="198" class="alignnone size-large wp-image-398" />

You are confused, but you manage to produce a decent state machine.

Create the state machine. You probably need some individual focus time to try it out on a piece of paper before you sketch a solution in Draw.io.

## Today's Delivery

Merge all PDFs into a single document and deliver on Blackboard, once per team.