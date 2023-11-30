# ECDSA signature

## Two types of signature supported&#x20;

* EIP712
* EthSign



### EIP712

This signature type is best for web frontends that present an order to be signed through Metamask in a human-readable format. It relies on the <mark style="color:green;">eth\_signTypedData JSON-RPC</mark> method exposed by MetaMask. This signature has the `signatureType` of <mark style="color:red;">2</mark>.



### EthSign

This signature is best for use with headless providers, such as when using a geth node. This relies on the <mark style="color:green;">eth\_sign JSON-RPC</mark> method common to all nodes. This signature has the `signatureType` of <mark style="color:red;">3</mark>.
