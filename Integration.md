## Some terminology

An **integration** or **EDI** is the implementation of a data exchange between Odoo and an other software. This other software can be for example another ERP, a specific warehouse management solution, an authentication platform (this case is special and will be the object of a specific section). It can be in-house and developed by the client, or a 3rd party product.

An **API** is a list of methods (functionalities) exposed to the outer world by a software. This allows an other software to call these methods and either retrieve or post/update information. Odoo comes with an API in standard, using XML-RPC or JSON-RPC as protocol. 
https://www.odoo.com/documentation/13.0/webservices/odoo.html

An **FTP** or **SFTP** is a secured file server used to drop and collect files remotely. Usually used because no API is available from the software Odoo must integrate with, so this is an alternative way of exchanging information.

## Gathering information

As business analyst, you must obtain some important information from your client before we start any kind of technical analysis.

### Who will initiate the data exchanges? 

The first option to consider is that the other software will call the Odoo API. This will require development in the other software and usually no development in Odoo. The main job on Odoo side will be to assist the client or 3rd party editor on how to connect to the Odoo API, interact with the models, fields and flows of Odoo, etc.

The second option is to implement the integration in Odoo. A new custom module will be developed in order to make the calls to the other software API or read / write files on a FTP.

Quite often the client does not have the means, rights or resources to customize the other software he uses, so the second option will be chosen.

### How to exchange data?

Given option 2 above was chosen, is there an API available on client side? If yes we must receive the endpoints (urls) and documentation on how to connect to this API. The protocol used by this API is also very useful information, and should be part of the documentation. It can be REST (using JSON contents), SOAP (XML contents) for example.

If there is no API, Odoo should receive an access to a FTP for exchanging data files. Usually Odoo does not provide the FTP, it should be provided by the other party because it will act as interface for their software. We should also receive information about the file format used for the data exchange (usually .xml). At least sample files are necessary.

### What data will be exchanged? Identify the business flows.

You must identify each flow that will be integrated with the other software. This defines which models in Odoo will be impacted. 

For each of those models in Odoo, a mapping of the necessary fields should be listed, because there is not an exact match of fields between the 2 software. Also, some fields are not always mandatory so they can be excluded from the integration. This mapping analysis should ideally be done in advance by the BA, but in some case it will require the tech consultant to have a look at the API documentation or sample XML files.

Here is an examples of an integration with a warehouse management software, with 3 flows to be identified:
1. Update the list of products (product.template) in Odoo with the data coming from the other software.
2. Send the delivery orders (stock.picking) from Odoo to the other software.
3. Update the product quantities (stock.quant) in Odoo with the data coming from the other software.

**Remark:** in this example, there are 2 IN flows and one OUT flow. However, technically, all the flows will be implemented in Odoo, and all data exchanges will be initiated by Odoo. Having IN and OUT flows does not mean that they have to be implemented on both sides.

### When will the data exchange occur?

Usually, a scheduled action (cron) will initiate every data exchange. That means the integration will be asynchronous (not real time) and you must decide of a time interval. For most cases its perfectly fine because we can go down to 15 or even 5 minutes time intervals.

However in some rare cases, the integration must be real time. But this is only doable for OUT flows because instead of a cron, it is an action in Odoo that will trigger the data exchange.

In our example we could have the following time intervals:
1. Update products 2 times per day. Because this information does not change very often.
2. Send the delivery orders every hour. Because they will be processed by batch in the WH management software.
3. Update the quantities every 15 min. Because it's important to stay up to date in the Odoo webshop.

**Remark:** asynchronous integration must always be preferred to real-time because of technical reason. Error management is much easier to manage with a cron being executed in background. Real time integrations may cause poor user experience in case of issues with the other software.

## Integration with a user authentication platform

(To be completed)