# Semester Project

During the semester you will work on a system specification in your development teams. 
This work is the basis for the entire course, and it will be delivered in several versions so you get feedback on it also during the semester.


### Managing Uncertainty is part of your job

Sooner or later you will feel that our system constraints are ambiguous or vague. We don't do this on purpose---we really try to answer any of your questions as good as we can. But this is in fact a similar situation that you will experience in a real system development scenario: With many things that are new, there is an element of uncertainty. Managing such uncertainty is one of the key skills you should acquire in this course, and the tools we give you are intended to reduce uncertainty step by step.


### You are the Product Owner

Often the product owner is external to the development team or company, and is available to answer questions about the product to be built. (That doesn't mean that they are always right or have all the answers.)

In this course, there is no external product owner. We could have designed the course like this, but this adds additional complexity and would have come at a cost of reducing some of the other learning goals. 

You are therefore also the product owner, and have to decide which product to build and how it should work at the same time you are developing it. That's not a problem, but we have to be aware of this.

Since you are the product owner, we choose a domain where you have some insights, so that you can answer the most important questions on your own and judge which features to implement and how they make sense.


### Theme

Each year we select a theme for the semester project. There are two reasons for this: 

1. It should make it easier for you to converge towards a solution; instead of beginning to sketch very different ideas in the beginning you will probably much quicker agree on a common idea.
2. It will make it more interesting for you to see the solutions of other teams. During the semester you will give feedback to another team, and this is of course simpler if they work on a system that you already have some ideas about.


### Theme for 2023: Digital meets Physical Education

Imagine a university course that involves exercises in a lab, similar to what you are doing in the team activities on Monday afternoon. 

Can you build a system that makes communication within the lab easier? 

Here are some high-level ideas of functions:

- How can student assistants and teachers get a live overview over the progress of each team?
- How can we see which teams have missing students?
- Which tasks are done? Which tasks are difficult? Which teams are stuck at a certain task?
- How long does each task take, and can we collect historic information about task to estimate the remaining time in the lab?
- Can we track progress during the RATs?
- Managing breaks
- Can there be CTF-inspired "leader boards" that update?

The idea is that most students are physical on campus and in the classroom or lab, not a fully digital setting. But it can be interesting if the solution would allow to help remote students (sick or away for another reason) could more easily join.

The system should not replace a complete learning system, which are mostly about handling documents or providing material.    

You can use a Raspberry Pi with a SenseHAT as a hardware device, for instance to show the status at each table. If you have good ideas that require other hardware we can have a talk if we can incorporate them. 


# Deliveries

During the semester, you need to hand in the following deliveries: 

---
type: table
file: tables/deliveries.mw
class: table table-sm 
---


The deliveries contain the following elements:

---
type: table
file: tables/spec.mw
class: table table-sm
---


- Deliveries marked with {{:bi-circle-fill:}} *must* be included. 
- Deliveries marked with {{:bi-circle-half:}} *can* be included if they are updated, and you want provide them as context for the new parts.
- Deliveries marked with {{:bi-circle:}} are not part of the delivery, since we have not yet treated them in class when the delivery is due.

# Format and Template 


- All delivery documents must be in *PDF* format. 
- You can include diagrams and figures in landscape mode for entire pages. In this case, they need to be readable **from the right**. 
- Check which pattern for the filename we require. This makes file handling for us faster.
- The header on each page must contain your team number and the delivery name.
- For group deliveries, you team number (and name) must be in the header. The front page must list all members of the team that have contributed to the delivery.
- For individual deliveries, your name must be in the header.



# Questions and Answers

---
type: qna
q: Can we make changes between the different versions of the specifications?
---
Yes. It is natural that your understanding of the system evolves, so what you have submitted in version 1 can be updated for version 2 and then also the final version. In the end, only the final version counts.
  