---
description: >-
  Subscribe to this topic to receive notifications about order updates for
  specific trading pairs.
---

# Order Notification

### Rules <a href="#rules" id="rules"></a>

* Topic name: `order`&#x20;
* ApiKey requred: Yes

### Parameters <a href="#parameters" id="parameters"></a>

<table><thead><tr><th>Parameter</th><th>Note</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>market</td><td><a href="https://docs.loopring.io/en/dex_apis/getMarkets.html">Trading pair</a></td><td>Y</td></tr></tbody></table>

### Status code <a href="#status-code" id="status-code"></a>

| Value  | Note                        |
| ------ | --------------------------- |
| 104110 | Invalid topic or parameters |

### Notification example <a href="#notification-example" id="notification-example"></a>

```json
{
   "topic": {
        "topic": "order",
        "market": "LRC-ETH"
   },
   "ts":1565844328,
   "data": {
        "hash": "11212",
        "clientOrderId": "myOrder",
        "size": "500000000",
        "volume": "210000000",
        "price": "0.000004",
        "filledSize": "30000000",
        "filledVolume": "100000",
        "filledFee": "1000000",
        "status": "processing",
        "createdAt": "1494900087",
        "validSince": "1494900087",
        "validUntil": "1495900087",
        "side": "buy",
        "market": "LRC-ETH"
    }
}
```



### Data Model <a href="#data-model" id="data-model"></a>

#### **Notification**

<table><thead><tr><th>Field</th><th>Type</th><th>Note</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>topic</td><td>JSON</td><td>Topic and parameters</td><td>Y</td></tr><tr><td>ts</td><td>integer</td><td>Notification timestamp (milliseconds)</td><td>Y</td></tr><tr><td>data</td><td><a href="order-notification.md#order">Order</a></td><td>The order</td><td>Y</td></tr></tbody></table>

#### **Order**

<table><thead><tr><th>Field</th><th>Type</th><th>Note</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>hash</td><td>string</td><td>Order hash</td><td>Y</td></tr><tr><td>clientOrderId</td><td>string</td><td>Client defined order ID</td><td>Y</td></tr><tr><td>size</td><td>string</td><td>Amount (quantity of base token)</td><td>Y</td></tr><tr><td>volume</td><td>string</td><td>Total (quantity of quote token)</td><td>Y</td></tr><tr><td>price</td><td>string</td><td>Order price</td><td>Y</td></tr><tr><td>filledSize</td><td>string</td><td>Filled amount of base token</td><td>Y</td></tr><tr><td>filledVolume</td><td>string</td><td>Filled amount of quote token</td><td>Y</td></tr><tr><td>filledFee</td><td>string</td><td>Fees paid</td><td>Y</td></tr><tr><td>status</td><td>string</td><td>Order status</td><td>Y</td></tr><tr><td>createdAt</td><td>integer</td><td>Order creation timestamp</td><td>Y</td></tr><tr><td>updateAt</td><td>integer</td><td>Order last update timestamp</td><td>Y</td></tr><tr><td>side</td><td>string</td><td>Buy or sell</td><td>Y</td></tr><tr><td>market</td><td>string</td><td>Trading pair</td><td>Y</td></tr></tbody></table>

#### **Order status**

| Value      | Note                                       |
| ---------- | ------------------------------------------ |
| processing | Active (aka Open, may be partially filled) |
| processed  | Fully filled                               |
| cancelling | Being cancelled                            |
| cancelled  | Cancelled                                  |
| expired    | Expired                                    |
| waiting    | Pending active                             |
