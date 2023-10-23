# Creating contract event subscriptions


To create a new subscription to a contract event, refer to the following API:

**endpoint**: INSTANCE:3030/event
**method**: POST
**content-type**: application/json
**auth**: "Authorization: Bearer YOUR_JWT_ACCESS_TOKEN"
**body**:

```json
{"contract_id": "CONTRACT_ID", "topic1": "XDR", "topic2": "XDR", "topic3": "XDR", "topic4": "XDR", "max_single_size": "MAX_EVENT_BYTE_SIZE as integer"}
```

As you can see, you can choose to be as specific as you want with the events you subscribe to. You can leave fields (contract_id, topic1, topic2, topic3, topic4) null to have the field match with any value, for example, setting the contract id to null and the first topic to transfer matches with all transfer events from all contracts. 

We also set the max single size parameter which indicates how much will one event cost us at most (for now that we don't have the metering running, you can also set to the network's max so like 2000 bytes). 

## Example

This example subscribes to all events of xycLoans' XLM pool:

```curl
 curl --header "Content-Type: application/json" \
  --request POST \
  --data '{"contract_id":"CCVP5K2R2X4RWSJB7WZDDYVWHWDUUZWBWHLFPSZBIDOAWXH3LX6GG5PU", "max_single_size": 200}' -H "Authorization: Bearer YOUR_JWT_ACCESS_TOKEN" \
  http://INSTANCE:3030/event
```
