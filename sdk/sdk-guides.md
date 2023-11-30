---
description: Loopring SDK Initialize and Mock Data structure
---

# SDK Guides

### Quick Start

{% code lineNumbers="true" %}
```shell
# Using npm
npm i @loopring-web/loopring-sdk --save
# Using yarn
yarn add @loopring-web/loopring-sdk
```
{% endcode %}

### SDK Initialize

{% code lineNumbers="true" %}
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
{% endcode %}



### Connect Wallet

Suggestion web3 provider [#mock-provider](sdk-guides.md#mock-provider "mention")

{% code lineNumbers="true" %}
```shell
# Using npm
npm i @loopring-web/web3-provider --save
# Using yarn
yarn add @loopring-web/web3-provider
```
{% endcode %}

* [Demo Vue](https://codesandbox.io/s/vue-8nco78)
* [Demo React](https://codesandbox.io/s/react-4v50ft)

### Loopring ERC20 Data Structure

{% code overflow="wrap" lineNumbers="true" %}
```ts
const {tokensMap, idIndex, addressIndex} = LoopringAPI.exchangeAPI.getTokens();
```
{% endcode %}

[#mock-erc20-token-map](sdk-guides.md#mock-erc20-token-map "mention")

### Token Decimal

{% code overflow="wrap" lineNumbers="true" %}
```ts
const uiValue = 100;
const tradeValue = sdk.toBig(uiValue).times("1e" + TOKEN_INFO.tokenMap.LRC.decimals);
```
{% endcode %}

####
