### HOW do you design the feature in Odoo ?
* Goal: Estimation but but not only….
* Share all information found during the estimation phase
* Avoid the developper to redo the analysis work
* Take notes of everything

**...it generally takes 5 to 7% of the final estimation**

### Steps
* Understand the flow: if necessary ask for a test environment and a test scenario from functional consultant
* Read the code: look in Odoo standard code what is being done to understand what should be modified and the possible corner cases. Avoid assumptions.
* Follow the [template](Saas-Custo-template)
* Poc the shadow zone: if you are really not sure, and no one else is, do a POC to test your solution. Don't do a full POC if possible, but on the shadow zones only
* Challenge your solution: is my solution ok?
* On odoo.sh check if you need studio fields, or if you need saas fields based on studio fields

### Estimation
* Estimation for a large amount of time is NEVER RELIABLE
* Estimate each small item of the analysis
* Do not underestimate the time to test complex cases (...it generally takes 5 to 7% of the final estimation)
* Follow your intuition
* Always remind others and yourself that an estimation is an ESTIMATION

### Reliability.
* 70% is the minimum acceptable in normal condition
* 100% It’s not an estimation

It will be less than 70% if:
* Need more information
* Spend more time on the analysis
* Need a poc maybe

**Exception where 50% is more likely**
* Website
* Integration
* JS
* Complex Access right (record rules for example can trigger a lot of unwanted behaviors, you won't know until you try to implement it, time can easily double)

