# Contract Events

Assuming that you have a subscription targeted to the events you are indexing,
below are some instructions to get started making some more specific queries.

## Events by contract id

In this example, we're querying events (within the constraints of our subscription) for Testnet's
native token contract.

```grapqhl
query MyQuery {
  eventByContractId(
    searchedContractId: "CDLZFC3SYJYDZT7K67VZ75HPJVIEUVNIXF47ZG2FB2RMQQVU2HHGCYSC"
  ) {
    edges {
      node {
        contractId
        data
        ledger
        ledgerTimestamp
        topic2
        topic1
        topic4
        topic3
      }
    }
  }
}
```

Example response:

```json
{
  "data": {
    "eventByContractId": {
      "edges": [
        {
          "node": {
            "contractId": "CDLZFC3SYJYDZT7K67VZ75HPJVIEUVNIXF47ZG2FB2RMQQVU2HHGCYSC",
            "data": "AAAACgAAAAAAAAAAAAAAAAX14QA=",
            "ledger": 1976715,
            "ledgerTimestamp": 1697125133,
            "topic2": "AAAAEgAAAAAAAAAAlgxjlS3RNgkTERctfeiCrlUtOyt9BCzR4tRDDY9zmIE=",
            "topic1": "AAAADwAAAAh0cmFuc2Zlcg==",
            "topic4": "AAAADgAAAAZuYXRpdmUAAA==",
            "topic3": "AAAAEgAAAAFkp3At7J1OWk8PiDhUMY2lWuneIYknC4OsmpJHxEYR7Q=="
          }
        },
        {
          "node": {
            "contractId": "CDLZFC3SYJYDZT7K67VZ75HPJVIEUVNIXF47ZG2FB2RMQQVU2HHGCYSC",
            "data": "AAAACgAAAAAAAAAAAAAAAAABgnY=",
            "ledger": 1977257,
            "ledgerTimestamp": 1697127978,
            "topic2": "AAAAEgAAAAAAAAAAtXs1DVecP4w3jdgAVoD8DDcUkSryRVL3pjWQIbk1EZY=",
            "topic1": "AAAADwAAAAh0cmFuc2Zlcg==",
            "topic4": "AAAADgAAAAZuYXRpdmUAAA==",
            "topic3": "AAAAEgAAAAAAAAAAPTdgJsV5ZyTSlS3RBk3s+JcreccjoCp3Vj7Z8jmU26k="
          }
        },
        {
          "node": {
            "contractId": "CDLZFC3SYJYDZT7K67VZ75HPJVIEUVNIXF47ZG2FB2RMQQVU2HHGCYSC",
            "data": "AAAACgAAAAAAAAAAAAAAAAAAA+g=",
            "ledger": 1977723,
            "ledgerTimestamp": 1697130446,
            "topic2": "AAAAEgAAAAAAAAAAJYf9NMqmC02G4br+I6LKzbfLvGV8QeiHblDN8VQtkyI=",
            "topic1": "AAAADwAAAAh0cmFuc2Zlcg==",
            "topic4": "AAAADgAAAAZuYXRpdmUAAA==",
            "topic3": "AAAAEgAAAAAAAAAAf1sKj1rp5aRGdzj/pa4Yh0Jg83YJhhCmvWdqZoi4zks="
          }
        },
        {
          "node": {
            "contractId": "CDLZFC3SYJYDZT7K67VZ75HPJVIEUVNIXF47ZG2FB2RMQQVU2HHGCYSC",
            "data": "AAAACgAAAAAAAAAAAAAAAlQL5AA=",
            "ledger": 1977738,
            "ledgerTimestamp": 1697130525,
            "topic2": "AAAAEgAAAAAAAAAAJYf9NMqmC02G4br+I6LKzbfLvGV8QeiHblDN8VQtkyI=",
            "topic1": "AAAADwAAAAh0cmFuc2Zlcg==",
            "topic4": "AAAADgAAAAZuYXRpdmUAAA==",
            "topic3": "AAAAEgAAAAAAAAAAf1sKj1rp5aRGdzj/pa4Yh0Jg83YJhhCmvWdqZoi4zks="
          }
        },
        {
          "node": {
            "contractId": "CDLZFC3SYJYDZT7K67VZ75HPJVIEUVNIXF47ZG2FB2RMQQVU2HHGCYSC",
            "data": "AAAACgAAAAAAAAAAAAAAAAX14QA=",
            "ledger": 1978025,
            "ledgerTimestamp": 1697132038,
            "topic2": "AAAAEgAAAAAAAAAAlgxjlS3RNgkTERctfeiCrlUtOyt9BCzR4tRDDY9zmIE=",
            "topic1": "AAAADwAAAAh0cmFuc2Zlcg==",
            "topic4": "AAAADgAAAAZuYXRpdmUAAA==",
            "topic3": "AAAAEgAAAAAAAAAADrWdipCyvgYDlv6kRpdNchs5UGHB3Dsol3VHKAS2tYE="
          }
        }
      ]
    }
  }
}
```

> Note that the data for events is stored as base64-encoded XDR.

## Events by topics

Mercury also allows you to query events given certain topics. For instance, let's index
all transfer events in our subscription to the address `GAHLLHMKSCZL4BQDS37KIRUXJVZBWOKQMHA5YOZIS52UOKAEW22YDSXX`:

```graphql
query MyQuery {
  eventByTopic(
    t1: "AAAADwAAAAh0cmFuc2Zlcg=="
    t3: "AAAAEgAAAAAAAAAADrWdipCyvgYDlv6kRpdNchs5UGHB3Dsol3VHKAS2tYE="
  ) {
    edges {
      node {
        contractId
        data
        ledger
        ledgerTimestamp
        topic1
        topic2
        topic3
        topic4
      }
    }
  }
}
```

sample response:

```json
{
  "data": {
    "eventByTopic": {
      "edges": [
        {
          "node": {
            "contractId": "CDLZFC3SYJYDZT7K67VZ75HPJVIEUVNIXF47ZG2FB2RMQQVU2HHGCYSC",
            "data": "AAAACgAAAAAAAAAAAAAAAAX14QA=",
            "ledger": 1978025,
            "ledgerTimestamp": 1697132038,
            "topic1": "AAAADwAAAAh0cmFuc2Zlcg==",
            "topic2": "AAAAEgAAAAAAAAAAlgxjlS3RNgkTERctfeiCrlUtOyt9BCzR4tRDDY9zmIE=",
            "topic3": "AAAAEgAAAAAAAAAADrWdipCyvgYDlv6kRpdNchs5UGHB3Dsol3VHKAS2tYE=",
            "topic4": "AAAADgAAAAZuYXRpdmUAAA=="
          }
        }
      ]
    }
  }
}
```

> Note: this assumes that you already know the exact structure of the events you're querying.
> In this example we know that topic1 (t1) holds the event kind (Symbol("transfer") in our case)
> and that topic3 (t3) holds an Address object for the public key `GAHLLHMKSCZL4BQDS37KIRUXJVZBWOKQMHA5YOZIS52UOKAEW22YDSXX`.
> Building these xdrs must be done by the client and can be easily done with the existing
> stellar xdr tooling. 
