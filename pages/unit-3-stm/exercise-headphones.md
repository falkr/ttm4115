
# The Headphone Story

This is an additional task if we have time left. 


You work as a summer intern at a computer company during the spring of 2007. You get the task to develop a controller for a mysterious remote control for some headphone stuff or so. Everyone is busy. A product manager drops by, and tells you:

> "The controller should translate button clicks into specific commands, depending on how often the user clicks. A single click should generate signal ’switch’. I think they use that for switching between playing and pausing. A double click should send signal ’next’. And if the user clicks three times in a row they need signal ’back’. That’s all I know. I have to go. Oh... the guys from the X-department gave me a diagram how it should be integrated. Here.” 

---
type: figure
source: figures/headphones.png
---

You are confused, but manage to draw a sequence diagram onto the whiteboard. When the product manager comes again, you ask if it looks okay. The immediate answer is:

> "Sure. Build it!"

And the product manager is away again. You shout:

> "But wait.. there is one thing I need to know. How long... never mind."

But even without the answer, you create a state machine. 

After you created the state machine, an engineer from team X drops by.

> "Are you done with the design? I have bad news. We made some changes. We require not a single switch signal, but dedicated pause and play signals. Just assume that all music is paused when your controller is activated. You need to build it all again." 

---
type: figure
source: figures/headphones-2.png
---

That's tough. But you manage to build another state machine that solves the task. That's the story.


## Questions


1. Draw the sequence diagram that you sketched on the whiteboard.
2. Which information did you try to get from the product manager? 
3. Build the first state machine for the controller. 
4. What is the difference for the state machine of the controller because of the changes?
5. Draw a second state machine that uses the signals `pause` and `play` instead of `switch`. 
6. Looking at the new state machine and comparing it with the first one, why do you feel confident it is the proper solution?




# Solution

**Spoiler Alarm:** Only look at the solutions after you prepared your own solution, or you are really, _really_ stuck.


### Q1: Sequence Diagram


---
type: hint
title: Answer
image: figures/headphones-sd-1.png
---

### Q2: Info from Product Manager

---
type: hint
title: Answer
---
I don't know how much time must pass between two clicks so that they should count as two separate single clicks that trigger `switch` twice, in contrast to triggering only a single `next`. Similar for the timing between three clicks. 


### Q3: First State Machine

---
type: hint
title: Answer
image: figures/headphones-stm-1.png
---

### Q4: What is the difference in the new machine?

---
type: hint
title: Answer
---
The controller needs to know when to send signal `play` and when to send signal `pause`. With the hint from the engineer we know that the music is initially paused, so the first time we need to send a `play`. We then need to keep track of the current state of the music, which we do with a control state in the state machine.


### Q5: Second State Machine

---
type: hint
title: Answer
image: figures/headphones-stm-2.png
---

### Q6: Why are you confident?

---
type: hint
title: Answer
---
The new state machine has some symmetry, i.e., it has similar behavior for the pause and play states.


