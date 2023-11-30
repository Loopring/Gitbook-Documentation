---
description: >-
  Loopring SDK supports EOA (EOA hardware wallet) & Loopring Smart Wallet
  signature
---

# SDK Signature

### &#x20;Environment  type   &#x20;

* For Browser extension, Dapp, and hardware wallet we only support EOA
* For Loopring smart wallet (App), the provider gateway is WalletConnect



### The following are the provider gateways we inject & test:

* MetaMask (Ledger, Trezor)
* WalletConnect (Authereum, Loopring smart wallet )
* Coinbase



### For signature:

> &#x20;Understand  what is  [`eth_sign signing types`](https://docs.metamask.io/guide/signing-data.html#a-brief-history) (eth\_sign, personal\_sign, v1, v3, v4)
>
> ❗ when adding `SigSuffix` `02|03` (please follow:  `EIP712` & `signTypedData_v4`  + `02`, `personal_sign` + `03`)
>
> * for `v4` ecdsaSignature, the result signature should + `SigSuffix.Suffix02`;
> * for `personal_sign` ecdsaSignature the result signature should + `SigSuffix.Suffix03`;

#### EOA:

* For Browser extension ([More information: signing-data](https://docs.metamask.io/guide/signing-data.html#a-brief-history))
  * common EOA: we use the `v4` signature and `web3.eth.personal.ecRecover` validate signature
  * when `v4` signature fails for any step, we will try `personal_sign` and `web3.eth.personal.ecRecover` validate signature
* For Dapp
  * when loopring DEX is inside Dapp Webview & connect by `window.ethereum`, we remove the `web3.eth.personal.ecRecover` validate

#### Loopring smart wallet:

* For Loopring smart wallet we send `eth_signTypedData` by WalletConnect & validate ABI.Contracts.ContractWallet.encodeInputs `isValidSignature(bytes32,bytes)`

#### Loopring counterfactual wallet:

* signature is same as Loopring smart wallet
* But ecRecover is by walletOwner, `const {walletOwner} = await LoopringAPI.exchangeAPI.getCounterFactualInfo({ accountId: LOOPRING_EXPORTED_ACCOUNT.accountIdCF, });`



### Validate signature

[github: src/api/base\_api.ts#personalSign](https://github.com/Loopring/loopring\_sdk/blob/2c79c1837114f4f383e2d292de3da4b2dac02252/src/api/base\_api.ts#L549)

```
 export async function personalSign(
  web3: any,
  account: string | undefined,
  pwd: string,
  msg: string,
  walletType: ConnectorNames,
  chainId: ChainId,
  accountId?: number,
  counterFactualInfo?: CounterFactualInfo,
  isMobile?: boolean
) {
  if (!account) {
    return { error: "personalSign got no account" };
  }

  return new Promise((resolve) => {
    try {
      web3.eth.personal.sign(
        msg,
        account,
        pwd,
        async function (err: any, result: any) {
          if (!err) {
            // Valid:1. counter Factual signature Valid
            if (counterFactualInfo && accountId) {
              myLog("fcWalletValid counterFactualInfo accountId:");
              const fcValid = await fcWalletValid(
                web3,
                account,
                msg,
                result,
                accountId,
                chainId,
                counterFactualInfo
              );
              if (fcValid.result) {
                resolve({
                  sig: result,
                  counterFactualInfo: fcValid.counterFactualInfo,
                });
                return;
              }
            }

            // Valid: 2. webview directory signature Valid
            if (
              (window?.ethereum?.isImToken || window?.ethereum?.isMetaMask) &&
              isMobile &&
              // Mobile directory connect will sign ConnectorNames as MetaMask only
              walletType === ConnectorNames.MetaMask
            ) {
              const address: string[] = await window.ethereum?.request({
                method: "eth_requestAccounts",
              });
              if (
                address?.find(
                  (item) => item.toLowerCase() === account.toLowerCase()
                )
              ) {
                return resolve({ sig: result });
              }
            }

            // Valid: 3. EOA signature Valid by ecRecover
            const valid: any = await ecRecover(web3, account, msg, result);
            if (valid.result) {
              return resolve({ sig: result });
            }

            // Valid: 4. contractWallet signature Valid `isValidSignature(bytes32,bytes)`
            const walletValid2: any = await contractWalletValidate32(
              web3,
              account,
              msg,
              result
            );

            if (walletValid2.result) {
              return resolve({ sig: result });
            }

            // Valid: 5. counter Factual signature Valid when no counterFactualInfo
            if (accountId) {
              const fcValid = await fcWalletValid(
                web3,
                account,
                msg,
                result,
                accountId,
                chainId
              );
              if (fcValid.result) {
                return resolve({
                  sig: result,
                  counterFactualInfo: fcValid.counterFactualInfo,
                });
              }
            }

            // Valid: 6. myKeyValid Valid again
            const myKeyValid: any = await mykeyWalletValid(
              web3,
              account,
              msg,
              result
            );

            if (myKeyValid.result) {
              return resolve({ sig: result });
            }

            // Valid: Error cannot pass personalSign Valid
            // eslint-disable-next-line no-console
            console.log(
              "web3.eth.personal.sign Valid, valid 5 ways, all failed!"
            );
            return resolve({
              error: "web3.eth.personal.sign Valid, valid 5 ways, all failed!",
            });
          } else {
            return resolve({
              error: "personalSign err before Validate:" + err,
            });
          }
        }
      );
    } catch (reason) {
      resolve({ error: reason });
    }
  });
}
```
