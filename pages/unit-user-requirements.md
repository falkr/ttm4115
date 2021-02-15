# User Requirements

This week we are getting started with the semester project by working on the user requirements and outlining some use cases. 

It is probably a weak point in the course that you not only specify and implement the system, but are also responsible to come up with the requirements for the system.
There is no real customer that you can interview, and that can tell you in the end if your system satisfies their requirements or not. 
(We could fill an entire course with just the user requirements.)
We need to keep that in mind. 
The goal is hence to come up with a sensible set of good use cases that we take as input for the subsequent specification and implementation process. 

We guide the design of these use cases using a partial Vision-and-Scope document.



# Discuss the Semester Project

We provided you with a [partial and vague outline of the semester project](deliveries-project.html).
It is vague because it should allow you to adjust the system idea with your own ideas and plans. 
Defining the detailed requirements is part of the task. 

Have a short round where each of you explains their understanding of the system, and make a list of good ideas. For example: 

* Do you want the system to focus on a specific domain?
* Are there some functions you want to focus on?
* Are there some specific ideas you want to try?

This is an open-ended task, so make sure to conclude the discussion after some maximum time. (Like 20 minutes maximum.)


# Partial Vision and Scope Document

Based on your idea, create a preliminary Vision and Scope Document. 
The entire document should be short and concise, probably only about two to three pages. 
Capture the following sections:

* **Background:** A better name for this section is probably **"The Problem"**, because it needs to introduce why the system is actually needed. 
It provides information about the context of the system to make the vision more understandable and motivate it.
  * It is important that this part focuses on the context of the system, the environment, the problem and **not** the system itself.
  * Simply said, which problem does the system  solve for someone?
  * See also Compendium, Vision and Scope Document, p.576, 1.1
* **Vision Statement:** This is the most important item. 
Formulate a vision for your system that will guide your development, and explain the system also to others.
  * This may be hard to write down in a first attempt. Make some sketches, and be satisfied with an initial version.
  * See Compendium, Vision and Scope Document, p.577, 1.5
* **Objectives:** Try to formulate specific goals that the system should achieve, and that are somehow measurable. 
This should guide the technical development, and contribute to achieve the vision.
  * See Compendium, Vision and Scope Document, p.576, 1.3
* **Stakeholders:** Describe briefly the stakeholders that are important for the system. What is important to them? 
  * See Compendium, Vision and Scope Document, p.579, 3.1
* **Risks:** Describe briefly the main risks relevant for the system. Which are they, how can they be handled or reduced? 
  * See Compendium, Vision and Scope Document, p.577, 1.6


This task kicks off your work with the semester project, but is open-ended in the sense that you will probably not come up with the final document in this session. **Write down any questions you have for the session on Friday.** 
Based on the coarse idea of the system you will describe a set of use cases in the following. 

:delivery: You don't need to deliver this document this week, as it will be part of the delivery for the semester project. Create a folder in your own Team channel where you store all semester project related documents. You can also create a private team for that, where only you can access the documents. 



# What are Good Use Cases?

You have now already learned a lot about use cases and seen some examples, and know which goal we have when designing use cases. So what are the characteristics of **good** use cases?

### Step 1: Individual Work

As always, have an individual round first:

* Use 3 to 5 minutes of silence where each of you thinks about what are characteristics of a good use case. 
  - Each one should come up with about 3 to 5 such suggestions.
  - Each one prepares a ranked list, with the most important quality of a use case at the top.
  - Try to be compact, either a word or a short phrase for each characteristic.

### Step 2: Teamwork

Now combine your work together:

* Take rounds where each of you takes their top choice, and compile a complete list of attributes. 
  - Take rounds until you have listed all characteristics. 
  - Eliminate or rephrase similar characteristics as you go, to remove making the same point several times.
* Discuss and select the **three most important** characteristics. 
  - Mark the them with a star, or highlight them in yellow.

:delivery: Deliver your solution in the Teams folder for this unit. Use filename `ttm4115-use-case-qualities-Team-XX.docx`




