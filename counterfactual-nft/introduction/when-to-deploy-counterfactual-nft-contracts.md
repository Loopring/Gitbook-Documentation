# When to deploy counterfactual NFT contracts?

If all the NFTs under a counterfactual NFT contract only ever stay on Layer 2, the contract will never need to be deployed. But Layer 1 deployment is necessary for the following transactions to be successful:

* An NFT is to be withdrawn to Layer 1.
* The owner wants to mint on Layer 1.

Deploying counterfactual NFT contracts is permissionless. The idea is that for someone to perform the above transactions, they will first have to deploy the contract at his/her own cost. It’s possible to interact with our factory contracts directly to deploy counterfactual NFT contracts. Loopring also provides an API so people can request for us to [deploy counterfactual NFT contracts](../sdk-guides/deploy-nft.md) on their behalf, but Layer 2 fees will apply.
