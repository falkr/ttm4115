# Advanced Queue Semantics

In the following, we want to consider more detailed cases of event handling. 
If you have understood everything above, then these should be okay to understand too. 
If you feel that the basic state machines are still a but unfamiliar and you need to get used to, then don't worry too much about the details below. We will come back to them at a later point too.


### Discarding Events

As described above, when an event arrives in the input queue, it is consumed by the state machine by executing whatever transition is triggered by that event from the current state.
But what if the current state does not say anything about the incoming event?

When the state machine is in a state that does not declare a transition that is triggered by the event at the head of the queue, the event is taken from the queue and **discarded**, that means thrown away.

---
type: figure
source: figures/discard.png
caption: "An illustration how a message is discarded. In the current state `s1`, an arriving message `b` is discarded because `s1` does not handle it."
---

Look at the situation above. Assume that the state machine is currently in state `s1`.
When message *b* arrives, it is not consumed, since state `s1` only has a transition with a trigger *a*, so the state machine only waits for *a*. Message *b* is therefore discarded as soon as it arrives during state *s1*. Note that it is discarded even if it is consumed by the later state *s2*, which is not the current state.



### Deferring Events

What if you design a state machine, and know that two events (`A` and `B`) can arrive in any order, but you can only handle event `A` _after_ you have received event `B`. (For instance because what to do with `A` depends on the content of `B`.)
For this case, you can **defer** an event in some states. 

A state can defer an event by naming it inside the state body like a transition, but following the keyword `/defer`.
When a deferred event is at the head of the event queue, the state machine will act like it is not there, and process the first event that is not deferred.
Once the state machine switches into its next state, the previously deferred event is not ignored anymore (unless also the next state defers it).
 
---
type: figure
source: figures/defer.jpg
caption: "State `s1` _defers_ event `A` so that it is stored in the queue until after the arrival of event `B`."
---

### Summary of Queue Semantics

Many of the semantics we have learned now are about how the input queue of the machine is handled. 
We can summarize them with the following points:

* Messages arriving at the input of the state machine are placed **at the end** of the queue.
* Time events are placed at the **front of the queue** when the corresponding timer expires, so that timers can be handled as close to their actual expiration as possible.
* States can defer events, in which case they are only regarded when the state machine switches into a new state.
* Events that are not consumed or deferred are simply discarded, that means thrown away.



These were most of the thing you will need to know about state machines, and you are good to go for the test. For your next team activity, you will create state machines. 
You can already now read about some tips to create state machines. Read on if you have some energy left.

---
type: nav
prev: ["State Machine Semantics", "preparation-3.html"]
next: ["Creating State Machines", "preparation-5.html"]
---