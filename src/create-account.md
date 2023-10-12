# Create Account OPs

## Account created

```graphql
query MyQuery {
  createAccountToPublicKey(
    publicKeyText: "GAQX75URIUYBKEUWDWPRTFBMTW6ZWMAGDMC7IBBA6XWTIDYOSE5LRXLE"
  ) {
    edges {
      node {
        accountByDestination {
          publickey
        }
        accountBySource {
          publickey
        }
        muxedaccountBySourceMuxed {
          publickey
          muxedaccountid
        }
        ledgerByLedger {
          closeTime
          sequence
        }
        startingBalance
      }
    }
  }
}

```

```json
{
  "data": {
    "createAccountToPublicKey": {
      "edges": [
        {
          "node": {
            "accountByDestination": {
              "publickey": "GAQX75URIUYBKEUWDWPRTFBMTW6ZWMAGDMC7IBBA6XWTIDYOSE5LRXLE"
            },
            "accountBySource": {
              "publickey": "GAIH3ULLFQ4DGSECF2AR555KZ4KNDGEKN4AFI4SU2M7B43MGK3QJZNSR"
            },
            "muxedaccountBySourceMuxed": null,
            "ledgerByLedger": {
              "closeTime": 1697129852,
              "sequence": 1977611
            },
            "startingBalance": "100000000000"
          }
        }
      ]
    }
  }
}
```

## Account created from


```graphql
query MyQuery {
  createAccountByPublicKey(
    publicKeyText: "GAIH3ULLFQ4DGSECF2AR555KZ4KNDGEKN4AFI4SU2M7B43MGK3QJZNSR"
  ) {
    edges {
      node {
        accountByDestination {
          publickey
        }
        accountBySource {
          publickey
        }
        muxedaccountBySourceMuxed {
          publickey
          muxedaccountid
        }
        ledgerByLedger {
          closeTime
          sequence
        }
        startingBalance
      }
    }
  }
}
```

```json
{
  "data": {
    "createAccountByPublicKey": {
      "edges": [
        {
          "node": {
            "accountByDestination": {
              "publickey": "GAGTO2P23XRSRUGH7NIRH4GIZX55X77DWNHI6UMHN3JVMJJ2FRZKW2TS"
            },
            "accountBySource": {
              "publickey": "GAIH3ULLFQ4DGSECF2AR555KZ4KNDGEKN4AFI4SU2M7B43MGK3QJZNSR"
            },
            "muxedaccountBySourceMuxed": null,
            "ledgerByLedger": {
              "closeTime": 1697129852,
              "sequence": 1977611
            },
            "startingBalance": "100000000000"
          }
        },
        {
          "node": {
            "accountByDestination": {
              "publickey": "GAQX75URIUYBKEUWDWPRTFBMTW6ZWMAGDMC7IBBA6XWTIDYOSE5LRXLE"
            },
            "accountBySource": {
              "publickey": "GAIH3ULLFQ4DGSECF2AR555KZ4KNDGEKN4AFI4SU2M7B43MGK3QJZNSR"
            },
            "muxedaccountBySourceMuxed": null,
            "ledgerByLedger": {
              "closeTime": 1697129852,
              "sequence": 1977611
            },
            "startingBalance": "100000000000"
          }
        }
      ]
    }
  }
}
```
