## Bug prevention
### Trust your linter
In general TRUST your linter. If they highlight something, especially in red or bright yellow, it is worth it to check it out. Most of the time it is trying to make you notice a bug. The only exception is for import of odoo modules. 
### General rules
This are the questions that you should ask yourself each time you write
#### A line of code
* Can my variable be empty (or equivalent language/context specific value)? Yes? Throw a user error or put an if statement before it
* Can my variable contain multiple record? Yes? Use a for loop or the mapped function
* Does this attribute exists on the object used? You can check in the models view in the interface
* Do i understand what this standard function is returning? Can it return nothing or return a null value?

#### A function
* Should my function be called all the time? No? Put the conditions inside the function NOT outside

DO
```python
def fun(self):
    if not self.state == 'done':
        return
    ...
``` 
DO NOT
```python
if not line.state == 'done':
    line.fun()
    
def fun(self):
    ...
``` 
* Should my function throw an error if the condition are not met or silently do nothing?
* Should my function always return something? 
* Can my function be used with multiple records? Default answer : YES ! Put the loop in the function NOT outside. If the answer is no then use ensure_one

#### A functionality
* Does it make sense to have a traceback instead of a user error?
* Is my code indistinguishably from standard code? Both in terms of code and in terms of functionality?
* Will a non technical user be able to use this functionality? Is it simple enough?
* Will you be satisfied with this solution if you were on the receiving end of the development?
* Did you test ALL the correct ways to use your dev? 
* Did you test the incorrect ways to use your dev?
* After deploying to a platform, did you test it again?

### Saas specific
When an error occur during deployment, the record is still created !!! Delete the record manually in the DB before trying to redeploy !!!
