# For Saas/Odoo.sh/On-Premise projects

# Rules

**Features**

Separate the features that can be isolated from one another (no link between features)

**Module Setup Time**

Range between :

	- New customer 0.5h to
	- Big database 4H

**Nomenclature**

Use standard nomenclature. English variable names. No capitals. Words separated by _.

Try to make explicit variable names. Ex: sale_order_line_ids instead of order_line

	- M2O end with _id
	- O2M, M2M end with _ids

**Time estimate reliability**

For website, front-end, webshop, modification of standard record rules => 50% to **MAXIMUM** 70%

# Template

## How to use?
Try separating features and create one block like the template below for each feature. 
You only need to display the blocks that you need for your task analysis, no need to display all the blocks.

Exemple:
```
Data model:
    - account.invoice: 
        New Field: margin, float, RQ
```

## Feature 1
```
Data:
    - Config parameters
    - Sequence
    - New records for configurations
    - Email templates

Data model:
    - (New) Model 1: 
        New Field: Name, String, Type, RQ, RO, Compute, Related, Stored (compute/related), groups
    - Model 2:
        New Field: Name, String, Type, RQ, RO, Compute, Related, Stored (compute/related), groups
    - Model n:
        ...

Back-end view change (View, Menu, Action):
    - Model 1:
        New View
           See mock-up + domain attrs, button, groups
        Inherit View: xml_id
           Change (domain, attrs, button, groups) 
        menu + action
    - Model 2:
        ...

Business Flow change (Python code in model, compute fields explanation):
    - Method to overwrite
    - Compute
    - Explain the behavior
    - Use external library.. 
    - New button: new method
    - Constrains
    - On change
    - Server actions
    - Automated actions
    - Scheduled actions

Security :
    - Groups
    - ACL (required if new model)
         name, model, group, read, write, create, unlink
    - Record rules

Report Change:
    - Use studio as much as possible ! 
    - Change existing report
    - New Report => minimum 8h estimate

Controller:
    - Change existing controller: Specify which one (route/method) + Behavior
    - Create new controller

Website template change:
    - Specify which template to change (xml_id)
    - To create

Js Change:
    - Specify which file (*.js)
    - Specify which class to inherit

Scripts:
    - Migration scripts
    - Workflow change scripts. Example: changing an M2O to an O2M, creating new fields that need to have set values, etc.


Integration:
    - Type: out / in / out real time / odoo api call  
    - Trigger: Cron or real time (which user action)
    - Which record to filter
    - Mapping: Based on functional mapping
    - Post-process
```

## Feature 2: 

The new feature, no link to feature 1