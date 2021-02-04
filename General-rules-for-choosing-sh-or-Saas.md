## Cases where we force the use of SH:

### Based on development time
* Customisations that take at least 10 hours
* The customer has reached at least 10 hours on previous development or will be over 10 hours with the new development request
* If you anticipate (or the sales or consultant does) that the customer will need many customization in the future and/or will need customization for which only sh will work

### Based on the customization
* Some modifications of existing fields (remove a compute for example)
* Modification of the webshop's business logic. For cosmetic modifications, we can still do it in Saas if it is validated by an expert 
* If there are on_change methods on a field and you need to modify these on_change, the only way is with sh as the methods need to be overridden
* Modification on controllers (even though it's possible in SaaS, it's painstakingly long)
* Any method called automatically by Odoo for which you can't replace with server action. Example: change the behavior of a write or create method

### Estimation for SaaS to sh
If you decided the customer has to go on sh there can be consequences on the estimation. Here are the guidelines for each case:
* your analysis requires some elements (models, fields, views, etc.) from a studio customization => you need to rewrite the studio components **needed for your development** in python. You need to add the estimation for this rewriting in your analysis
* your analysis requires some code or elements from a SaaS module => you need to rewrite the components **needed for your development** (server actions, etc). You need to add the estimation for this rewriting in your analysis