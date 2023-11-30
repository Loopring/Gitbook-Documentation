---
description: >-
  Subscribe to this topic to receive notifications about new trades for specific
  trading pairs.
---

# Trade Notification

### Rules <a href="#rules" id="rules"></a>

* Topic name: `trade`
* ApiKey required: No

### Parameters <a href="#parameters" id="parameters"></a>

<table><thead><tr><th>Parameter</th><th>Note</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>market</td><td><a href="https://docs.loopring.io/en/dex_apis/getMarkets.html">Trading pair</a></td><td>Y</td></tr></tbody></table>

### Status code <a href="#status-code" id="status-code"></a>

| Value  | Note                        |
| ------ | --------------------------- |
| 104109 | Invalid topic or parameters |

### Notification example <a href="#notification-example" id="notification-example"></a>

```json
{
    "topic": {
        "topic": "trade",
        "market": "LRC-ETH"
    },
    "ts": 1584717910000,
    "data": [
        [
            "1584717910000",  //timestamp
            "123456789",  //tradeId
            "buy",  //side
            "500000",  //size 
            "0.0008",  //price
            "100"  //fee
        ]
    ]
}
```



### Data Model <a href="#data-model" id="data-model"></a>

**Notification**

<table><thead><tr><th>Field</th><th>Type</th><th>Note</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>topic</td><td>JSON</td><td>Topic and parameters</td><td>Y</td></tr><tr><td>ts</td><td>integer</td><td>Notification timestamp (milliseconds)</td><td>Y</td></tr><tr><td>data</td><td><a href="https://docs.loopring.io/en/websocket/trade.html#trade">List[List[string]</a>]</td><td>Trade array list</td><td>Y</td></tr></tbody></table>

**Trade**

<table><thead><tr><th>Index</th><th>Type</th><th>Note</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>1</td><td>integer</td><td>Trade timestamp</td><td>Y</td></tr><tr><td>2</td><td>integer</td><td>Fill sequence number</td><td>Y</td></tr><tr><td>3</td><td>string</td><td>Taker's side (buy or sell)</td><td>Y</td></tr><tr><td>4</td><td>string</td><td>Filled amount of base token</td><td>Y</td></tr><tr><td>5</td><td>string</td><td>Fill price</td><td>Y</td></tr><tr><td>6</td><td>string</td><td>Fee paid in base token</td><td>Y</td></tr></tbody></table>
