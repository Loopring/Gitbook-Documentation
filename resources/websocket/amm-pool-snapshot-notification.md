---
description: >-
  Subscribe to this topic to receive notifications about token balance updates
  for specific AMM Pools.
---

# AMM Pool Snapshot Notification

### Rules <a href="#rules" id="rules"></a>

* Topic name: `ammpool`
* ApiKey requred: No
* <mark style="color:red;">**snapshot mode ONLY!**</mark>

### Parameters <a href="#parameters" id="parameters"></a>

<table><thead><tr><th>Parameter</th><th>Note</th><th data-hidden>Required</th><th data-hidden></th><th data-hidden></th></tr></thead><tbody><tr><td>poolAddress</td><td><a href="https://docs.loopring.io/en/dex_apis/getAmmPools.html">poolAddress</a></td><td>Y</td><td></td><td></td></tr></tbody></table>

### Status code <a href="#status-code" id="status-code"></a>

| Value  | Note                                  |
| ------ | ------------------------------------- |
| 102034 | receive illegal arg for topic ammpool |

### Notification example <a href="#notification-example" id="notification-example"></a>

```json
{
  "topic" : {
    "topic" : "ammpool",
    "poolAddress" : "0x18920d6E6Fb7EbE057a4DD9260D6D95845c95036",
    "snapshot" : true
  },
  "ts" : 1611267558234,
  "data" : [ [ "11792920485390000000000000", "3998385574130000000000" ], "41277091829000" ]

}
```



### Data Model <a href="#data-model" id="data-model"></a>

**Notification**

<table><thead><tr><th>Field</th><th>Type</th><th>Note</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>topic</td><td>JSON</td><td>Topic and parameters</td><td>Y</td></tr><tr><td>ts</td><td>integer</td><td>Notification timestamp (milliseconds)</td><td>Y</td></tr><tr><td>data</td><td>[[string, string], string]</td><td>Amm snapshot array</td><td>Y</td></tr></tbody></table>

**PoolSnapshot**

<table><thead><tr><th>Index</th><th>Type</th><th>Note</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>1</td><td>[string, string]</td><td>Token balance of in pool token pair, i.e. [base token amount, quote token amount]</td><td>Y</td></tr><tr><td>2</td><td>string</td><td>Token balance of pool's LP token</td><td>Y</td></tr></tbody></table>
