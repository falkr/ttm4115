# Unit 9: Components

In this unit, you will learn about software components. We will first look at the motivation, that means, why we need to think about components at all. The reason is mainly that we need to partition the implementation of our system into smaller parts for many reasons, and components are these parts. We will then look into different aspects of modularity, how components can communicate with each other, and we will introduce the concept of services, before we look which support we get for components in the real world.

This was a difficult learning unit to prepare! The reason is that we have to integrate three different perspectives at the same time:
  
- The real world of software development is complex and difficult to grasp, many concepts are not uniquely defined and there are many products. When you start learning in this world, you will likely be overwhelmed and confused. 
- Only making theoretical treatment of the principles is boring and useless, and you may wonder why the concepts are relevant at all. 
- Finally, only focusing on programming matters will be too detailed and too incidental, not providing you a good picture of the real value of components. 

So in the following, we have a combination of these perspectives. Some theoretical treatment with the principles, some view into the real world, and some programming in the week ahead. 

But don't get me wrong: Components are a fascinating subject! Components do not only couple together a lot of the properties of a system, both at runtime and after deployment. They are the main subjects when we talk about software architecture, which is a changing field with different trends, ideas, fashions, faiths and also fantasies. When you learn, such discussions can be interesting but also confusing. What I want to achieve in the following unit is that you get the basic ideas and develop the skills to think about modularity in a system so you can adapt to whichever specific component framework and architectural style is used in your job. Here are, as always, the learning :goals:

## Learning Goals


:goals: The learning goals specific for this week are the following:

- Be aware of the aspects when decomposing a system into parts.
- Understand and apply the mechanisms of services.
- Decompose the semester project into components.



So far, we have created single state machines, and just connected them with MQTT to let them communicate, but we didn't build anything with them yet. 
This week we want to combine several concepts to build a more complete software component. 

---
type: figure
source: figures/meme.jpg
---



## Preparation

Go through the following preparation material before we meet in class:


---
type: link
title: 'Components'
icon: journal-bookmark-fill
link: preparation-1.html
---


---
type: link
title: 'Implementing Components'
icon: journal-bookmark-fill
link: preparation-2.html
---


## Teamwork on Monday

Go through the following activities with your team:


---
type: link
title: 'Timer Module for a Voice Assistant: The Spaghetti Timer'
icon: people-fill
link: teamwork-1.html
---


---
ref: ../reflection.ref
---
