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

## Install  DotEnv

```
npm install dotenv --save
```

Create a `.env`, ensure to supply it to .gitignore

```
CONNECTION_STRING=
QUEUE_NAME=
```

## Get Service Bus Connection String URL

Settings > Shared Access Policies > RootManagerSharedAccesskey > Copy Primary Connection String.

## Send a message to the queue
Provide the values Service Bus connection string and Queue name enviroment variable values

```
node send.js
```

## Observe there is a message in the queue

```
az servicebus queue show \
--resource-group= \
--namespace-name= \
--name=  \
--output=yaml
```

Obeserve there are 10 messages in the queue

> messageCount: 10

## Receive a message from the queue

```
node receive.js
```

Recieve should print them all out.
Wait for it to finish executing...

```
Received message: Albert Einstein
Received message: Werner Heisenberg
Received message: Marie Curie
Received message: Steven Hawking
Received message: Isaac Newton
Received message: Niels Bohr
Received message: Michael Faraday
Received message: Galileo Galilei
Received message: Johannes Kepler
Received message: Nikolaus Kopernikus
```