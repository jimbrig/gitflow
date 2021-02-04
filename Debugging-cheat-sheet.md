## Debugging cheat-sheet
### General rules
* Do not make ANY assumptions, always verify the actual value with ipdb (debugger for JS). Follow the Russian proverb : 'Trust but verify'
* I do not understand the error -> Google
* Sql constrains is being violated -> check the python code of the model _sql_constrain
* I do not know how to do X, Y, Z -> Search in the base code and copy paste
* I have to create a model and don't know what is necessary -> Search in the base code and copy paste
* I don't know how to test -> Amy videos or ask the functional
### My code is not being executed
* Did you add the file in the manifest?
* Did you add the file to the init file?
* Did you add the dependency on the module you are using?
* Is the module installed?
* Did you delete the created records? (for saas only)
* Do you have a typo? Use copy paste to make sure
* Did you refresh the page?
* Did you redeploy your module?

