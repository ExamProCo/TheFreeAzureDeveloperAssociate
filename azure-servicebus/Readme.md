# create resource group

```
az group create --name ContosoRG --location eastus
```

## create servicebus namespace

```
az servicebus namespace create --resource-group ContosoRG --name ContosoSBusNS --location eastus
```

## create servicebus queue

```
az servicebus queue create --resource-group ContosoRG --namespace-name ContosoSBusNS --name ContosoOrdersQueue
```

# create servicebus authorization rule

```
az servicebus namespace authorization-rule keys list --resource-group ContosoRG --namespace-name ContosoSBusNS --name RootManageSharedAccessKey--query primaryConnectionString --output tsv
```