# Use Case Levels

Recall the different levels of use cases from the preparation, where we assigned use cases to different levels on a horizon:

<div class="mxgraph" style="max-width:100%;border:1px solid transparent;" data-mxgraph="{&quot;highlight&quot;:&quot;#0000ff&quot;,&quot;nav&quot;:true,&quot;resize&quot;:true,&quot;toolbar&quot;:&quot;zoom layers lightbox&quot;,&quot;edit&quot;:&quot;_blank&quot;,&quot;url&quot;:&quot;https://drive.google.com/uc?id=1Q3F2M-akRFF_G0HIhx5faG2iu6gjRWkg&amp;export=download&quot;}"></div>
<script type="text/javascript" src="https://www.draw.io/embed2.js?&fetch=https%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1Q3F2M-akRFF_G0HIhx5faG2iu6gjRWkg%26export%3Ddownload"></script>

In the document above, you see a number of use cases lined up at the sea-level, but many of them belong either to a higher or a lower level. 
In case you have troubles with the document, here is a list of all the use cases it lists:

* Log into system
* Hit tab key
* Register a new customer
* Get paid for a car accident
* Buy a book
* Provide students loans. 

As you can see, these use cases do not relate to the same system. Use some fantasy to think about the systems around them, most should be obvious.
Your task is to assign these use cases to the level where they fit best. The exercise has the main intention to make you familiar with the use case levels, before we apply this kind of thinking on your semester project.


* Make a **copy** of the diagram. [Here is the direct link to it.](https://drive.google.com/file/d/1Q3F2M-akRFF_G0HIhx5faG2iu6gjRWkg/view?usp=sharing)
* Move the use cases up and down, and discuss them. 
  * Argue why they should be on a certain level. 
  * Compare the use cases with each other, and see if the level also fits relative to each other. 
* Once you are happy with the level of all use cases, [fill out the quiz (once per team.)](https://forms.office.com/Pages/ResponsePage.aspx?id=cgahCS-CZ0SluluzdZZ8BSxiepoCd7lKk70IThBWqdJUMk1CS1gxMDhIVEtZS1pFMEJGSkRTWjBVNC4u)
* See if you agree with the answers.



# Use Cases for Your Project

Turn your attention now to your semester project. 

For your project delivery, you should focus on **three** use cases **at the sea-level**. As you have seen above, these are the use cases most important to get right. The ones above provide direction and connect to your system's goals and purpose, but are more abstract. The ones below sea-level provide too much detail, but may be valuable when implemeting the system. 

* Make a copy of the [use case level document](https://drive.google.com/file/d/1Q3F2M-akRFF_G0HIhx5faG2iu6gjRWkg/view?usp=sharing), and start filling it with some use cases for your system.
* Be critical so that you capture the most important three use cases at the sea-level of your system. 
  * Look at higher-level ones, how they can be decomposed into sea-level use cases.
  * Look at lower-level ones to see if they can be aggregates into sea-level ones.
  * Ignore clam-level use cases.
* Store a screenshot of your results for your T1 delivery.

As an example, look at the use cases below I sketched for one of the many toilet paper ordering systems. My focus is at the sea-level, where I added two and think about a third one. I added a few use cases at the fish, kite, and cloud level, and connected the use cases with some arrows to show their dependencies. Try to follow the same strategy for your use cases. 

---
type: figure
source: figures/use-cases/toilet-paper.png
---


# Team Reflection for This Unit 

* Add another section to the team reflection document, just like last week.
* How did the roles work today? 


# Individual Reflection

* Fill out the <a href="https://forms.office.com/Pages/ResponsePage.aspx?id=cgahCS-CZ0SluluzdZZ8BSxiepoCd7lKk70IThBWqdJUQUQxNEVLOTBZMDZGNkJBM1Y2NjZCTzhWSi4u" class="arrow">individual reflection survey</a>.
* Copy the answers into a document that you maintain on your own.
* Add any additional observations to your reflection diary.