# Ps - Saas Customisation Process

## Introduction
This page explains the process for saas custo tasks, for functional and technical consultants.
If you need a training on writing these, check this page : [[Technical analysis]].

## 1. New
_**Responsible:** Functional Team, Functional consultant that write the specification_  

_**Mandatory output:**_ 

* _Functional Specification and required information_
* _Meaningful Name_
* _Task Owner_ -> **Functional consultant**
* _Parent Task (with SO line) and client_
* _Subscription_

_**Fields that must be empty:**_ 

* _Assigned to_
* _Reviewer_

_**Description:**_

First the functional consultant needs to determine [[is it a development?]]

This stage should be use by the functional consultant as stage to set all the needed information. Once it's done, he can move the task to the stage _Analysis_.

The task should be create from the button "Sub-tasks", you reach the kanban view. Click on create.

Change the task name, remove useless information like the SO and the number of pack hour. Keep the client name and add a meaningful name that give a small idea on the needed customization. 

Change the task owner to the functional consultant who wrote the specification. DO NOT USE the reviewer to put the functional consultant name, we will use it for something else. DO NOT FILL _assigned to_ as well

For the description please fill this template

```
Odoo Version: v10.0 or v11.0 or saas-11.2 or ...
Platform: Saas or odoo.sh
Production Database URL:
Test Database URL:
Admin Login:

Business Need:
-------------- 

Functional Analysis:
--------------------


Existing Customization:
-----------------------

```

Once all the information are present, change the stage to _Analysis_. If there is already exting customization, please tell it. If it's already in a module that's great, If you can export it with sudio, do it and push it on github. If it's in the database the developer will export it for you.

**Warning: As we are getting more and more tasks, tasks that do not have the correct information will be put back in _New_. Once corrected you will need to put it back in _Analysis_. This means the task will go back to the end of the queue, so please make sure all the fields are correctly set**
<!-- Done -->

## 2. Analysis 
_**Responsible:** Technical Team(check rotation), Support Responsible_  

_**Mandatory output:**_ 

* _Technical Analysis in description_
* _Estimate time in description_
* _Timesheet Tab-> Initially planned hours = time spent on estimation + time estimated_
* _Timesheet Tab-> Reliability_
* _Status -> Waiting for client go_
* _Reviewer_ -> **Technical consultant**

_**Fields that must be empty:**_ 

* _Assigned to_

_**Description:**_

The technical consultant immediately puts himself as reviewer on the task when he starts to study it. This way we avoid 2 people working one same task

First of all the technical consultant should check that all the information required are present. Based on that information, he write a technical analysis and adds it as a new section in the task's description.

If you find that the task was not correctly written, put it back as _New_ and ping the consultant on the missing information so that they can correct it. Keep in mind the point of this is not to "punish" people, but to have processes respected. So try to be discerning, everyone makes mistakes.

First you must determine if it's SaaS or sh. Here are the [[general rules for choosing sh or SaaS]].

Please follow the [[Technical analysis template]].

Please follow these [[guidelines]] regarding estimations, reliability, analysis and change requests.

While doing the analysis, ask yourself if this can become a [[standard ps-tech modules]]. Some already exist and might be an answer to the task, check the list regularly.

Add the estimation and reliability in the chatter. 

Add the estimation and reliability in the fields "Initially planned hours" and "Reliability" in the "Timesheets" tab. **In the field "Initially planned hours", the time should take into account the time already spent for the technical analysis.**

If there is any change in the functional analysis, update the description accordingly. The chatter is not made for that. This is the functional consultant responsibility.

Once the analysis is done, the technical consultant puts the task in _Waiting for client go_.

If there is change in the estimation, add as a note the new estimation in the description and update the fields according to these change (Initially planned hours and reliability). We do not want people having to go though the chatter and do additions to get the final time.

The entire time spent by the technical consultants must be logged on the task in the timesheets and thus will be counted for the recurring price (analysis, development, feedback, change requests, meeting about the task, etc.)

<!-- Done -->
## 3. Waiting for client GO 
_**Responsible:** Functional consultant, task owner_  

_**Mandatory output:**_ 

* _Client approbation to start the development_
* _Set the estimation in the field initial planned hour if not done before_

_**Fields that must be empty:**_ 

* _Assigned to_

_**Description:**_
The task wait in this stage until the client decide to go for the development or not to do it. 

If the client want to change the scope, make the change accordingly in the description and the estimation with the help of a technical consultant

if the client don't want to make de development move the task in Cancelled. After a certain amount of times (few month) without news the task can be moved to Backlog

Once the client decide to go for the development, if it wasn't done before (especially in cases where there a change requests), put the estimation in the field "Initially Planned Hours" in order to reserve the hour on the pack of the client and finally change the stage to _Planning_. (should be done in _Analysis_ stage)


<!-- Done -->
## 4. Planning 
_**Responsible:** TFR or CVI by interim_  

_**Mandatory output:**_ 

* _Assigned to a technical consultant_
* _Initially Planned hour_
* _Deadline_
* _Green Light_

