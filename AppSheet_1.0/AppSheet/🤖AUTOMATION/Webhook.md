#webhook #automation #api 

[[📌AppSheet Inventory Management PART 1]]

> Auto update [available stocks] after [new available stocks] are updated

## Process

Go to _Manage_ ➡️ _Integrations_ ➡️ *enable integrations*

Go to _Automations_ ➡️ _Tasks_ ➡️ _New Task_ ➡️ [[Webhook]]

[API documentation](https://support.google.com/appsheet?p=api)

# Webhook API 

#### Purpose: When release stocks  is updated, updated available stocks 

## The HHTPS task Editor

###### Task category

_Call a webhook_

###### Task name

_release stocks minus_


###### Table name

%%>What entity table does this task work against?%%

##### What is the origin table name?

_release stocks_

###### Preset
%% Not too sure what this is to be honest %%

_AppSheet API_

###### App Id
##### This is automatic
>App ID to send the request to

6a629944-9965-441c-ace9-52c65e0c7df7 (INVENTORYTEMPLATE-31002422)5dfa70db-243f-4fc2-842b-b5198b8905e8 (SimpleInventory-31002422-22-12-25)9e429f85-1298-4ccf-afa3-b88481244edd (Flowhealth_Canada-31002422)7867e6f5-4049-491f-a9df-dacafb80085b (inventory_management_practice_12-31002422)

###### Target Table Name

_stocks_inventory_

###### Body
##### Fun part : the Script

The body of the HTTP request. (Template that yields the body is supported. Leave empty for default body.)

See the [API documentation](https://support.google.com/appsheet?p=api) for more usage details

[[API Script]]

###### HTTP Headers

Optional HTTP headers. (Expressions that yield HTTP header names or values are supported.)

Add

###### Body Template

The template text file used to format the body of the HTTP request. (Leave empty if no body template used.)


Create

###### Body Template Data Source

The data source for the Body template file.

​

### Execution options

###### Timeout

How many seconds should AppSheet wait for this webhook to complete before timing out?

###### Max number of retries on failure

Should AppSheet retry the webhook if it fails or times out? If so, how many times?

###### Run asynchronously?

Should AppSheet run this webhook asynchronously (in the background) and let the rule return immediately?
