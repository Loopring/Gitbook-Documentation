---
description: >-
  Subscribe to this topic to receive notifications about candlestick updates for
  specific trading pairs.
---

# Candlestick Notification

### Rules <a href="#rules" id="rules"></a>

* Topic name: `candlestick`
* ApiKey required: No

### Parameters <a href="#parameters" id="parameters"></a>

<table><thead><tr><th>Parameter</th><th>Note</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>market</td><td><a href="https://docs.loopring.io/en/dex_apis/getMarkets.html">Trading pair</a></td><td>Y</td></tr><tr><td>interval</td><td>Time interval</td><td>Y</td></tr></tbody></table>

**Time intervals**

| Value | Note       |
| ----- | ---------- |
| 1min  | 1 minute   |
| 5min  | 5 minutes  |
| 15min | 15 minutes |
| 30min | 30 minutes |
| 1hr   | 1 hour     |
| 2hr   | 2 hours    |
| 4hr   | 4 hours    |
| 12hr  | 12 hours   |
| 1d    | 1 day      |
| 1w    | 1 week     |

### Status code <a href="#status-code" id="status-code"></a>

| Value  | Note                        |
| ------ | --------------------------- |
| 104106 | Invalid topic or parameters |

### Notification example <a href="#notification-example" id="notification-example"></a>

```json
{
    "topic": {
        "topic": "candlestick",
        "interval": "2hr"
    },
    "ts":1584717910000,
    "data": [
        "1584717910000",  //open timestamp (ms)
        "5000",  //count
        "3997.3",  //open
        "3998.7",  //close
        "4031.9",  //high
        "3982.5",  //low
        "500000000000000000",  //size
        "2617521141385000000",  //volume
    ]
}
```



### Data Model <a href="#data-model" id="data-model"></a>

**Notification**

<table><thead><tr><th>Field</th><th>Type</th><th>Note</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>topic</td><td>JSON</td><td>Topic and parameters</td><td>Y</td></tr><tr><td>ts</td><td>integer</td><td>Notification timestamp (milliseconds)</td><td>Y</td></tr><tr><td>data</td><td>List[string]</td><td><a href="https://docs.loopring.io/en/websocket/candlestick.html#candlestick"><code>Candlestick</code> array</a></td><td>Y</td></tr></tbody></table>

**Candlestick**

<table><thead><tr><th>Index</th><th>Type</th><th>Note</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>1</td><td>integer</td><td>Open timestamp</td><td>Y</td></tr><tr><td>2</td><td>integer</td><td>Nubmer of trades</td><td>Y</td></tr><tr><td>3</td><td>string</td><td>Open price</td><td>Y</td></tr><tr><td>4</td><td>string</td><td>Close price</td><td>Y</td></tr><tr><td>5</td><td>string</td><td>Highest price</td><td>Y</td></tr><tr><td>6</td><td>string</td><td>Lowest price</td><td>Y</td></tr><tr><td>7</td><td>string</td><td>Traded amount of Base Tokens (in Wei)</td><td>Y</td></tr><tr><td>8</td><td>string</td><td>Traded amount of quote Tokens (in Wei)</td><td>Y</td></tr></tbody></table>
