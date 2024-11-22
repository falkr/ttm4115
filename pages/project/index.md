# Semester Project

During the semester you will work on a system specification in your development teams. 
This work is the basis for the entire course, and it will be delivered in several versions so you get feedback on it also during the semester.

## Properties of the System

* You will need some form of user interface, since we need to cover the interactions with the users of the system. At the same time, this is not a course about how to program the details of user interfaces. We will hence find some way of making prototypical user interfaces. What we would like to emphasize, however, is that the user interface is responsive, and react to the interactions with the other system components.

* Managing interactions between components through the handling of stateful behavior and communication is at the core of this course. We hence want to see that the system consists of several components that interact with each other, and that these interactions work well.

* The system should be able to handle several events coming in any order as they may occur in reality. For instance, several users may issue commands that could be in conflict with each other, and the system should handle this well.


# Theme

Each year we select a theme for the semester project. There are two reasons for this: 

1. It should make it easier for you to converge towards a solution; instead of beginning to sketch very different ideas in the beginning you will probably much quicker agree on a common idea.
2. It will make it more interesting for you to see the solutions of other teams. During the semester you will give feedback to another team, and this is of course simpler if they work on a system that you already have some ideas about.

The theme should guide what you are considering, but we don't want that all systems will work in the same way, focus on the same features and are too similar to each other. 


### Theme for 2025: Handling of E-Scooters

---
type: figure
source: figures/e-scooter.jpg
text: Picture taken by Thomas Wolter is free to use according to the [Pixabay Content License](https://pixabay.com/service/license-summary/).
---

Shared electric kick scooters, better known as e-scooters, are a popular means of transport for last-mile mobility in urban areas. Using them can be fun, and their use is environment-friendly, since they are electrically operated without direct CO<sub>2</sub> emission. On the other side, they have a tendency to block walkways and may produce [visual pollution](https://en.wikipedia.org/wiki/Visual_pollution). 

Usually they are operated with the help of mobile phone apps, that allow their owners to localize e-scooters in their vicinity, to unlock them, and to pay. You should create a system for handling e-scooters, that adds some new interesting features for the use of e-scooters. For that, you should program components for the e-scooters and the apps. Depending on your ideas, you may also add more components. 

You will receive two Raspberry Pi computers, one of them with a [Sense HAT](https://www.raspberrypi.com/documentation/accessories/sense-hat.html). With these you could simulate for instance the control unit of an e-scooter.

Feel free to discuss the outline of the semester project on the discussion forum, we will refine the guidelines as we learn more together.


Apart from being related to handling of e-scooters, you have a lot of freedom. In the following, you will find some ideas for possible new features:

* Could there be possibilities to reserve an e-scooter and, if yes, in which way?
* In contrast to shared bicycles, e-scooters have no fixed place, where they are stored, and where they can be recharged. Can that be changed by, for instance, placing charging stations ahead of popular places like university lecture halls? Users that place the e-scooters at such loading stations, could be rewarded by lower fees.
* Has your team any ideas to reduce the problem with blocking walkways or causing visual pollution?




[Theme 2023](theme-2023.html)


# Hints

### Managing Uncertainty is part of your job

Sooner or later you will feel that our system constraints are ambiguous or vague. We don't do this on purpose---we really try to answer any of your questions as good as we can. But this is in fact a similar situation that you will experience in a real system development scenario: With many things that are new, there is an element of uncertainty. Managing such uncertainty is one of the key skills you should acquire in this course, and the tools we give you are intended to reduce uncertainty step by step.


### You are the Product Owner

Often the product owner is external to the development team or company, and is available to answer questions about the product to be built. (That doesn't mean that they are always right or have all the answers.)

In this course, there is no external product owner. We could have designed the course like this, but this adds additional complexity and would have come at a cost of reducing some of the other learning goals. 

You are therefore also the product owner, and have to decide which product to build and how it should work at the same time you are developing it. That's not a problem, but we have to be aware of this.

Since you are the product owner, we choose a domain where you have some insights, so that you can answer the most important questions on your own and judge which features to implement and how they make sense.



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
  
