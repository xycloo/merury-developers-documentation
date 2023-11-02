# Change trust

```graphql
query FullQuery {
  changeTrustByPublicKey(publicKeyText: "$PUBLIC_KEY") {
    nodes {
      accountBySource {
        publickey
      }
      assetByLineAsset {
        issuer
        code
      }
      ledgerByLedger {
        closeTime
        sequence
      }
      limit
      lineNative
      poolshareByLinePoolShare {
        assetA
        assetB
        fee
      }
    }
  }
}
```
