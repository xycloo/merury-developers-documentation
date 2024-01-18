# Full account subscriptions - Stellar Classic

Mercury aims to also enable efficient indexing of all stellar classic operations. Currently, 
we do so through full account subscriptions. These are stellar account-centered subscriptions, 
and a subscription for an account will tell mercury to index all the currently supported operations
that encompass the specified stellar account.

Currently-supported stellar classic operations are:
- payments
- createaccount

To create a full account subscription, refer to the following API:

**endpoint**: INSTANCE:3030/account
**method**: POST
**content-type**: application/json
**auth**: "Authorization: Bearer YOUR_JWT_ACCESS_TOKEN"
**body**:

```json
{"publickey": "public key of the account (strkey)", "hydrate": bool}
```

## Example

```
curl --header "Content-Type: application/json" \
  --request POST \
  --data '{"publickey":"GDEFZKAH3SDHKR6OJYNORMTQY7QB44EJX5BL6WHVZBDQKOYO7BHEBC5C"}' -H "Authorization: Bearer $JWT_TOKEN" \                         
  BACKEND/account

```
