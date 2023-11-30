# Compute NFT Address API

You can compute counterfactual NFT addresses by interacting with the factory smart contract. We also provide an API for convenience.

**Endpoint**: `/api/v3/nft/info/computeTokenAddress` \
\
**Parameters**:

1. _nftFactory_ : the official NFT factory address.
2. _nftOwner_ : the owner address.
3. _nftBaseUri_ : this is to support another feature in the future, but is currently not supported.



An example: [ ](https://uat2.loopring.io/api/v3/nft/info/computeTokenAddress?nftFactory=0x25315F9878BA07221db684b7ad3676502E914894\&nftOwner=0xE20cF871f1646d8651ee9dC95AAB1d93160b3467\&nftBaseUri)[https://uat2.loopring.io/api/v3/nft/info/computeTokenAddress?nftFactory=0x0ad87482a1bfd0B3036Bb4b13708C88ACAe1b8bA\&nftOwner=0xE20cF871f1646d8651ee9dC95AAB1d93160b3467\&nftBaseUri](https://uat2.loopring.io/api/v3/nft/info/computeTokenAddress?nftFactory=0x0ad87482a1bfd0B3036Bb4b13708C88ACAe1b8bA\&nftOwner=0xE20cF871f1646d8651ee9dC95AAB1d93160b3467\&nftBaseUri)

returns:

```
{
  tokenAddress: "0xc00cb8d1f71b00c1bb54a1a7233fe6a1c9c65a00"
}
```
