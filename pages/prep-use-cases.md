# Use Cases

During requirements engineering, we are focused on the needs of the users and the stakeholders of the systems. We don't yet think of how to implement or how to structure the system. Maybe some of the structure is indirectly obvious because we know users will use a mobile phone or a PC, and that there is a data center involved. But during requirements engineering we do not yet decompose the system into more fine-grained components. 

Before we think about the system, we first structure its functionality as seen from the outside, and for that we describe the system's **use cases**. This forces us to ask questions like _"Which are the (five) most important jobs a user wants to accomplish?"_ We say _five_ here because that gives you an idea for the number of high-level use cases that we should think of in the first place. (There may be more finer-grained use cases.)

Having good use cases is often undervalued. But it is exactly in this phase where clever thinking and a thorough process pays off manyfold. Use cases are at a level where we work so specific that we can find problems with our understanding of the user requirements, and we can identify inconsistencies within the requirements. We start to get an idea how much effort the system will probably take, although that requires some experience. We can also understand dead ends, i.e., solutions that will probably not work, or some that won't add any value to the system or product. 


I have an example: As you know, we write the RATs for this course on paper, and I made a Python program to read in the codes you submit and then generate all feedback from it. This is a very small software project, but even here use cases pay off. Before I started implementing the first version of the program, I made the following diagram:

---
type: figure
source: figures/use-cases/teampy.jpg
caption: "A simple sketch of the use cases for the system to read in RAT results. Even though this was a simple diagram, it saved a lot of work as it revealed one of the use cases to be unnecessary."
---

**This is a use case diagram.** It describes the main functions a system provides to its environment, depicted as actors. Here, the main actors are _teacher_ and _student_. As you can see, there is a use case _Enter Results_. Originally, I thought this could be done by students on their own, using a web formular. However, as you know, during the RAT you are not allowed to use your phone, so how should we have done this? Also, how to ensure that everyone is reporting their own, correct results? Just by thinking at this level of use cases I then decided that this was a task for the teaching assistant, and changed the use case.

You may think now that you could have done this also without use cases, just by thinking about the system. But this is exactly what we are talking about: The use cases make your thinking on a high level about the system visible to your development team, your boss, your customers, and yourself. This is why use cases are important, and why hopping over them can cost you time and money. 


## Learning Goals




Goals: The learning goals specific for this week are the following:

- Appreciate the value of thinking in terms of use cases.
- Creating use case overview diagrams and use case tables.
- Sorting use cases according to their level of detail.
- Breaking use cases into finer ones, or aggregating them into more high-level ones.




## Preparation

**Read carefully through the following book chapter from the compendium:**

* Software Requirements, Third Edition Karl Wiegers and Joy Beatty, 2013, Microsoft Press. (In the Digital Compendium, via Blackboard) **Chapter 8: Understanding User Requirements.** pp 143-165 (22 pages). Introduces use cases, beyond the notation. This chapter also explains user stories as an alternative to use cases. (We will stick to use cases.)

## Optional Preparation

Have a look at the following videos that show how to create deployment diagrams.

---
type: youtube
video: tLJXJLfLCCM
---

---
type: youtube
video: _JCsqdNf8bA
---

---
type: youtube
video: SmcBTsPsbIY
---

---
type: youtube
video: q7O2EAZ_s7M
---

---
type: youtube
video: bL_Bl_Xl7wQ
---

---
type: youtube
video: x5LkaZlLT28
---

---
type: youtube
video: gYmOzpU7DDI
---