# arm-template-demo

This is an actions-based ARM template runner which creates a resource group and deploys storage to it. Most of this can be setup using the [Microsoft Documentation](https://docs.microsoft.com/en-us/azure/azure-resource-manager/templates/deploy-github-actions). However, the creation of a resource group requires a broader scope than what is created in the Authentication section of this walkthrough. Therefore, the [Service Principal creation step](https://docs.microsoft.com/en-us/azure/azure-resource-manager/templates/deploy-github-actions#generate-deployment-credentials) needs to be scoped to the subscription rather than a resource group (example below):

```sh
az ad sp create-for-rbac --name {myApp} --role contributor --scopes /subscriptions/{subscription-id} --sdk-auth
```
