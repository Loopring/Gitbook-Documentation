---
description: Loopring supported markets
---

# Get markets info

## EndPoint

```
GET /api/v3/mix/markets
```



## Response

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>markets</td><td>List[<a href="./#marketinfo">MarketInfo</a>], Markets list</td><td>/</td><td>List[<a href="https://docs.loopring.io/en/dex_apis/getMixedMarkets.html#CombineMarketInfo">Combine<br>Market<br>Info</a>]</td><td>Y</td></tr></tbody></table>



## Model

### **MarketInfo**



<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>market</td><td>Trading pair ID</td><td>"LRC-USDT"</td><td>string</td><td>Y</td></tr><tr><td>baseTokenId</td><td>The base token ID</td><td>2</td><td>integer</td><td>Y</td></tr><tr><td>quoteTokenId</td><td>The quote token ID</td><td>0</td><td>integer</td><td>Y</td></tr><tr><td>precisionForPrice</td><td>The precision of price</td><td>6</td><td>integer</td><td>Y</td></tr><tr><td>orderbookAggLevels</td><td>The max level of orderbook price aggregation</td><td>4</td><td>integer</td><td>Y</td></tr><tr><td>enabled</td><td>True if trading is enabled for this trading pair</td><td>true</td><td>boolean</td><td>Y</td></tr><tr><td>status</td><td>status, bit0 means amm status, bit1 means orderbook status</td><td>3</td><td>integer</td><td>Y</td></tr><tr><td>createdAt</td><td>created timestamp</td><td>"160946640000<br>0"</td><td>string</td><td>Y</td></tr></tbody></table>
