# System Spec, Version 1

This delivery is a partial Vision and Scope document that focuses on why the system exists and what it should do, 
but without all detailed requirements listed. 
This delivery shows already a part of the system solution, by illustrating it with a deployment diagram.

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
* The vision should be ca. a quarter of a page.


---
type: qna
q: Should we include risks in the vision and scope document?
---
No, they are not necessary to cover. They are part of the example in the book chapter, and they are an important part in a real project, but they turned out to be very "artificial" for the student projects so I thought it would be better just to take them out, also to reduce size of the document and workload. 


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
class: rubric
file: rubrics/requirements.mw
type: table
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

---
class: rubric
file: rubrics/usecases-level.mw
type: table
---

## Architecture Part

### 7. Deployment Diagram

Present a first version of a deployment diagram of your system. Identify the main execution nodes of your system and how they are connected. Identify critical hardware components (even if you later chose to simulate them.) Identify communication protocols that you are already aware of, and identify execution environments.

**Hints:** Most likely, the deployment diagram will fit on a single A4 page in landscape orientation.

### Criteria for the Deployment Diagram

The deployment diagram is evaluated based on general criteria for diagrams.

---
class: rubric
file: rubrics/deployment.mw
type: table
---

# Feedback Document and Delivery

On Teams, you find a template for the evaluation document, under `Semester Project / feedback-v1-team-xx.docx`.
Create a copy, and fill it out for your own team:

* Add team name and team members
* Follow the instructions in the document
    * For each rubric, evaluate which level you have achieved for each criteria. Comment where necessary.
    * Add up to three questions at the end of the document where you ask about particular help.


# Delivery

Deliver both the system specification and the feedback document via Blackboard.



Should we include risks in the vision and scope document?

No, not necessary to cover. They were part of the example in the book chapter, and they are an important part in a real project, but they turned out to be very "artificial" for the student projects so I thought it would be better just to take them out, also to reduce size of the document and workload. 