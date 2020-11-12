# Car Lock

You should design the controller of a car lock. The controller is one of several modules in the car, which are connected via a CAN-bus, that sends signals between the modules. 
The controller gets input from the remote car key, which can send the commands *key_unlock* and *key_lock*. (The necessary encryption and security mechanisms are implemented between the car key and the key component, but not detailed here.) The controller send the signals *unlock* and *lock* to the lock component. It can also detect if the car door was opened or closed, via the signals *door_opened* and *door_closed*. Below is a diagram that illustrates all components and the CAN bus. 


<div class="mxgraph" style="max-width:100%;border:1px solid transparent;" data-mxgraph="{&quot;highlight&quot;:&quot;#0000ff&quot;,&quot;lightbox&quot;:false,&quot;nav&quot;:true,&quot;resize&quot;:true,&quot;toolbar&quot;:&quot;zoom&quot;,&quot;edit&quot;:&quot;_blank&quot;,&quot;url&quot;:&quot;https://drive.google.com/uc?id=1ZX0ZxYLXXpE4ZLAdk7D39M1mdFLEcA7T&amp;export=download&quot;}"></div>
<script type="text/javascript" src="https://www.draw.io/embed2.js?&fetch=https%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1ZX0ZxYLXXpE4ZLAdk7D39M1mdFLEcA7T%26export%3Ddownload"></script>


The following are the functional requirements for the controller:

- **R1.1:** When the button *Unlock* is pressed, the door is unlocked.
- **R1.2:** When the button *Lock* is pressed, the door is locked.
- Assume that the controller starts in a state where the door is closed and the lock is locked.  

The following signals are sent between the components via the CAN-bus:

- From Remote Key Controller to Car Lock Controller: `key_unlock` `key_lock`
- From Car Lock Controller to Door Controller: `unlock` `lock`
- From Door Controller to Car Lock Controller: `door_opened` `door_closed`

To send a signal, use method `send_signal('...')` with the signal name as argument. 
To react on the reception of a signal, simply write that signals as the trigger of a transition.

Design a state machine in draw.io for the Car Lock Controller that keeps track of the state of the door and the lock, and that implements the functional requirements from above.

---
type: figure
source: figures/statemachines/car-lock-1.png
---



Now, add the following functional requirement and create another version of the state machine. (Edit as a copy of the sheet.)

- **R2.1:** If a door is unlocked but not opened, it is locked again after 60 seconds.

This implies that we add a timer to the state machine with a transition reacting to it once the timer expires. We do this in the state machine below. It is important that we use the exit/stop_timer(t) action to state `closed_unlocked`, to prevent a sequence where the user quikcly opens the door, then closes it again, then the timer (which was not stopped) to expire and the lock to close. This is prevented by explicitly stopping the timer.

---
type: figure
source: figures/statemachines/car-lock-2.png
---

Another solution adds an additional state, here called `coled_unlocked_timed`. This state covers explicitly that the timer is active, and we leave this state either byt the timer expiration or by opening the door. 

---
type: figure
source: figures/statemachines/car-lock-3.png
---