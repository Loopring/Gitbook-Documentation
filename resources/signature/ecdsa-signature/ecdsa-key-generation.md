# ECDSA key generation

The **ECDSA key-pair** consists of:

* **private key** (integer): _**privKey**_
* **public key** (EC point): _**pubKey**_ = _**privKey**_ \* **G**

The **private key** is generated as a **random integer** in the range \[0..._**n**_-1]. The public key _**pubKey**_ is a point on the elliptic curve, calculated by the EC point multiplication: _**pubKey**_ = _**privKey**_ \* **G** (the private key, multiplied by the generator point **G**).

The public key EC point {_**x**_, _**y**_} can be **compressed** to just one of the coordinates + 1 bit (parity). For the `secp256k1` curve, the private key is 256-bit integer (32 bytes) and the compressed public key is 257-bit integer (\~ 33 bytes).

[Source](https://cryptobook.nakov.com/digital-signatures/ecdsa-sign-verify-messages)
