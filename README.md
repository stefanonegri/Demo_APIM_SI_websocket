# Demo_APIM_SI_websocket
demo of websocket API using RabbitMQ, WSO2 Streaming Integrator, WSO2 APIM

![Picture](Image.png)

## Prerequisites:

Install WSO2 API Manager 3.2.0 

Install WSO2 SI tooling 1.1.0

Install RabbitMQ

Install Google Browser web socket client 

## Create stream flow with SI tooling
ReceiveRabbitmqInJSONFormat.siddhi [(source)](ReceiveRabbitmqInJSONFormat.siddhi);

## Create new API in APIM:

### in the Publisher
- Create a new websocket API with:
- Name: any, for example RabbitMQStream
- Context: rabbiymq
- Version: 1.0
- Endpoint: ws://localhost:8080
- Business Plan: any
- Publish the API

### in the Developer Portal
- Eventually create new Application
- Subscribe to the websocket API RabbitMQStream
- Create a new token

### Test the websocket API
- open the browser web socket client
- in the server url set: ws://localhost:9099/rabbitmq/1.0?access_token=<token> and connect
- to test, use the samples in SI tooling: /Users/wso2/wso2si-tooling-1.1.0/samples/sample-clients/rabbitmq-producer
- run the command: ant -DnoOfEventsToPublish=5
- check the reeived messages in web socket client
