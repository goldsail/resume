## How to request the Azure login credential

In Azure CLI:
```Bash
az ad sp create-for-rbac --name "myApp" --role "Storage Blob Data Contributor" \
                         --scopes /subscriptions/{subscription-id}/resourceGroups/{resource-group-name} \
                         --sdk-auth
```
