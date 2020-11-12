

# Agile vs. Architecture

No matter which development method you will use for a project, there is one very important questions, that all of them need to address: **How much should we plan ahead?**

Remember the diagram from the preparation, that listed some development methods based on the amount of planning:

---
type: figure
source: figures/agile-spectrum.png
caption:
  "**The spectrum of development methods:**  
  Aligned on an axis that goes from a waterfall model with lots of planning
  on the left towards pure hacking without planning to the right."
---


Think of your own semester project: 

* On the one side, planning is necessary when you want to work together, so that you can deliver on time, decide when to meet, when you want to reach which milestones. It is obvious that some degree of planning is necessary for any project.
* On the other side, planning can also be hard. You don't know how something works out before you have done it. There are a lot of unknowns ahead, and sometimes you just need to try something out.

So how much *should* you plan? 


## Discussion

Before we continue, let's have a discussion on the challenges and benefits with planning:

* Use 3 minutes and think individually about the tradeoff between planning ahead and making plan as you go ahead.
* Discuss your findings around the table. 
* Write down concrete challenges you face in your particular project you have observed. What can you do to mitigate these problems.




Unfortunately, there is no simple answer. Instead, managing a development project means to constantly think about adequate planning. It means to review progress, routines and watch out for warning signs. What helps is to be aware of the different forces that are at work during development, forces that can either require to plan more or to plan less. 

The figure below illustrates the forces (in red) that influence a development team, and the strategies (in blue) that can be applied to mitigate them:

---
type: figure
source: figures/agile-forces.png
caption: A development faces forces (in red), and should react with strategies (in blue).
---

The forces and strategies were identified by Waterman, Noble and Allan in their article _How much up Front? A Grounded Theory of Agile Architecture_. The following are the more detailed descriptions of the **forces** (paraphrased from the original article):

* **F1 (REQUIREMENTS INSTABILITY)** refers to the effect that unstable requirements have on up-front planning. Being able to respond to changing requirements is one of the underlying values of the Agile Manifesto and is central to our conceptual definition of agility.
* **F2 (TECHNICAL RISK)** describes the effect that exposure to potentially negative outcome has on a team’s up-front effort. Risk is caused by complex architecture. 
* **F3 (EARLY VALUE)** refers to a customer’s need to gain value from a system or product being built (rather than simply provide feedback) before all functionality has been implemented, perhaps in the form of a minimum viable product.
* **F4 (TEAM CULTURE)** describes the effect that a team’s culture has on its agility and the effort it puts into up-front planning. A culture that is people-focused and collaborative is a very important factor in a team’s ability to communicate.
* **F5 (CUSTOMER AGILITY)** describes the culture of the customer’s organisation and the huge impact that it has on the amount of up-front architecture design a team does. A customer must have an agile culture that is similar to the team’s culture, whether the team is in-house or an ISV (independent software vendor), for the team to be truly agile. A highly-agile team will not fit in well with a heavyweight process-oriented organisation that prefers planning and formal communication.
* **F6 (EXPERIENCE)** describes the impact that an experienced architect’s tacit knowledge and implicit decision-making ability has on the time that an agile team spends on up-front design. Experienced architects have breadth of knowledge; they are more likely to be aware of suitable options for implementing a solution and better understand what will work and what will not.

And here are the detailed **strategies**, which help to mitigate the challenges caused by the forces:

* A team's ability to use **S1 (RESPOND TO CHANGE)** is directly related to how agile it is. S1 increases the architecture’s agility by increasing its modifiability and its tolerance of change, and allows the team to ensure the architecture continuously represents the best solution to the problem as it evolves.
* **S2 (ADDRESS RISK)** reduces the impact of risk before it causes problems, and is usually done up-front, particularly for risk relating to system-wide decisions (for example, risk in selecting the technology stack or top-level styles). Using S2, a team designs the architecture in sufficient detail that it is comfortable that it is actually possible to build the system with a satisfactory level of risk.
* **S3 (EMERGENT ARCHITECTURE)** produces an architecture in which the team makes only the minimum architecture decisions up-front, such as selecting the technology stack and the highest level architectural styles and patterns. When using S3, the team only considers the requirements that are immediately needed for its design, ignoring even high- level requirements that are to be implemented in the longer term. 
* **S4 (BIG DESIGN UP-FRONT)** requires that the team acquires a full set of requirements and completes a full architecture design before development starts. There are no emergent design decisions, although the architecture may evolve during development. 
* **S5 (USE FRAMEWORKS AND TEMPLATE ARCHITECTURES)** is the use of software frameworks, and template and reference architectures sourced from particular framework vendors for use with those frameworks. Frameworks … include default architectural patterns which constrain the systems to these patterns. S4 provides the benefit of standard solutions to standard problems, which means that software engineers do not need to make as many architectural decisions, and can greatly reduce the effort required to design a system and get it up and running. 


## Task

Make a copy of the diagram below, and move the forces on the right side to the right place.

<div class="mxgraph" style="max-width:100%;border:1px solid transparent;" data-mxgraph="{&quot;highlight&quot;:&quot;#0000ff&quot;,&quot;nav&quot;:true,&quot;resize&quot;:true,&quot;toolbar&quot;:&quot;zoom layers lightbox&quot;,&quot;edit&quot;:&quot;_blank&quot;,&quot;url&quot;:&quot;https://drive.google.com/uc?id=1hZdFV59lQ20oGVIzIQK5W0W4xcJzVLTL&amp;export=download&quot;}"></div>
<script type="text/javascript" src="https://www.draw.io/embed2.js?&fetch=https%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1hZdFV59lQ20oGVIzIQK5W0W4xcJzVLTL%26export%3Ddownload"></script>

Here is also a [link to the diagram](https://drive.google.com/file/d/1hZdFV59lQ20oGVIzIQK5W0W4xcJzVLTL/view?usp=sharing).

With some discussion you should be able to place all forces and strategies so that the entire diagram makes sense. These are the considerations you have to do in a development project!