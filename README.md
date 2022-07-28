# Sharepoint Integrations

As initial step you will have to create an application registred in your SharePoint online tenant.
Register your app with the Azure AD v2.0 endpoint - Microsoft Graph | Microsoft Docs
Apps & service principals in Azure AD - Microsoft Entra | Microsoft Docs

Setup your Postman Environment variables:
* tenant
* client_id
* client_secret
* scope = https://graph.microsoft.com/.default

Setup your Postman Collection variables:
* webUrl -> https://<host>.sharepoint.com/sites/<your_site>

![image](https://user-images.githubusercontent.com/102023453/181501060-4ffd7341-a856-469c-ae7d-961980ac07c2.png)

# Use Graph API to integrate with SharePoint to poll for changes within a document library
You can check out graph explorer for testing puposes (usefull to make sure your used has appropriate privileges).
https://developer.microsoft.com/en-us/graph/graph-explorer
  
# API activations can be controlled to support paging and etc.
List the contents of a folder - Microsoft Graph v1.0 | Microsoft Docs![image](https://user-images.githubusercontent.com/102023453/181495331-ad1dc76e-a2b4-4d75-b75a-4f7a67d3af5d.png)

## Use delta operation to captur changes
https://docs.microsoft.com/en-us/graph/api/driveitem-delta?view=graph-rest-1.0&tabs=http


## Use query parameter to filter chnages based on lastModifiedDateTime
You can choose to query fields based on list item columns



