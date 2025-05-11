# Azure Cli

## Login

```shell
az login
```

## Account

```shell
az account list --output table
az account show
```

## Container Registry

List container registries

```shell
az acr list
```


## Group

Show information of a resource group

```shell
az group show --name [resource_group_name]
```


## Resource Provider

List all resource providers

```shell
az provider list
```


## Network

Show Virtual network

```shell
az network vnet show --resource-group  [resource_group_name] --name [virtual_network_name]
```