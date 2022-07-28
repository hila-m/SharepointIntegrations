# Sharepoint Integrations

As initial step you will have to create an application registred in your SharePoint online tenant.
You have several option to integrate to SharePoint, based on Pull (Graph/Sharepoint API) or Push (SharePoint Webhook) activation models.

Register your app with the Azure AD v2.0 endpoint - Microsoft Graph | Microsoft Docs
Apps & service principals in Azure AD - Microsoft Entra | Microsoft Docs

Setup your Postman Environment variables:
* tenant
* client_id
* client_secret
* scope = https://graph.microsoft.com/.default

Setup your Postman Collection variables (Use Graph collection-Graph.postman_collection.json):
* webUrl -> https://<host>.sharepoint.com/sites/<your_site>
![image](https://user-images.githubusercontent.com/102023453/181501060-4ffd7341-a856-469c-ae7d-961980ac07c2.png)

## Pull SharePoint changes-
# Use Graph API to integrate with SharePoint to poll for changes within a document library
You can check out graph explorer for testing puposes (usefull to make sure your used has appropriate privileges).
https://developer.microsoft.com/en-us/graph/graph-explorer
  
## API activations can be controlled to support paging and etc.
https://docs.microsoft.com/en-us/graph/api/driveitem-list-children?view=graph-rest-1.0&tabs=http#optional-query-parameters
  
## Use delta operation to captur changes
https://docs.microsoft.com/en-us/graph/api/driveitem-delta?view=graph-rest-1.0&tabs=http

## Use query parameter to filter changes based on lastModifiedDateTime
Execute the collection operations -> 
  QuerySiteId->QueryDriveId->QueryFiles-lastModifiedDateTime based on webUrl collection variable, operation will query sharepoint object ids and query root document library for chnages based on last modified time
  
* You can choose to query fields based on list item columns
* You can also query document library based on path.

# Get Push notifications for SharePoint changes by using Webhooks-
  ![image](https://user-images.githubusercontent.com/102023453/181506793-cd3a5191-186f-495a-a00c-9d8223bc94c2.png)

Webhooks will allow to create a subscription to a SharePoint object and get notification for changed events.
Webhook handler has to be implemented in an A-Sync mode and reply back within 5 seconds, in case the activation of the notification service failes there will be automatic retry for 5 times (https://docs.microsoft.com/en-us/sharepoint/dev/apis/webhooks/webhooks-reference-implementation![image](https://user-images.githubusercontent.com/102023453/181505192-36a4a3ce-4006-495b-a96b-45184ece2233.png)

## Setup webhook
Get started with SharePoint webhooks | Microsoft Docs![image](https://user-images.githubusercontent.com/102023453/181505318-b70405fc-bf1f-45b4-ab71-3fe05976f612.png)
  
## Using Azure Functions with SharePoint webhooks | Microsoft Docs
https://github.com/pnp/sp-dev-samples/blob/master/Samples/WebHooks.List.AzureAD/azure%20functions%20guide.md![image](https://user-images.githubusercontent.com/102023453/181505277-84c9c521-ef17-4d86-817d-44321c37becc.png)





