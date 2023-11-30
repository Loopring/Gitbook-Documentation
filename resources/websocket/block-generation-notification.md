---
description: Subscribe to this topic to receive notifications about Loopring L2 block.
---

# Block Generation Notification

### Rules <a href="#rules" id="rules"></a>

* Topic name: `blockgen`&#x20;
* ApiKey requred: No

### Parameters <a href="#parameters" id="parameters"></a>

This topic has an optional flag: `verbose`, which indicates the response has more info about the blocks or just the block id. Once the user gets the block id notification, they can also call getBlock REST API to get the details.

| Parameter | Required | Note                                       |
| --------- | -------- | ------------------------------------------ |
| verbose   | N        | Default is false, so only block Id returns |

Sub:

```json
{
  "op": "sub",
  "sequence": 30006,
  "unsubscribeAll": false,
  "topics": [
    {
      "topic": "blockgen"
    }
  ]
}
```

Response:

```json
{
  "op" : "sub",
  "sequence" : 30006,
  "topics" : [ {
    "topic" : "blockgen"
  } ],
  "result" : {
    "status" : "OK"
  }
}
```

### Notification example <a href="#notification-example" id="notification-example"></a>

```json
{
    "topic": {
        "topic:": "blockgen"
    },
    "ts":1584717910000,
    "data": {
    [
      {"blockid": 1},
      {"blockid": 2},
    ]
    }
}
```



### Data Model <a href="#data-model" id="data-model"></a>

**Notification**

<table><thead><tr><th>Field</th><th>Type</th><th>Note</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>topic</td><td>JSON</td><td>Topic and parameters</td><td>Y</td></tr><tr><td>ts</td><td>integer</td><td>Notification timestamp (milliseconds)</td><td>Y</td></tr><tr><td>data</td><td>[<a href="../layer-2-block-info/">BlockResp</a>]</td><td>Block generation messages, a list of BlockResp, refer to getBlock API for data format</td><td>Y</td></tr></tbody></table>