_**Description:**_
The responsible of the technical team (nfl)(or it's backup the responsible of the functional team) assign a technical consultant and set a deadline. The deadline is the day when the first version should be available for testing (at the end of the day).

The initially planned hours is set in order to reserved the hour needed on the pack. The initially planned hour will take into account the time spend on the analysis. For example, if the estimation is 8h and 30 minutes have been spent for the analysis, the initially planned hour will be set to 8h30. 


<!-- Done -->
## 5. Development
_**Responsible:** Technical Team, Assigned to_  

_**Mandatory output:**_ 

* _Branch on github with the module_
* _Module deployed on the test database_
* _Module Importable with it's dependency on a fresh database_

_**Description:**_

The task is pulled by the assigned developer from _Planning_ to _Development_ when he really start to work on it.
If the specification are not clear enough ask the task owner and write down the details in the task to keep track of your discussion

1. The dev take a backup of the test database
2. Check if a main branch (ODOOVERSION-CLIENTNAME) already exist. If not create one. 
3. Extract all customization if it's not done yet and push it on the main client branch ODOOVERSION-CLIENTNAME
4. Create a branch from the main one for your development named: ODOOVERSION-CLIENTNAME-FEATURE-TRIGRAM (example: 8.0-mtsolutions-portal-tfr)
5. Make your development, don't forget to test often locally 
5. test locally with the copy of the production database and test that your module can be installed on a fresh database
4. push it on the feature branch, 
6. Deploy the module on a test database in order to let the functional consultant validate the feature
7. Change the stage of the task to functional testing.
8. At the end of each day or at the end of the task, fill in the task work 

<!-- Done -->
## 6. Functional Testing 
_**Responsible:** Functionnal Team, Task Owner_  

_**Mandatory output:**_ 

* _Technical Analysis in description_
* _Estimate time as note_

_**Description:**_
The task owner should check on the test database that the module works as needed. 

- If the feature work
	- Change the status in Client validation
        - Duplicate the production database, upload the module on the new database in order to let the client validate
- if the feature does not work as needed
	1. Change the status in fail validation
	2. Add a comment that explain why the feature does not work properly and if it's a bug, write the procedure to reproduce it and the details of the environment where the feature was tested.


<!-- Done -->
## 7. Code Review
_**Responsible:** Technical Team

_**Mandatory output:**_ 

Approved pull request

_**Description:**_ 

Code is reviewed by a senior developer. When approved the stage will be changed to Client validation, if not changes will be made until it is approved or the ticket is pushed to Fail validation if the changes are major

<!-- Done -->
## 8. Client Validation
_**Responsible:** Functionnal Team, Task Owner_  

_**Mandatory output:**_ 

* _Agreement of the client_
* _And module deployed on production_
* _Or Feedback of the client_

_**Description:**_

Once the code review happen and the functional consultant has validated the feature, the client need to sign off in order to consider the task done and deploy the module on the client production.  
- The functional consultant has to make the client test
- once the client agreed on the feature he can deploy on client's production or ask the assigned developer to deploy it. The task can be moved to _Merge_ by the functional consultant
- If the client does not agreed with the feature, then the stage of the task is change in fail validation, the functional consultant has to write a comment that explain the change(s) required or describe the scenario to reproduce the bug(s) found. 

<!-- Done -->
## 9. Fail Validation
_**Responsible:** Technical Team, Support Responsible_  

_**Mandatory output:**_ 

_**Description:**_

**The task in fail validation should be the priority**
- Check that the feedback is clear and feasible otherwise block the task and check with the task owner for more details.
- If the feedback will take a lot of time (A lot has to be compare with the time already spend. 2h for a 3h task it's a lot, 2h for 20h task it's ok) check with the task owner to see if you need the approbation of the client. 
- Once you start to work on the feedback, pull the task in _Development_ stage.
- Work on the same feature branch

- [[Planning Fail Validation]] : TODO



<!-- Done -->
## 10. Merge
_**Responsible:** Technical Team, Consultant assigned_  

_**Mandatory output:**_ 

* _The branch merge in the main branch of the client if needed_

_**Description:**_ If the development has not been done in the main client branch (version-CLIENT_NAME), the developer responsible should merge the branch into the main one in order to keep the main branch up to date. 
and then the task will be finally done. Move the task to stage _Done_.

<!-- Done -->
## 11. Done 
_**Responsible:** No one, it's done_  

_**Switch to:** It's the end of the process_

_**Mandatory output:**  Nope_

_**Description:**_
It's done, yippee! The maintenance Fee of 4€ per hour will be add automatically on the subscription.

- If you have a bug related to that task, send a ticket to help It will reach the ps technical support who will solve the problem asap
- If your client want to change something, no problem create a new task with the description change, you can/should reference this task in the description. 


## General Remarks
**The technical Support** should care about the tasks

- in Analysis
 
**Developer** should care about the tasks assigned to them 
	
- in Planing with green dot
- in Development
- in Fail validation with a green dot
- in Merge

**Functional Consultant** are responsible for the tasks regarding their client
- In New
- In Waiting for client go
- In Functional testing
- In Client Validation


### Peer Check 
Most of the process is a push process which mean that the responsible of a stage change the task to the next stage. Only the task in _Planning_ and _Fail validation_ need a pull from the developer to change the stage in _Development_. 

Since it's a push process, before starting the task related to a stage you should check that the mandatory output of the previous stage is present, if it's not the case you should send back the task to the previous stage with a note explaining why. 


### Timesheet
Each time spend by technical consultant at any stage should be recorded on the task. This time will be use for the maintenance recurring cost. 
The time spend by the functional consultant should be logged on the parent task, the name of the sub-task should be use at the beginning of the description. 