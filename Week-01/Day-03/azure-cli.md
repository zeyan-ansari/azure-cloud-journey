# Azure CLI - Day 03

## What is Azure CLI?
Azure CLI is a command-line tool used to manage Azure resources using commands instead of the portal.

---

## Commands I Used

### Create Resource Group

az group create --name rg-cli-test --location centralindia

### List Resource Groups
az group list --output table


### Delete Resource Group
az group delete --name rg-cli-test --yes --no-wait

```bash
Add Azure CLI Day 03 notes
