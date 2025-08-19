### You can use the below Azure cli commands to set the terraform remote backend
``` shell
#!/bin/bash
## The Storage account name must be unique, and the values below should match your backend.tf
RESOURCE_GROUP_NAME=demo-resources
STORAGE_ACCOUNT_NAME=techstorage
CONTAINER_NAME=prod-tfstate

# Create resource group
az group create --name demo-resources --location centralindia

# Create storage account
az storage account create --name techstorage --resource-group demo-resources --location centralindia --sku Standard_LRS

# Create blob container
az storage container create --name prod-tfstate --account-name techstorage

# Check all available SKUs
az vm list-skus --location centralindia --all --output table
```
