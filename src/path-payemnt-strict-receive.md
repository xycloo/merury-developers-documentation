# Path payments (strict receive)

### From Account

```graphql
query FullQuery {
  pathPaymentsStrictSendByPublicKey(publicKeyText: "$PUBLIC_KEY") {
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
      destMin
      path1Native
      path2Native
      path3Native
      path4Native
      path5Native
      sendAmount
      sendAssetNative
    }
  }
}
```

### To Account

```graphql
query FullQuery {
  pathPaymentsStrictSendToPublicKey(publicKeyText: "$PUBLIC_KEY") {
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
      destMin
      path1Native
      path2Native
      path3Native
      path4Native
      path5Native
      sendAmount
      sendAssetNative
    }
  }
}
```
