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




## Theme for 2026: Drone-Based Package Delivery

---
type: figure
source: figures/drone.jpg
---

Drone-based package delivery is an emerging logistics solution designed to transport packages quickly and efficiently using autonomous or remotely controlled unmanned aerial vehicles (UAVs). This technology aims to reduce delivery time, traffic congestion, and environmental impact by leveraging aerial routes rather than traditional on the ground road networks. Equipped with sensors, GPS navigation, and smart routing algorithms, delivery drones can navigate complex environments, avoid obstacles, and land at designated delivery points. As the technology evolves, drone delivery systems are increasingly becoming a key feature of future urban and rural logistics infrastructures. 

You should create a system for handling drones used in package delivery scenarios, that provides some interesting features for the use of drones. For that, you should program components for the drone and the apps. Depending on your ideas, you may also add more components. 

You will receive two Raspberry Pi computers, one of them with a [Sense HAT](https://www.raspberrypi.com/documentation/accessories/sense-hat.html). With these you could simulate for instance the control unit of a drone. 

**Scope of your project:** you may ask how many features a project should realize. This of course depends heavily on the complexity of the particular features you are aiming to implement. However, if you manage to realize three to four [use cases at the sea level](https://ttm4115.iik.ntnu.no/unit-4-req/preparation-1.html), preferably those that have some logical relationships with each other, it should be fine. Feel free to discuss the outline of the semester project on the discussion forum, we will refine the guidelines as we learn more together. 

Apart from being related to handling of drones, you have a lot of freedom. In the following, you will find **some ideas for possible** new features: 

 

* **Real-time tracking and simulated telemetry**, showing drone position, speed, battery level, and estimated delivery time. 

* **Fleet management and drone assignment logic**, where the system selects the best drone based on location, load capacity, and battery status. 

* **Battery simulation and energy modeling**, including automated decisions for charging, landing in charging stations, or forced return. 

* **Delivery prioritization rules**, where urgent or high-value deliveries override default standard route for delivery. 

* **User notifications and communication flow**, informing customers about each delivery stage (takeoff, flying & real-time location, issue detected, delivered, etc.). 

 
We emphasize once again that the above features are **only examples** meant to illustrate the scope and possible direction of the project. You are encouraged to develop **your own ideas**, explore creative alternatives, and propose new features that align with your system concept or introduce novel features.  



[Theme 2025](theme-2025.html)


# Hints

## Managing Uncertainty is part of your job

Sooner or later you will feel that our system constraints are ambiguous or vague. We don't do this on purpose---we really try to answer any of your questions as good as we can. But this is in fact a similar situation that you will experience in a real system development scenario: With many things that are new, there is an element of uncertainty. Managing such uncertainty is one of the key skills you should acquire in this course, and the tools we give you are intended to reduce uncertainty step by step.


## You are the Product Owner

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
  
