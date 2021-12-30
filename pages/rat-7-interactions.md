## Question 1

:rat:What do sequence diagrams cover?

1. They cover selected interaction scenarios in a system.
2. They cover all interactions in a system.
3. They cover selected interaction scenarios of a single system component.
4. They cover the behavior of a system.

## Question 2

:rat:Look for the figure with the arrows.
Which of the arrows represent which type of message?

1. synchronous (1), return (2), asynchronous (3)
2. asynchronous (1), return (2), synchronous (3)
3. synchronous (1), asynchronous (2), return (3)
4. asynchronous (1), synchronous (2), return (3)

---
type: figure
source: figures/rats/arrows.png 
---


## Question 3

:rat:Sequence diagrams can define **ref** fragments.

1. The **ref** fragment can only be used with object-oriented languages.
2. The **ref** fragment defines a reference that all other diagrams must follow.
3. The **ref** fragment helps to reuse diagrams and manage large ones.
4. The **ref** fragment is resolved at runtime.

## Question 4

:rat:Which lines in sequence diagrams do never cross each other?

1. Only nested messages can cross each other.
2. Lifelines don't cross lifelines.
3. A message does not cross another message.
4. A message does not cross a lifeline.

## Question 5

:rat:Creation and destruction of lifelines:

1. **create** and **destroy** can be used independently.
2. Lifelines created with a **create** also have to be destroyed with a **destroy**.
3. Only lifelines created dynamically with a **create** can be destroyed dynamically with a **destroy**.
4. All other statements are wrong.

## Question 6

:rat:Which of the following alternatives contain only valid fragment types?

1. alt, break, ref, neg, opt, switch
2. alt, assert, break, opt, ref
3. alt, break, do, loop, opt, ref
4. alt, assert, ref, break, neg, opt, switch

## Question 7

:rat:The following answer alternatives show short traces of events. Which alternative shows traces that are **not** described by diagram X?

1. !C,?C and ?C,!D
2. !D,?D and ?C,!D
3. ?A,?B and ?D,?E
4. ?B,!C and !E,?E

---
type: figure
source: figures/rats/sdx.png 
---


## Question 8

:rat:Have a look at diagram Y. How can we call this scenario?

1. mixed-initiative
2. non-causal ordering
3. sequential ordering
4. parallel messages

---
type: figure
source: figures/rats/sdy.png 
---


## Question 9

:rat:Have a look at diagram Z. How can we call this scenario?

1. non-causal ordering
2. mixed-initiative
3. sequential ordering
4. parallel messages

---
type: figure
source: figures/rats/sdz.png 
---

## Question 10

:rat:Why is it important to consider also implied scenarios?

1. They can reveal bugs or trouble spots in the system.
2. Because all implied scenarios need to be resolved.
3. Implied scenario are a sure sign of a bug or trouble spot.
4. Implied scenarios require a fix of the original specification.
