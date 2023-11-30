---
description: >-
  Subscribe to this topic to receive notifications about ticker updates for
  specific trading pairs.
---

# Ticker Notification

### Rules

* Topic name: `ticker`
* ApiKey requred: No

### Parameters <a href="#parameters" id="parameters"></a>

<table><thead><tr><th>Parameter</th><th>Note</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>market</td><td><a href="https://docs.loopring.io/en/dex_apis/getMarkets.html">Trading pair</a></td><td>Y</td></tr></tbody></table>

### Status code <a href="#status-code" id="status-code"></a>

| Value  | Note                        |
| ------ | --------------------------- |
| 104111 | Invalid topic or parameters |

### Notification example <a href="#notification-example" id="notification-example"></a>

```json
{
    "topic": {
        "topic": "ticker",
        "market": "LRC-ETH"
    },
    "ts": 1584717910000,
    "data": [
        "LRC-ETH",  //market
        "1584717910000",  //timestamp
        "5000000",  //size
        "1000",  //volume
        "0.0002",  //open
        "0.00025",  //high
        "0.0002",  //low
        "0.00025",  //close       
        "5000",  //count    
        "0.00026",  //bid
        "0.00027"  //ask
    ]
}
```



### Data Model <a href="#data-model" id="data-model"></a>

**Notification**

<table><thead><tr><th>Field</th><th>Type</th><th>Note</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>topic</td><td>JSON</td><td>Topic and parameters</td><td>Y</td></tr><tr><td>ts</td><td>integer</td><td>Notification timestamp (milliseconds)</td><td>Y</td></tr><tr><td>data</td><td><a href="https://docs.loopring.io/en/websocket/ticker.html#ticker">List[string]</a></td><td>Ticker array</td><td>Y</td></tr></tbody></table>

**Ticker**

<table><thead><tr><th>Index</th><th>Type</th><th>Note</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>1</td><td>string</td><td>Trading pair</td><td>Y</td></tr><tr><td>2</td><td>integer</td><td>Ticker update timestamp</td><td>Y</td></tr><tr><td>3</td><td>string</td><td>Amount (quantity of base token)</td><td>Y</td></tr><tr><td>4</td><td>string</td><td>Total (quantity of quote token)</td><td>Y</td></tr><tr><td>5</td><td>string</td><td>Open price</td><td>Y</td></tr><tr><td>6</td><td>string</td><td>Highest price</td><td>Y</td></tr><tr><td>7</td><td>string</td><td>Lowest price</td><td>Y</td></tr><tr><td>8</td><td>string</td><td>Latest price</td><td>Y</td></tr><tr><td>9</td><td>integer</td><td>Number of trades</td><td>Y</td></tr><tr><td>10</td><td>string</td><td>Highest bid price</td><td>Y</td></tr><tr><td>11</td><td>string</td><td>Lowest ask price</td><td>Y</td></tr></tbody></table>
