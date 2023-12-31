# Path payments (strict send)

### By account

```graphql
query FullQuery {
  pathPaymentsStrictReceiveByPublicKey(publicKeyText: "") {
    nodes {
      ledgerByLedger {
        closeTime
        sequence
      }
      accountBySource {
        publickey
      }
      accountByDestination {
        publickey
      }
      assetByDestAsset {
        code
        issuer
      }
      assetByPath1 {
        code
        issuer
      }
      assetByPath2 {
        code
        issuer
      }
      assetByPath3 {
        issuer
        code
      }
      assetByPath4 {
        issuer
        code
      }
      assetByPath5 {
        issuer
        code
      }
      assetBySendAsset {
        code
        issuer
      }
      destAssetNative
      path1Native
      path2Native
      path3Native
      path4Native
      path5Native
      sendAssetNative
      destAmount
      sendMax
    }
  }
}

```

### To account

```graphql
query FullQuery {
  pathPaymentsStrictReceiveToPublicKey(publicKeyText: "") {
    nodes {
      ledgerByLedger {
        closeTime
        sequence
      }
      accountBySource {
        publickey
      }
      accountByDestination {
        publickey
      }
      assetByDestAsset {
        code
        issuer
      }
      assetByPath1 {
        code
        issuer
      }
      assetByPath2 {
        code
        issuer
      }
      assetByPath3 {
        issuer
        code
      }
      assetByPath4 {
        issuer
        code
      }
      assetByPath5 {
        issuer
        code
      }
      assetBySendAsset {
        code
        issuer
      }
      destAssetNative
      path1Native
      path2Native
      path3Native
      path4Native
      path5Native
      sendAssetNative
      destAmount
      sendMax
    }
  }
}
```
