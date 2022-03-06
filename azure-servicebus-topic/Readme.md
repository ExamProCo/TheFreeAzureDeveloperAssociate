## Install deps 
```
npm install @azure/service-bus
npm install dotenv --save
```

## Send data

```
node sendtotopic.js
```

# Obeserve messages in topic
```
az servicebus topic show \
--resource-group= \
--namespace-name= \
--name=  \
--output=yaml

```

## Recieve data
```
recievefromsubscription.js
```