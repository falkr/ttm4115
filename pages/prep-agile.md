# Agile vs. Architecture




So far, we haven't spent a lot of time to talk about our development process. We have spent most effort into: 

* understanding how to figure out the user requirements so that we built the right system
* understanding the intricacies with communication and interactions
* the documentation of system architecture
* the specification of use cases
* the detailed specification of interactions with sequence diagrams
* the detailed specification of component behavior using state machines
* and finally how to code state machines

When we talk about *development process* we mean how we should organize our work around these documents:
When to create which document, how they depend on each other, and how to organize our team around these.
Initially, we could follow this scheme:

---
type: figure
source: https://www.iik.ntnu.no/ttm4115/wp-content/uploads/2018/03/method-1024x315.jpg
caption:
  "An idealized method that connects the requirements to the final system given in code."
--- 

We start by analyzing the user requirements, and develop the use cases based on them. Then, we look at the necessary system components and interactions between them. Once the interactions look okay, we develop the detailed state machines for the individual components, and then implement the state machines in code. The above model is also called "Waterfall Model", because the different stages follow each other.

**But this is not how real projects work!** In reality, the following will happen:

* When making the use cases, more questions come up that you have to clarify with the customer, and you need to refine the requirements. 
* When making the sequence diagrams, you may also need to go back and reconsider use cases and requirements. 
* You may also wonder if a specific operation is possible at all, and may want to implement a simple prototype first, i.e., invest some time to test out some code. 



Have a look into the following presentation: (The details of the video are not part of the RAT.)



---
type: youtube
video: NP9AIUT9nos
start: 525
caption: 
  "Talk at a developer conference about the waterfall model and its problems. "
---


We can look at the waterfall model as one side in a spectrum of methods:

---
type: figure
source: figures/agile-spectrum.png
caption:
  "**The spectrum of development methods:**  
  Aligned on an axis that goes from a waterfall model with lots of planning
  on the left towards pure hacking without planning to the right."
---

This image is based on one from an article called "Get Ready for Agile Methods, With Care." To the left are methods that require a lot of **planning**, like waterfall.  To the right, we have methods that require less (or no) planning, like just plain "hacking." Somewhere in between, we have methods such as milestone-driven approaches, extreme programming, and **agile methods**. Those last ones have received a lot of attention in industry, and it is very likely that you will work with an agile method in the future. 

To popularize agile development, some engineers gathered and prepared the [Agile Manifesto](https://www.agilealliance.org/agile101/the-agile-manifesto/). This document explains some of the principles. It is short to read, and most developers have at some point heard about it.

A word of caution: There are a lot of people that have very strong opinions about development methods. This is understandable, since development methods can have a lot of influence on a project's success, but touch on complex issues and are often discussed based on anecdotes and in general a bit "fluffy".  What is important in the course in the following is that you develop an understanding for the different forces between the need for planning and the ability to adapt to changes. For a project to be successful, you will need both planning and agility. In fact, all agile methods include some amount of planning. So it is important that you look at the arguments, observe, make your own conclusions and don't stop thinking. (Which is probably a generally good advice for many things in life.)


## Mandatory Preparation

One popular agile method is *Scrum*. It is very likely that you will be invited to a course in Scrum when you start working. 
As part of the preparation, you should read through the Scrum Guide:

* [The Scrum Guide](https://www.scrumguides.org/docs/scrumguide/v2017/2017-Scrum-Guide-US.pdf#zoom=100) by Ken Schwaber and Jeff Sutherland (An earlier version of this page linked to a previous version of the guide, but there are only minor adjustments.)



## Optional Material


The guide above may be a bit dry to read, but contains all the essential information about SCRUM. I hence recommend that you find some more videos or other material that help you to get a more vivid picture and some illustrations, and watch them in addition to reading the guide. I'll leave the choice of videos to yourself, but give you two as a starting point below. Also, if you find one that you like, tell me and the others on MS Teams!


### Video: Scrum in under 5 minutes

---
type: youtube
video: 2Vt7Ik8Ublw
---


### Video: Explaining Agile - Martin Fowler and Neil Ford at USI

---
type: youtube
video: GE6lbPLEAzc
---

