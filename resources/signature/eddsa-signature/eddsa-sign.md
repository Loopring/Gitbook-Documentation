# EdDSA sign

The **EdDSA signing** algorithm ([RFC 8032](https://tools.ietf.org/html/rfc8032#page-13)) takes as input a text message _**msg**_ + the signer's EdDSA **private key** _**privKey**_ and produces as output a pair of integers {_**R**_, _**s**_}. EdDSA signing works as follows (with minor simplifications):

`EdDSA_sign(msg, privKey) --> { R, s }`

1. Calculate _**pubKey**_ = _**privKey**_ \* **G**
2. Deterministically generate a secret integer _**r**_ = hash(hash(_**privKey**_) + _**msg**_) mod _**q**_ (this is a bit simplified)
3. Calculate the public key point behind _**r**_ by multiplying it by the curve generator: _**R**_ = _**r**_ \* **G**
4. Calculate _**h**_ = hash(_**R**_ + _**pubKey**_ + _**msg**_) mod _**q**_
5. Calculate _**s**_ = (_**r**_ + _**h**_ \* _**privKey**_) mod _**q**_
6. Return the **signature** { _**R**_, _**s**_ }

The produced **digital signature** is 64 bytes (32 + 32 bytes) for **Ed25519** and 114 bytes (57 + 57 bytes) for **Ed448**. It holds a compressed point _**R**_ + the integer _**s**_ (confirming that the signer knows the _**msg**_ and the _**privKey**_).

[Source](https://cryptobook.nakov.com/digital-signatures/eddsa-and-ed25519)
