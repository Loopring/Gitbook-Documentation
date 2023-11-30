---
description: >-
  Subscribe to this topic to receive notifications about orderbook updates for
  specific trading pairs.
---

# Orderbook Notification

### Rules <a href="#rules" id="rules"></a>

* Topic name: `orderbook`
* ApiKey requred: No

### Parameters <a href="#parameters" id="parameters"></a>

<table><thead><tr><th>Parameter</th><th>Note</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>market</td><td><a href="https://docs.loopring.io/en/dex_apis/getMarkets.html">Trading pair</a></td><td>Y</td></tr><tr><td>level</td><td>Price aggregation level</td><td>Y</td></tr><tr><td>count</td><td>Number of bids/ask price slots, count can not be larger than 50, and only take effect when snapshot is true.</td><td>N</td></tr><tr><td>snapshot</td><td>Default to false. If true, the client will receive full notification with up to <code>count</code> bid/ask price slots when at least one slot has update.</td><td>N</td></tr></tbody></table>

### Status code <a href="#status-code" id="status-code"></a>

| Value  | Note                        |
| ------ | --------------------------- |
| 104107 | Invalid topic or parameters |

### Notification example <a href="#notification-example" id="notification-example"></a>

```json
{
    "topic": {
        "topic:": "orderbook",
        "market": "LRC-USDT",
          "level": 0
    },
    "ts": 1584717910000,
    "startVersion": 1212121,
    "endVersion": "1212123",
    "data": {
        "bids": [
            [
                "295.97",  //price
                "456781000000000",  //size
                "3015000000000",  //volume
                "4"  //count
            ]
        ],
        "asks": [
            [
              "298.97",
              "456781000000000000",
              "301500000000000",
              "2"
            ]
        ]
    }
}
```



### Data Model <a href="#data-model" id="data-model"></a>

#### **Notification**

<table><thead><tr><th>Field</th><th>Type</th><th>Note</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>topic</td><td>JSON</td><td>Topic and parameters</td><td>Y</td></tr><tr><td>ts</td><td>integer</td><td>Notification timestamp (milliseconds)</td><td>Y</td></tr><tr><td>startVersion</td><td>integer</td><td>Previous version number</td><td>Y</td></tr><tr><td>endVersion</td><td>integer</td><td>Updated versionnumber</td><td>Y</td></tr><tr><td>data</td><td><a href="orderbook-notification.md#orderbook">OrderBook</a></td><td>The orderbook</td><td>Y</td></tr></tbody></table>

#### **OrderBook**

<table><thead><tr><th>Field</th><th>Type</th><th>Note</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>bids</td><td>List[List[string]]</td><td><a href="orderbook-notification.md#priceslot">PriceSlot</a> array for bids</td><td>Y</td></tr><tr><td>asks</td><td>List[List[string]]</td><td><a href="orderbook-notification.md#priceslot">PriceSlot</a> array for asks</td><td>Y</td></tr></tbody></table>

#### **PriceSlot**

<table><thead><tr><th>Index</th><th>Type</th><th>Note</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>1</td><td>string</td><td>Price</td><td>Y</td></tr><tr><td>2</td><td>string</td><td>Amount (quantity of base token)</td><td>Y</td></tr><tr><td>3</td><td>string</td><td>Total (quantity of quote token)</td><td>Y</td></tr><tr><td>4</td><td>string</td><td>Number of orders at this price</td><td>Y</td></tr></tbody></table>

{% hint style="warning" %}
Note that amount and total are the current values, not the delta between the current and the previous values.
{% endhint %}
