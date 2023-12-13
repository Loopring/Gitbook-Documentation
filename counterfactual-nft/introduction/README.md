# Introduction

{% hint style="info" %}
Loopring announced NFT support in protocol release (v3.6.2). Since then, further enhancements have been made to NFT support on Loopring. NFT contracts no longer need to be deployed on Ethereum before being minted, transferred, and traded on Loopring. This new type of NFT is called a [_<mark style="color:blue;">`Counterfactual NFT`</mark>_](https://loopring-1.gitbook.io/loopring-university/create-your-nft/minting-nft-on-loopring/requirements-when-minting)<mark style="color:blue;">.</mark>
{% endhint %}

## **How is it implemented?**

First, we use `CREATE2` to calculate the counterfactual NFT’s smart contract address that can be deployed on Ethereum L1 later. All we need are:

* A counterfactual NFT factory (`factory` ) that will deploy the actual NFT contract for us when necessary. Deploying a new NFT contract is simply creating a new proxy instance that delegates all logic to a concrete counterfactual NFT implementation.
* The NFT contract’s owner address (`owner` ). The owner is also the only account allowed to mint the NFT on Loopring Layer 2 under this contract.

The following code sample demonstrates how to calculate the contract address. You can refer to [our GitHub repo](https://github.com/Loopring/Gitbook-Documentation) for more details on the contract implementation.

```
Create2Upgradeable.computeAddress(               
 keccak256(abi.encodePacked(NFT_CONTRACT_CREATION, owner, baseURI)),
 keccak256(CloneFactory.getByteCode(implementation))
);
```

{% hint style="info" %}
Loopring only supports our own _NFTFactory_ implementation. On Ethereum mainnet, our official _NFTFactory_ address is `0xc852aC7aAe4b0f0a0Deb9e8A391ebA2047d80026`; on Goerli testnet, the address is 0x0ad87482a1bfd0B3036Bb4b13708C88ACAe1b8bA. Third-party counterfactual NFT factories can implement our factory method.
{% endhint %}

##

##
