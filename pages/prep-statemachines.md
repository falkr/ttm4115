---
status: draft
---

# Welcome to Unit 4

In the previous units, we learned how to capture and understand our user's requirements for a system, and structure what the system should provide to its users in the form of use cases. We have also learned how to use deployment diagrams to reveal already some details about the structure of the system. This week, we start with the specification of how the system actually works. This will be more technical and on a more detailed level as before. 


## Hello, State Machines!

In the following, we are going to learn the concept of state machines. Besides sequence diagrams and activities, state machines are one of the fundamental ways to describe behavior. They are used to specify communication protocols, logic in embedded systems, and in general behavior where events need to be coordinated in a complex way. Here is an intuitive example of a sketch for a state machine that illustrates in a compact way how a traffic light works:

---
type: figure
source: figures/statemachines/state-machines-traffic-light.jpg
caption: "A state machine describing the sequence of phases in a traffic light."
---

Another example is the specification of the TCP protocol, also using a state machine:

![]()


---
type: figure
source: figures/statemachines/state-machines-tcp.gif
caption: "The TCP protocol uses state machines to describe parts of its behavior."
---


A bit of a problem with state machines is that developers often only understand they they should have used a state machine for a problem *after* it is too late, and they already spent much effort on trying to solve a task in other ways. Have a look at this blog post from developer Alan Skorkin, [Why Developers Never Use State Machines][skorkin]. 

[skorkin]: https://www.skorks.com/2011/09/why-developers-never-use-state-machines/

Another example is the construction of the kernel for GNU. There you have a situation where the behavior quickly became very complex. Have a look at the interview with Richard Stallman:  

---
type: youtube
video: jw8K460vx1c
start: 1525
caption: "Interview with Richard Stallman, from  0:25:25 until 0:26:30, from the movie _Revolution OS_. You may watch the entire movie later." 
---

**"It took us years to get the thing to work."**  What we are saying is not that Richard should "just have used state machines." The answer is probably not that easy. What we are saying is that there are problems that can quickly grow very complex, and state machines offer a way to handle complexity that plays out very beneficial in some situations. With state machines, you can structure complex behavior such that:

- It is easy to debug and understand precisely what happened.
- Only one thing happens at a time. (Resp. you have detailed control over concurrency.)
- Given the complexity thay handle, state machines are easy to understand.





## Mandatory Preparation

In the compendium, read **Chapter 5: The State Machine Diagram**. (Page numbers from the original book are 85 to 106)


Hints: 

* Pay especially attention to the examples that the book presents and explains in detail, especially figures 5.3, 5.5, 5.6, 5.7, 5.8, 5.9, 5.11, 5.13, 5.14, 5.20. Try to understand the mechanics of state machines by going through these examples. You should be able to tell, for instance, what happens in a state machine when a given event happens.

* We won't ask specific questions about the history state (5.5.4) or submachines (5.5.2), but they may be helpful as context.



## A Physical State Machine Model

*The following is a description of state machines using a physical model. Have a look at its description, it may help you to understand the book chapter above.*

State machines are implemented in code and executed by a computer. To understand how a state machine works, you can also think of it as a physical machine, which executes almost like a mechanical clockwork.

The figure below illustrates such a machine. Feel free to ignore this illustration if it does not work for you, or if your mental model of a state machine is different. Also, note that this is an illustration, explaining some aspects of state machines while leaving out others.

---
type: figure
source: figures/statemachines/state-machine-machine.svg
caption: "An imaginary machine that illustrates how a state machine works."
---


The state machine has an input queue for signals sent by other parts of the system. These may be other state machines within the same computing node, state machines from other nodes, or other parts of programs that send messages.

All messages arrive and are sorted in a first-in, first-out (or short FIFO) order. (Timers are an exception to this.)

The state machine also manages a set of timers. The state machine starts these timers as part of its behaviour. When a timer expires, it places an event in the same event queue as the one for incoming messages. Timer expiration events are placed at the front of the queue, since an event from a timer should be processed as close to its actual expiration time as possible.

The state machine interprets the state machine diagram. The diagram can be represented as a state-transition table. In this table is written down in which current state of the state machine an event has which effect. The effect means the behaviour the state machine is executing. This includes to start and stop timers, run operations, and moving the state machine into its next state. The state machine can also keep track of other data by using variables. (This is why this type of state machine is also called *extended* finite state machine.)


## Queue Semantics

To understand how a state machine executes, it is important to understand how the input queue works. 

* Messages arriving at the input of the state machine are placed at the
end of the queue.
* Time events are placed at the front of the queue when the corresponding timer expires.
* States can defer events.
* Events that are not consumed or deferred are simply discarded.


**Discarding events:** When the state machine is in a state that does not declare a transition that is triggered by the event at the head of the queue, the event is taken from the queue and discarded, that means thrown away.

<img src="https://www.iik.ntnu.no/ttm4115/wp-content/uploads/2018/02/Screen-Shot-2018-02-06-at-10.32.12-1024x365.png" alt="" width="750" height="267" class="alignnone size-large wp-image-358" />

In state *s1* above, for instance, *b* is not consumed. (The state machine is waiting for message *a*.) It is therefore discarded as soon as it arrives during state *s1*. Note that it is discarded even if it is consumed by the later state *s2*, which is not the current state.

<img src="https://www.iik.ntnu.no/ttm4115/wp-content/uploads/2018/02/Screen-Shot-2018-02-06-at-10.32.18.png" alt="" width="958" height="302" class="alignnone size-full wp-image-359" />

**Deferring events:** A state can *defer* some events. This means that the deferred events are ignored in this state. When a deferred event is at the head of the event queue, the state machine will act like it is not there, and process the first event that is not deferred. Once the state machine switches into its next state, the previously deferred event is not ignored anymore (unless also the next state defers it). Deferred events are written within the state symbol following the keyword */defer*.