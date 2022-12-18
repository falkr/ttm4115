# State Machine Semantics

## Traces

Once you get more experienced with state machines, you will be able to simulate them in your head, just by figuring out the sequences in which the different events may happen. 
Since at any time more than one event could happen, the same state machine could create many different sequences of events, also called **traces**. When you will design state machines, it means to get control over all of these traces, so that in the end, any possible behavior (that means, any possible trace of events) is okay for the system. State machines hence describe **complete behavior**. (We will later see how another diagram type, interactions, describe usually only partial behavior.) For state machines, this means that what they don't describe, they can't do. 

By looking at a state machine, we can write down possible sequences of events. Lets just write down **one** trace of events that can happen when we activate the spaghetti timer. We just write down the events regarding the main machine **Blinking 10 min Timer**, and do so by listing the sequence of all triggers and actions as they happen:

- initial transition
- message start received
- entry action `start(t1, 1000)` in state `active`
- entry action `send(on, blink)` in state `active`
- timer `t1` expires
- exit action `send(off, blink)` in state `active`
- entry action `start(t2, 3000)` in state `beeping`
- entry action `start_beep()`    in state `beeping`
- timer `t2` expires
- exit action `stop_beep()` in state `beeping`

Here there is actually only a single behavior, because we go through the states based on the timeouts of the two timers `t1` and `t2`. A more realistic timers would also describe behavior where we could abort it, which would be another trace. 


**Exercise:** Put your finger on the state machine **Blinking 10 min Timer** and follow through the trace above. Note that the event that timer `t1` expiration happens _before_ the exit action `send(off, blink)` in state `active` happens. This is because the timer expiration of `t1` _causes_ this transition and action. (Some students find that not intuitive, since the timer `t1` is graphically outside of the state, and somehow looks graphically to happen "later" in time.)



## State-Transition Tables

So far, we used diagrams to write down our state machine. 
Instead we can also use a table that lists all the transitions. 
This will be the basis for implementing state machines in Python.
There's not much more to say about this table, other than that it offers another way of looking at a state machine, and understand them systematically. 
Below you see again the state machine for the tunnel light, and the table that describes the same behavior. Check if you understand what each row means, and how it corresponds line by line to the diagram.

---
type: figure
source: figures/tunnel-2.svg
caption: "The state machine from the tunnel light."
--- 


---
type: table
class: table
caption: "A transition table with equivalent content."
---
{|
| Source State
| Trigger
| Actions
| Target State
|-
| initial
| -
| left_on()
| left
|-
| left
| t1
| left_off(); right_on()
| right
|-
| left
| off
| left_off()
| final
|-
| right
| t2
| right_off(); left_on()
| left
|-
| right
| off
| right_off()
| final
|}


## A Physical State Machine Model

We promised you another way to get an intuitive understanding of state machines.
To understand how a state machine works, you can also think of them as a physical machine, which executes almost like a mechanical clockwork.
The figure below illustrates such a machine. 

---
type: figure
source: figures/state-machine-machine.svg
caption: "An imaginary machine that illustrates how a state machine works."
---

The state machine has an input queue for messages sent by other parts of the system.
These may be other state machines within the same computing node, state machines from other nodes, or other parts of programs that send messages.

All messages arrive and are sorted in a first-in, first-out order, also called _FIFO_. 

The state machine also manages a set of timers.
The state machine starts these timers as part of its behaviour.
When a timer expires, it places an event in the same event queue as the one for incoming messages.
Timer expiration events are placed at the front of the queue, since an event from a timer should be processed as close to its actual expiration time as possible.

The state machine interprets the state machine diagram.
The diagram can be represented as a state-transition table, as we have seen above.
This table encodes in which current state of the state machine an event has which effect.
The effect means the behaviour the state machine is executing.
This includes to start and stop timers, run operations, and moving the state machine into its next state.
The state machine can also keep track of other data by using variables.
This is why this type of state machine is also called *extended* finite state machine.


---
type: nav
prev: ["State Machine Diagrams", "preparation-2.html"]
next: ["Advanced Queue Semantics", "preparation-4.html"]
---