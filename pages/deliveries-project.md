# Semester Project


In contrast to previous years, we constrain the type of system that you should build. The reason for this is that many students find it hard to come up with a good idea that isn't too similar to what we already had. In addition, this has the benefit that you are more focused and interested when providing feedback to the other teams, as they try to solve a similar problem. 

We sill expect that there is enough variation in your priorization, selection, interpretation and implementation of the system functionality that you all end up with different systems. 


# 2022: Digital-Physical Interaction for Distributed Teams

The base idea is to create a communication device for members of a development team or office that is distributed in at least 2 office locations, together with persons working from home.

How can we enable informal, "accidental" conversations, like when you meet someone in the kitchen in a physical office. How could such interactions also span across several locations?

For example: 

* A screen, camera, speakers, microphone, movement detection besides the coffee machine.
* How can a worker in a home office detect when someone is brewing a coffee and join in?
* Can there be a fun game to play across the offices? 

There is an element of uncertainty in this system, which is important as we learn how to manage this uncertainty. 

This base idea leaves some room for suggestions and ideas on your side. 

We will refine this idea together and incorporate your ideas over time.



# Some Guidelines

There are some recommendations or guidelines to ensure that you build a system in a way where you can apply the learning outcomes of the units in the course as directly as possible. Don't see them as tight constraints that need to be followed precisely, but as rules of thumb that should guide you.

In general, we recommend that some parts of your system are implemented in Python using STMPY state machines, follow the component architecture we have studied in the last unit, and communicate via MQTT. 

The motivation is that you can 

* describe the software in meaningful ways using the diagram types we have learned
* develop state machines that work on synchronization of concurrency via signals
* develop a set of loosely coupled components
* overall, apply the learning goals of the different units

Of course you can incorporate other components written in other languages and using other frameworks, for instance to get specific functions implemented that are easier in other languages than Python. 

User interfaces only have to be practical so that you can show how the system should work. Python is not very good at coding user interfaces, and this course is not about user interfaces either. So don't worry too much about them. 


