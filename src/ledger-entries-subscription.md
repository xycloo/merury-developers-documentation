# Ledger entries

Mercury also allows to easily record state changes. This is especially useful in scenarios where
events alone don't give you enough context. When you subscribe to a ledger entry update for a contract
you are subscribing to the contract instance, to a presistent, or to temporary entry.


To create a new subscription to a ledger entry, refer to the following API:

**endpoint**: INSTANCE:3030/entry
**method**: POST
**content-type**: application/json
**auth**: "Authorization: Bearer YOUR_JWT_ACCESS_TOKEN"
**body**:

```json
{"contract_id": "CONTRACT_ID", "key_xdr": "entry key as base64 xdr", "max_single_size": "MAX_ENTRY_BYTE_SIZE as integer"}
```

### Example

To subscribe to a contract's instance updates:

```
curl --header "Content-Type: application/json" \
  --request POST \
  --data '{"contract_id":"contract id", "key_xdr": "AAAAFA==", "max_single_size": 64000}' -H "Authorization: Bearer $JWT_TOKEN" \
  BACKEND/entry
```
