# Querying ledger entries

### Entries by contract id

```graphql
query EntriesByContractId {
  entryUpdateByContractId(
    contract: "CDSFM6YQ5PBC3QZT5CSJNMROM355RE2OFIWBMQZHEXBJGCQYJW6JFO75"
  ) {
    nodes {
      contractId
      entryDurability
      keyXdr
      ledger
      ledgerTimestamp
      valueXdr
    }
  }
}
```

#### Example response

```json
{
  "data": {
    "entryUpdateByContractId": {
      "nodes": [
        {
          "contractId": "CDSFM6YQ5PBC3QZT5CSJNMROM355RE2OFIWBMQZHEXBJGCQYJW6JFO75",
          "entryDurability": "PERSISTENT",
          "keyXdr": "AAAAFA==",
          "ledger": 2043931,
          "ledgerTimestamp": 1697478387,
          "valueXdr": "AAAAEwAAAABSupsyUp3yF//KIautJd9SeXc+dBHo/b5Q7dAU1R1gggAAAAEAAAACAAAAEAAAAAEAAAABAAAADwAAAAdUb2tlbklkAAAAABIAAAAB15KLcsJwPM/q9+uf9O9NUEpVqLl5/JtFDqLIQrTRzmEAAAAQAAAAAQAAAAEAAAAPAAAACVRvdFN1cHBseQAAAAAAAAoAAAAAAAAAAAAAAAAL68IA"
        },
        {
          "contractId": "CDSFM6YQ5PBC3QZT5CSJNMROM355RE2OFIWBMQZHEXBJGCQYJW6JFO75",
          "entryDurability": "PERSISTENT",
          "keyXdr": "AAAAEAAAAAEAAAACAAAADwAAABVGZWVQZXJTaGFyZVBhcnRpY3VsYXIAAAAAAAASAAAAAAAAAACWDGOVLdE2CRMRFy196IKuVS07K30ELNHi1EMNj3OYgQ==",
          "ledger": 2043931,
          "ledgerTimestamp": 1697478387,
          "valueXdr": "AAAACgAAAAAAAAAAAAAAAAAAAAA="
        },
        {
          "contractId": "CDSFM6YQ5PBC3QZT5CSJNMROM355RE2OFIWBMQZHEXBJGCQYJW6JFO75",
          "entryDurability": "PERSISTENT",
          "keyXdr": "AAAAEAAAAAEAAAACAAAADwAAAAdCYWxhbmNlAAAAABIAAAAAAAAAAJYMY5Ut0TYJExEXLX3ogq5VLTsrfQQs0eLUQw2Pc5iB",
          "ledger": 2043931,
          "ledgerTimestamp": 1697478387,
          "valueXdr": "AAAACgAAAAAAAAAAAAAAAAvrwgA="
        },
		....
	]
    }
  }
}
```

### Entries by contract id and data

```graphql
query EntriesByContractId {
  entryUpdateByContractIdAndKey(
    contract: "CDSFM6YQ5PBC3QZT5CSJNMROM355RE2OFIWBMQZHEXBJGCQYJW6JFO75"
    ledgerKey: "AAAAEAAAAAEAAAACAAAADwAAAAdCYWxhbmNlAAAAABIAAAAAAAAAAJYMY5Ut0TYJExEXLX3ogq5VLTsrfQQs0eLUQw2Pc5iB"
  ) {
    nodes {
      contractId
      entryDurability
      keyXdr
      ledger
      ledgerTimestamp
      valueXdr
    }
  }
}
```

#### Example response

```json
{
  "data": {
    "entryUpdateByContractIdAndKey": {
      "nodes": [
        {
          "contractId": "CDSFM6YQ5PBC3QZT5CSJNMROM355RE2OFIWBMQZHEXBJGCQYJW6JFO75",
          "entryDurability": "PERSISTENT",
          "keyXdr": "AAAAEAAAAAEAAAACAAAADwAAAAdCYWxhbmNlAAAAABIAAAAAAAAAAJYMY5Ut0TYJExEXLX3ogq5VLTsrfQQs0eLUQw2Pc5iB",
          "ledger": 2043931,
          "ledgerTimestamp": 1697478387,
          "valueXdr": "AAAACgAAAAAAAAAAAAAAAAvrwgA="
        },
        {
          "contractId": "CDSFM6YQ5PBC3QZT5CSJNMROM355RE2OFIWBMQZHEXBJGCQYJW6JFO75",
          "entryDurability": "PERSISTENT",
          "keyXdr": "AAAAEAAAAAEAAAACAAAADwAAAAdCYWxhbmNlAAAAABIAAAAAAAAAAJYMY5Ut0TYJExEXLX3ogq5VLTsrfQQs0eLUQw2Pc5iB",
          "ledger": 2061071,
          "ledgerTimestamp": 1697568458,
          "valueXdr": "AAAACgAAAAAAAAAAAAAAABHhowA="
        },
        {
          "contractId": "CDSFM6YQ5PBC3QZT5CSJNMROM355RE2OFIWBMQZHEXBJGCQYJW6JFO75",
          "entryDurability": "PERSISTENT",
          "keyXdr": "AAAAEAAAAAEAAAACAAAADwAAAAdCYWxhbmNlAAAAABIAAAAAAAAAAJYMY5Ut0TYJExEXLX3ogq5VLTsrfQQs0eLUQw2Pc5iB",
          "ledger": 2061140,
          "ledgerTimestamp": 1697568815,
          "valueXdr": "AAAACgAAAAAAAAAAAAAAABfXhAA="
        },
		...
	  ]
	  }
	}
}
```
