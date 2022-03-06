## CLI Commands

Documentation for the Storage Queue Message CLI
https://docs.microsoft.com/en-us/cli/azure/storage/message?view=azure-cli-latest



Set Env Vars
```
export QUEUE_CONNECTION_STRING=""
export QUEUE_NAME=
```

### Add a message to the queue

We'll set two messages so we can observe the visibility 

```
az storage message put \
--connection-string=$QUEUE_CONNECTION_STRING \
--queue-name=$QUEUE_NAME \
--content="hello world"
```

```
az storage message put \
--connection-string=$QUEUE_CONNECTION_STRING \
--queue-name=$QUEUE_NAME \
--content="hello mars"
```

## Peak at the message in the queue
Fetches top of queue message without setting the visiblity 

```
az storage message peek \
--connection-string=$QUEUE_CONNECTION_STRING \
--queue-name=$QUEUE_NAME
```

## Get at the message in the queue

```
az storage message get \
--connection-string=$QUEUE_CONNECTION_STRING \
--queue-name=$QUEUE_NAME
```

## Clear the queue

```
az storage message clear \
--connection-string=$QUEUE_CONNECTION_STRING \
--queue-name=$QUEUE_NAME
```