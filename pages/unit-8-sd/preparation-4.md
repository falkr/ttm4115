# Implied Scenarios

With the sequence diagrams, we describe scenarios, that means, specific
and selected examples of the system interactions. Some diagrams cover
several scenarios. In most cases, a specification (a set of diagrams)
does not document *all* possible scenarios. This is because it is often
not practical to write down all scenarios, and especially when sketching
a system it may not be relevant to think about all scenarios right at
the beginning.

Once a system specification gets more mature, you need to also develop
an understanding how the system handles scenarios that your
specification does not explicitly document yet. These scenarios often
exist because reality is more complicated than an idealized interaction.

Of course, you could just not care and leave the choice about details to
the developer who implements the system. In fact, this is what often
happens. However, this is not what you want. This may cause bugs in the
system, cost a lot of time of fixing afterwards and in general leads to
surprises later on. (And if there is one thing we want to prevent, it is
*surprises*.)

## Message Loss

Communication protocols provide different guarantees to the application
regarding the delivery of messages. However, even the most sophisticated
protocol cannot prevent that a communication link is failing and never
recovers. In these cases, the protocol cannot "hide" the problem from
the application, and the application itself needs to handle the
situation. The scenario *Lossy\_1* for instance also implies scenario
*Lossy\_2*, i.e., that the message is not received. The loss of a
message is written with a big cross.

---
type: figure
source: figures/lossy-12.png
---

So, whenever there is a diagram in which a message is sent, we should
check what would happen if this message got lost. Here are some possible
alternatives:

-   The application is fine even if message `A` is lost. This can be the
    case, for instance, if message `A` is one (of many) messages of the
    same type that are sent periodically, and where it does not matter
    if some of them get lost. A sensor that repeatedly sends some
    measurements is a typical example. (It may be, however, important
    that the sensor message *eventually* is sent, i.e., not all of them
    are lost.

-   The most common solution is to use acknowledgment messages. This is
    illustrated in *Lossy\_3*. In case message `A` is lost, `Y` does not
    send an acknowledgement. This is detected by `X` indirectly, through
    the expiration of a timer. We show the timer here as a message of
    `X` to itself.

---
type: figure
source: figures/lossy-3.png
---

## Non-Causal Orderings

The diagram below shows an interaction between parts in a movie ticket
system. At the end of the purchase process, the terminal sends a *pay*
message to the payment component. The payment component then forwards
*pay\_ok* to the ticket printer. The terminal sends the movie selection
to the printer. The printer then prints the tickets. We ignore the case
that the payment fails.

---
type: figure
source: figures/ex-6.png
---

This specification has a trouble spot. The diagram indicates that the
*movie* message is received after the *pay\_ok* message. In a real
system, we often have little control on the delay of message transfer.
The payment process within *payment* may also take different amounts of
time. In a real system it is therefore difficult, undesirable or even
impossible to ensure that *movie* is received after *pay\_ok*.

One way to fix this situation is with a co-region as in *Movie Fix 1*,
to express explicitly that the two signals can arrive at the printer in
any order. The implementation of the printer must then take care of
this.

Another way is to change the way the entire interaction works. Instead
of sending *pay\_ok* to the printer, the payment component may also
return it to the terminal, shown in *Movie Fix 2*. The terminal can then
send the *movie* message after the payment is confirmed. In this case,
we may also use a synchronous message for the payment as in *Movie Fix
2x*, since the terminal may anyways be waiting for it and not do
anything else.

Note: The original sequence diagram is not wrong, but depending on the
context, type of system and the subsequent development process and
implementation, the non-causal ordering of the events may be a source of
trouble.

---
type: figure
source: figures/ex-7.png
---


## Mixed Initiatives

Consider the following alarm system. A sensor may detect an alarm and
send message *alarm* to a subscriber. The subscriber may then confirm
the alarm via message *confirm*. The alarm can also be stopped by the
sensor via *stop*. This is shown in the two diagrams below.

---
type: figure
source: figures/ex-8.png
---

The two different scenarios seem pretty straight-forward. However, these
two scenarios imply a third one: What should happen, if the alarm is
stopped by the sensor, but the subscriber confirms it, right before it
receives the stop message? We call this scenario a *mixed initiative*,
since it involves a situation where several participants may take
initiative and send a message. This situation may seem like a rare
coincidence, but it is only a matter of time and you will observe this
situation. We can illustrate it in another diagram:

---
type: figure
source: figures/ex-9.png
---

So what to do about this? If you only provide the sequence diagrams
above, it is not clear how an implementation should respond in this
situation, i.e., when an alarm is both confirmed and canceled. In this
case, you need to find out what the application should do. Depending on
what kind of alarm it is, the stopping may overrule the confirmation, or
vice versa. The diagram *Confirm and Stop* shows one way to address the
mixed initiative, using a simple comment.

---
type: figure
source: figures/ex-91.png
---


---
type: nav
prev: ["Event Orderings and Semantics", "preparation-3.html"]
next: ["Epilogue: The Value of Sequence Diagrams", "preparation-5.html"]
---
