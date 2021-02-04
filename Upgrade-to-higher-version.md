### Migration / Upgrade
An upgrade / migration refers to a change of version (ex from 12 to 13)

+ Create a **migration request at http://upgrade.odoo.com**
  + For an estimation of time required for standard part : http://migration-test.odoo.com:5013 
+ A ticket will be automatically created in Ps maintenance (if dev > 25h or Sh projects)
  + We're here to migrate the custom code or to help you with Odoo.sh projects
+ If you really need to work on migration before the upgrade request : 
  + Create a task in Ps maintenance stage Migration Queue
  + Be complete : customer, from/to versions, change of plateform if required, existing customisations
  + Put yourself as reviewer
  + DO NOT complete Sales Order Item and Parent Task ($$)
+ Only 1 task by migration in Ps maintenance
  + Create a subtask for additional requests or bug fixes

###### FAQ
+ Do you handle upgrades for client on their own repository or in Time and Materials ? 
  + No. The client has to be hosted by Odoo and pay maintenance fees.

--------

### Migration / Upgrade for Techs

+ Follow-up with the functional
+ Ask for a migrated database (if not done already)
+ Install your modules on an empty database (locally then on Sh)
+ Install your modules on the upgraded database (locally then on Sh)
+ Migrate the data
+ Tests

More details on every steps on [wiki/Migration-Process](https://github.com/odoo/ps-custom/wiki/Migration-Process)

###### FAQ
+ Where should I check for **existing devs**? 
  + In Ps Saas Customisation project, check all Done tasks with subscription same as client's one.