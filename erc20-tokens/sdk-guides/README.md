---
description: Loopring SDK Initialize and Mock Data structure
---

# SDK Guides

### Quick Start

```shell
# Using npm
npm i @loopring-web/loopring-sdk --save
# Using yarn
yarn add @loopring-web/loopring-sdk
```

### SDK Initialize

```ts
import * as sdk from "../index";
export class LoopringAPIClass {
  public static userAPI: UserAPI;
  public static exchangeAPI: ExchangeAPI;
  public static ammpoolAPI: AmmpoolAPI;
  public static walletAPI: WalletAPI;
  public static wsAPI: WsAPI;
  public static nftAPI: NFTAPI;
  public static delegate: DelegateAPI;
  public static globalAPI: GlobalAPI;
  public static contractAPI: typeof ContractAPI;
  public static __chainId__: sdk.ChainId;
  public static InitApi = (chainId: sdk.ChainId) => {
    LoopringAPI.userAPI = new UserAPI({ chainId });
    LoopringAPI.exchangeAPI = new ExchangeAPI({ chainId });
    LoopringAPI.globalAPI = new GlobalAPI({ chainId });
    LoopringAPI.ammpoolAPI = new AmmpoolAPI({ chainId });
    LoopringAPI.walletAPI = new WalletAPI({ chainId });
    LoopringAPI.wsAPI = new WsAPI({ chainId });
    LoopringAPI.nftAPI = new NFTAPI({ chainId });
    LoopringAPI.delegate = new DelegateAPI({ chainId });
    LoopringAPI.__chainId__ = chainId;
    LoopringAPI.contractAPI = ContractAPI;
  };
}
/* env:
 * test:  sdk.ChainId.GOERLI 
 * eth:  sdk.ChainId.MAINNET 
 */
LoopringAPIClass.InitApi({sdk.ChainId.MAINNET}); 
```



### Connect Wallet

Suggestion web3 provider [#mock-provider](./#mock-provider "mention")

```shell
# Using npm
npm i @loopring-web/web3-provider --save
# Using yarn
yarn add @loopring-web/web3-provider
```

* [Demo Vue](https://codesandbox.io/s/vue-8nco78)
* [Demo React](https://codesandbox.io/s/react-4v50ft)

### Loopring ERC20 Data Structure

```ts
const {tokensMap, idIndex, addressIndex} = LoopringAPI.exchangeAPI.getTokens();
```

### Token Decimal

```ts
const uiValue = 100;
const tradeValue = sdk.toBig(uiValue).times("1e" + TOKEN_INFO.tokenMap.LRC.decimals);
```

###
