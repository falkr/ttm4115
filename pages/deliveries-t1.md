# Delivery T1: Requirements

This delivery is a partial Vision and Scope document that focuses on why the system exists and what it should do, 
but without all detailed requirements listed. 

This delivery shows already a part of the system solution, by illustrating it with a deployment diagram.



## Grading

**Grading:** You don't receive a grade for this document directly. You will receive feedback on its content from other students, and will re-submit all content as part of the final submission. However, the better this initial submission is, the easier it is to receive valuable comments, and the easier it will be to create a very good final version. (So simply assume that already this version is graded.)

**Rejection:** Since this document is the basis for further work, we may reject it if it does not meet some criteria, both in form or content. You will then need to resubmit an improved version.


# Content

The delivery must contain the following sections:

## Requirements Part

### 1. Problem and Background
 
Provide a brief description of the problem you want to solve. It should provide the context so that the reader can understand your vision in the next section.

**Hints:**

* Length should be maximum half a page.
* Formulate the problem and background in complete sentences, not bullet points.
* Focus on the problem and add as much background as necessary for the reader to understand the problem.
* In this part you should not mention the system at all.


### 2. Vision	

Provide a vision for the system to build.
All team members should be aware of this vision and share it.
Be concise and specific.
Ideally, the vision connects the objectives with the problem description.
The vision provides some details about the system that explain in very coarse language how the system will tackle the problem.
It highlights what is new or special with the system.

**Hints:**

* Formulate the vision in complete sentences, not bullet points.
* The vision should be ca. ¼th of a page.


### 3. Objectives

State at least three objectives, but not much more than five. Objectives are goals that your system can achieve. They need to be specific, and they need to be verifiable. State the objective, and state how it can be verified.
Objectives do not yet explain how the system is implemented, but are oriented towards the users' domain.

**Hints:** 

* Describe the objectives, not the features of the system.
* Show the objectives as a list.


### 4. Stakeholders
	
Identify the main stakeholders in the system. Identify their values and interest. Present all in a table. 

**Hints:** 

* Expected length: half a page to a full page.
* Stakeholders are humans or organizations.


### Criteria for the Requirements Part

All sections in the requirement part are evaluated together with the following criteria:

---
type: table
file: files/rubrics/requirements.mw
class: rubric
caption: '<a href="learning-grading.html#grading-criteria">Read more about these criteria...</a>'
---

## Use Case Part




### 5. Use Case Sea-Level Hierarchy

This is not an official diagram type, but it turned out so useful for the development process that we decided to add it as part of the delivery.

Show at least three use cases at the sea level. Add relevant ones at the fish-level that support the sea-level use cases. Also, make sure to have at least one cloud-level use case and relevant ones at the kit level to connect cloud-level with sea-level. Make sure that the use cases are at the right level and relevant for the vision and objectives of the system.

<!--
* **Task:** Present a use case diagram that covers the major features of your system.
* **Evaluation:** Completeness, plausibility, correctness of syntax, layout, clarity.
* **Hints:** Present a use case diagram that covers the major features of your system. Most likely, the use case diagram will fit on a single A4 page in landscape orientation. This diagram can show more use cases than you will detail in the next task. **This diagram type is shown in the compendium, page 149.** 
-->

### 6. Use Cases in Table Form

Describe 3 use cases for the major features of your system. Choose use cases at the sea-level. Follow the table format proposed in the book and shown on page 150.

**Hints:** Most likely, each of the use cases will fit on a single page in portrait orientation. (So use about 3 pages in total.)


### Criteria for the Use Case Part

The main function of the use cases is to provide a clearer picture of the needed system functionality before anything is implemented. 
The value of this part hence is based on its usefulness for the upcoming process.

---
type: table
file: files/rubrics/usecases.mw
class: rubric
caption: '<a href="learning-grading.html#grading-criteria">Read more about these criteria...</a>'
---


## Architecture Part



### 7. Deployment Diagram

Present a first version of a deployment diagram of your system. Identify the main execution nodes of your system and how they are connected. Identify critical hardware components (even if you later chose to simulate them.) Identify communication protocols that you are already aware of, and identify execution environments.


**Hints:** Most likely, the deployment diagram will fit on a single A4 page in landscape orientation.


### Criteria for the Deployment Diagram


The deployment diagram is evaluated based on general criteria for diagrams.


---
type: table
file: files/rubrics/deployment.mw
class: rubric
caption: '<a href="learning-grading.html#grading-criteria">Read more about these criteria...</a>'
---


# Formatting Rules for Deliveries

* Start each section on a new page. 
* Make sure to include team name on each page, in the header or footer of the document.
* Filename: **ttm4115-2018-XX-team-YY.pdf**, where XX is the delivery, like `T1` and YY is your team number, for instance 01 or 13. Consistent file name makes it much easier for us to process all deliveries!
* Diagrams can be included in landscape format, but must be readable from the right. (That means, they must be readable when the page is turned 90 degrees clockwise.
