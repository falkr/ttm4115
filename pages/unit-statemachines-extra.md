# Car Lock

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

# The Headphone Story

This is an additional task if we have time left. 


You work as a summer intern at a computer company during the spring of 2007. You get the task to develop a controller for a mysterious remote control for some headphone stuff or so. Everyone is busy. A product manager drops by, and tells you:

    “The controller should translate button clicks into specific commands, depending on how often the user clicks. A single click should generate signal ’switch’. I think they use that for switching between playing and pausing. A double click should send signal ’next’. And if the user clicks three times in a row they need signal ’back’. That’s all I know. I have to go. Oh... the guys from the X-department gave me a diagram how it should be integrated. Here.” 

<img src="https://www.iik.ntnu.no/ttm4115/wp-content/uploads/2018/02/Screen-Shot-2018-02-12-at-10.14.53-1024x270.png" alt="" width="750" height="198" class="alignnone size-large wp-image-398" />

You are confused, but you manage to produce a decent state machine.

Create the state machine. You probably need some individual focus time to try it out on a piece of paper before you sketch a solution in Draw.io.