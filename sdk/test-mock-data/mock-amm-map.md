# Mock AMM MAP

{% code lineNumbers="true" %}
```ts
export let AMM_MAP = {
  "AMM-LRC-ETH": {
    name: "LRCETH-Pool",
    market: "AMM-LRC-ETH",
    address: "0xfEB069407df0e1e4B365C10992F1bc16c078E34b",
    version: "1.0.0",
    tokens: { pooled: [1, 0], lp: 4 },
    feeBips: 20,
    precisions: { price: 6, amount: 5 },
    createdAt: "1617967800000",
    status: 31,
  },
  "AMM-ETH-USDT": {
    name: "AMM-ETH-USDT",
    market: "AMM-ETH-USDT",
    address: "0x049a02FA9bc6bd54a2937E67D174cc69a9194f8e",
    version: "1.0.0",
    tokens: { pooled: [0, 2], lp: 7 },
    feeBips: 20,
    precisions: { price: 3, amount: 3 },
    createdAt: "1617972300000",
    status: 31,
  },
  "AMM-USDC-ETH": {
    name: "AMM-USDC-ETH",
    market: "AMM-USDC-ETH",
    address: "0xf37cf4CEd77b985708D591AcC6BfD08586Ab3409",
    version: "1.0.0",
    tokens: {
      pooled: [8, 0],
      lp: 9,
    },
    feeBips: 20,
    precisions: {
      price: 3,
      amount: 4,
    },
    createdAt: "1636974420000",
    status: 0,
  },
};
```
{% endcode %}
