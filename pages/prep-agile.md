---
status: draft
---

# Agile vs. Architecture



Goals: 

## Learning Goals

- Have fun
- More Goals
- even more goals






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

**But this is not how real projects work!** In reality, the following will happen:

* When making the use cases, more questions come up that you have to clarify with the customer, and you need to refine the requirements. 
* When making the sequence diagrams, you may also need to go back and reconsider use cases and requirements. 
* You may also wonder if a specific operation is possible at all, and may want to implement a simple prototype first, i.e., invest some time to test out some code. 
* ...

The above model is also called "Waterfall Model", because the different stages follow each other. 
(The original image was also moving downwards, and looked like a waterfall.) 
Have a look into the following presentation: (The video is not part of the RAT.)



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

This image is based on one from an article called "Get Ready for Agile Methods, With Care." To the left are methods that require a lot of planning, like waterfall.  To the right, we have methods that require less (or no) planning, like just plain "hacking". Somewhere in between, we have methods such as milestone-driven approaches, extreme programming, and **agile methods**. Those last ones have received a lot of attention in industry, and it is very likely that you will work with an agile method in the future. 

To popularize agile development, some engineers gathered and prepared the [Agile Manifesto](https://www.agilealliance.org/agile101/the-agile-manifesto/). This document explains some of the principles. It is short to read, and most developers have at some point heard about it.

A word of caution: There are a lot of people that have very strong opinions about development methods. This is understandable, since development methods can have a lot of influence on a project's success. What is important in the course in the following is that you develop an understanding for the different forces between the need for planning and the ability to adapt to changes. For a project to be successful, you will need both planning and agility. In fact, all agile methods include some amount of planning. So it is important that you look at the arguments, observe, make your own conclusions and don't stop thinking. (Which is probably a generally good advice for many things in life.)


## Mandatory Preparation

One popular agile method is *Scrum*. It is very likely that you will be invited to a course in Scrum when you start working. 
As part of the preparation, you should read through the Scrum Guide:

* [The Scrum Guide](http://www.scrumguides.org/docs/scrumguide/v1/scrum-guide-us.pdf) by Ken Schwaber and Jeff Sutherland



## Optional Material:

* Explaining Agile - Martin Fowler and Neil Ford at USI


---
type: youtube
video: GE6lbPLEAzc
---

