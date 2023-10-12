# Indexing Payments

Assuming that you already have a full account subscription for the account you wish to index
payments for, with Mercury you can query both payments from and to this account.

## From account

```graphql
query MyQuery {
  paymentsByPublicKey(
    publicKeyText: "GAQX75URIUYBKEUWDWPRTFBMTW6ZWMAGDMC7IBBA6XWTIDYOSE5LRXLE"
  ) {
    edges {
      node {
        amount
        assetByAsset {
          code
          issuer
        }
        accountByDestination {
          publickey
        }
        accountBySource {
          publickey
        }
        muxedaccountByDestinationMuxed {
          publickey
          muxedaccountid
        }
        muxedaccountBySourceMuxed {
          publickey
          muxedaccountid
        }
        ledgerByLedger {
          closeTime
          sequence
        }
        assetNative
      }
    }
  }
}
```

Sample response:

```json
{
  "data": {
    "paymentsToPublicKey": {
      "edges": [
        {
          "node": {
            "amount": "100000000",
            "assetByAsset": null,
            "accountByDestination": {
              "publickey": "GAHLLHMKSCZL4BQDS37KIRUXJVZBWOKQMHA5YOZIS52UOKAEW22YDSXX"
            },
            "accountBySource": {
              "publickey": "GAQX75URIUYBKEUWDWPRTFBMTW6ZWMAGDMC7IBBA6XWTIDYOSE5LRXLE"
            },
            "muxedaccountByDestinationMuxed": null,
            "muxedaccountBySourceMuxed": null,
            "ledgerByLedger": {
              "closeTime": 1697129852,
              "sequence": 1977611
            },
            "assetNative": true
          }
        }
      ]
    }
  }
}
```

As you can see, there are some `null` fields in our response, and it's perfectly normal.
This is because:
- in Mercury, when an asset is queried the response can include either:
   * assetNative: when `true` it means the asset sent is XLM
   * assetByAsset: the asset object for non-native assets. When the asset being sent is not
     xlm this field holds an object with the code and the issuer of the asset.
- The query is asking Mercury to look for payments that have been made:
  1. from an account to another
  2. from a muxed account to another muxed account
  3. from an account to a muxed account
  4. from a muxed account to an account.
For this payment we indexed, it's situation 1, so `muxedaccountByDestinationMuxed` and `muxedaccountBySourceMuxed`
are both null, but you can see the `accountBySource` and `accountByDestination` populated with
the receiver and destination public keys.

This data structure design makes queries very efficient on our end, and allows the client
to easily understand whether the asset sent is native or not, whether the source is muxed, etc.
