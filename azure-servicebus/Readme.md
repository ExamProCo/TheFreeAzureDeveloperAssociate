## Creating Service Bus Queue via CLI 

### create resource group

```
az group create --name ContosoRG --location eastus
```

### create servicebus namespace

```
az servicebus namespace create --resource-group ContosoRG --name ContosoSBusNS --location eastus
```

### create servicebus queue

```
az servicebus queue create --resource-group ContosoRG --namespace-name ContosoSBusNS --name ContosoOrdersQueue
```

### create servicebus authorization rule

```
az servicebus namespace authorization-rule keys list --resource-group ContosoRG --namespace-name ContosoSBusNS --name RootManageSharedAccessKey--query primaryConnectionString --output tsv
```

## Install SDK

You need to implement it via the SDK.
Let's use Javascript and install the SDK library via npm.

```
npm install @azure/service-bus
```

## Send a message to the queue
Provide the values Service Bus connection string and Queue name enviroment variable values

```
CONNECTION_STRING= QUEUE_NAME= node send.js
```

## Observe there is a message in the queue


## Receive a message from the queue
```
CONNECTION_STRING= QUEUE_NAME= node receive.js
```