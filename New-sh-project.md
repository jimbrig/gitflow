# Process to create odoo.sh project
This process explain the step to create a new project on odoo.sh platform for Odoo direct client.

**This process is only valid if Odoo handle the project from a to z**

**If the client wants to make himself some development, he will handle the creation of the project on odoo.sh**

## For the functional team
* You need a github account for the process, create one if you still don't have it
* You need the subscription number of your client
* The subscription should have a line with the product _Odoo.sh Access_
* Ask the person in the PS support/maintenance rotation to create the project. Give him
   * the subscription number
   * the name of the client
   * the version of Odoo that should be used
   * the name of your github account


## For the technical consultant

* Ask baa@odoo.com access to https://github.com/odoo-ps/ if you don't have it yet
* Create a new repo **psOFFICE-CLIENT_NAME** within [odoo-ps github organization](https://github.com/odoo-ps/) where 
   * OFFICE should be [be, lu, us, hk] depending on which office manages the project
   * CLIENT_NAME should be the name of the client without any special char or accent or capital letter
   * Example: for the Belgian client "la fabrique givrée" create a repo _psbe-lafabriquegivree_ or _psbe-la-fabrique-givree_
   * There is a team for each office (PSBE (for be and lu), PSUS, PSIN, ...) add the corresponding team as admin of the repo in order to allow you colleague to access the repo as well
   * Add a default readme and the gitignore for python
* Go on [odoo.sh](https://www.odoo.sh/project/create), log in and create a new project
* Choose an existing repository: The one you just created
* Use the client subscription, choose the server region according to the client localization
    * By default client from BE and LU will be in Europe, HK and AE is Asia and US is Americas
* Add the consultant team (PSAE) as admin in the settings 


# I need a odoo.sh project for a pre-sales demo/test

## For the functional team
* Follow the same process but use this subscription: SH3141592654 
* When the presales is done ask the support/maintenance rotation to delete the repo and the project on odoo.sh
 
## For the technical team
* Follow the same process but for the name of the repo use psOFFICE-demo-CLIENT_NAME
* If the project really start we will create a new repo



PS: When you ask baa@odoo.com access on github always specify which access you need and what is your github account name.
