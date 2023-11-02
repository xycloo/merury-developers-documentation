# Manage sell offer

```graphql
query FullQuery {
  manageSellOfferByPublicKey(
    publicKeyText: "$PUBLIC_KEY"
  ) {
    edges {
      node {
        buyingNative
        accountBySource {
          publickey
        }
        assetByBuying {
          issuer
          code
        }
        assetBySelling {
          code
          issuer
        }
        ledgerByLedger {
          closeTime
          sequence
        }
        muxedaccountBySourceMuxed {
          id
          publickey
        }
        offerId
        priceD
        priceN
        sellingNative
      }
    }
  }
}
```
