# Manage buy offer

```graphql
query FullQuery {
  manageBuyOfferByPublicKey(
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
