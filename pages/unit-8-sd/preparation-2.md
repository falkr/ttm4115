# Combined Fragments

Combined fragments allow you to express more behavioral details in
compact ways. Some of them look very much like programming statements,
which makes them intuitive to understand. However, it can also be a trap
to think of them too much as control statements, since they do not
handle operations, but entire scenarios. Rather, think of them as a way
to characterize interactions.

## alt

The **alt** fragment specifies alternative scenarios. For instance, a
component may ask for access, and the access right may be granted or
not. We can show this in the sequence diagram *Access* below:

---
type: figure
source: figures/alt.png
---

The different compartments are alternatives to each other. There may be
any number of compartments, not only two. They are separated by a dashed
line. To describe in more detail, when a specific alternative is chosen,
the compartments can have an optional guard. This guard may refer to
some text or a variable.

*Access* almost looks like an if-statement. And in fact, the access
control component may internally execute an if-statement. But the alt
fragment can be even more abstract, since it can describe alternative
scenarios, independent of how they are realized. The specification of
*Timer* is therefore equally valid Do you see the difference? The
example shows that a timer can be started and then either be aborted or
it times out. This time the scenario is more subtle, the alternative is
not determined by a single component, but the overall timing of the
interaction.

## opt

The **opt** fragment contains behavior that can happen or not. It is
similar to an alt fragment with two compartments, one of which is empty.
Like with the alt fragment, the opt fragment can have a guard.

---
type: figure
source: figures/opt-1.png
---

## loop

With the **loop** fragment, you can express that a behavior is executed
repeatedly. Below, you see the specification of an alarm clock with a
snooze function. Within the loop fragment, you see an alt fragment, with
different branches of the user either snoozing or stopping the alarm. In
case of stopping the alarm, there is also a break fragment. This signals
the escape out of the loop. You may also leave unspecified how often the
loop is executed.

---
type: figure
source: figures/loop-1.png
---

## assert and neg

In some cases, you want to assert that a certain interaction must
exactly occur as specified. For that, you can place it into an
**assert** fragment. The other way round, you may want to specify
*negative* behavior, i.e., behavior that must not happen. Such behavior
can be places in a **neg** fragment.

---
type: figure
source: figures/assert-neg.png
---

## ref

With a **ref** fragment, you can refer from one sequence diagram to
another one. This makes diagrams easier to handle. It also allows to
reuse a sequence diagram and apply it at several places.

In the example below, we have another definition of the snooze feature
of an alarm clock. Here, we used the ref fragment that refers to the
sequence diagram itself and by that introduces some recursion. (The blue
arrow is just an illustration.) This is probably not a good example in
general, but it should work. Note that the outermost frame, labeled
"**sd** alarm" encapsulates the entire sequence diagram.

---
type: figure
source: figures/ref-1.png
---

## Time Constraints

In some cases, you want to add time constraints to a specification, to
show *when* an interaction occurs, or how long specific parts of it may
or should take. Have a look at the example below:

---
type: figure
source: figures/timing.png
caption: "From the UML@Class book."
---

It shows that the newsletter is sent at 12:00. Five time units later,
the student receives the confirmation. The diagram also specifies that
the signal *inform* must be received within two hours.

---
type: nav
prev: ["Intuition on Sequence Diagrams", "preparation-1.html"]
next: ["Event Orderings and Semantics", "preparation-3.html"]
---
