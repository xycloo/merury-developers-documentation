# Ledger etries expiration

Soroban introduces the novel concept of state expiration, and it's essential that developers and users
are able to efficiently know the expiration state of their entries.


To create a new subscription to a ledger entry expiration, refer to the following API:

**endpoint**: INSTANCE:3030/expiration
**method**: POST
**content-type**: application/json
**auth**: "Authorization: Bearer YOUR_JWT_ACCESS_TOKEN"
**body**:

```json
{"hash_xdr": "base64 xdr of your entry's hash"}
```

