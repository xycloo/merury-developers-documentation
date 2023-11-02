# Create passive sell offer

```graphql
query FullQuery {
  createPassiveSellOfferByPublicKey(publicKeyText: "$PUBLIC_KEY") {
    nodes {
      accountBySource {
        publickey
      }
      amount
      assetByBuying {
        code
        issuer
      }
      assetBySelling {
        code
        issuer
      }
      buyingNative
      ledgerByLedger {
        closeTime
        sequence
      }
      muxedaccountBySourceMuxed {
        id
        publickey
      }
      priceD
      priceN
      sellingNative
    }
  }
}

```
n
