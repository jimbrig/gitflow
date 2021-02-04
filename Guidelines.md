## Slides from presentation
https://drive.google.com/open?id=1evaZuBGFQP-S1y_LflYKZmO4cQLnWeCC9L8_8M7Wj28

## Time estimations
On the **timesheet** tabs, in the **Initially Planned Hours** field, put the sum of the dev estimation PLUS the time spent for the analysis, BUT the reliability will only be applied to the dev part of the time, not the total time. You can reinsure your functional consultant on that.

## Template
There is a template on github here: https://github.com/odoo-ps/psbe-process/wiki/Saas-Custo-template
Please follow this template as uniformisation will make everyone's life easier, and even though it might take a bit more time at first, eventually it will make doing the estimations faster. Especially for estimating the time.

## Estimation reliability
As a reminder, please find [here TFR's wonderful slideshow](https://github.com/odoo-ps/psbe-process/files/4476685/TTC.1.-.Write.a.good.technical.analysis.1.pptx) here on how to make good estimation reliability. Mostly, remember that for these cases, the reliability will be of 50%:
* Website
* Integration
* JS
* Complex Access rights (especially when changing multi-company record rules)

## Change request
In case of a change request, make sure the functional adds the request in the body of the task, not in the chatter, as this makes reading the history of the task a nightmare. They need to add a new section "Change request" with he date. Example:
```
Change request 22/00/2020 
```

## PS Tech Module databases
As you may or may not know, we are trying to build a database of recurrent developments. We realized some features are often asked by customers and we should isolate them and create specific modules that we could reuse in the future (example, SAML connector for SSO). So if you identify a feature that could be "ps-tech-standardized" please make a note of it in the task for the dev to create a separate module for this feature. Feel free to call on me to come discuss it with you if you are hesitant.

## Feedback
Please, if you have any comments, feedback, critics or suggestions, make sure to let me know as this is a group effort and we need everyone's input on how to make presales a better organized, less demanding task.
