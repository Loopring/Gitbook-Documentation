# EdDSA verify signature

The **EdDSA signature verification** algorithm ([RFC 8032](https://tools.ietf.org/html/rfc8032#page-13)) takes as input a text message _**msg**_ + the signer's EdDSA **public key** _**pubKey**_ + the EdDSA signature {_**R**_, _**s**_} and produces as output a boolean value (valid or invalid signature). EdDSA verification works as follows (with minor simplifications):

`EdDSA_signature_verify(msg, pubKey, signature { R, s } ) --> valid / invalid`

1. Calculate _**h**_ = hash(_**R**_ + _**pubKey**_ + _**msg**_) mod _**q**_
2. Calculate _**P1**_ = _**s**_ \* **G**
3. Calculate _**P2**_ = _**R**_ + _**h**_ \* _**pubKey**_
4. Return _**P1**_ == _**P2**_

[Source](https://cryptobook.nakov.com/digital-signatures/eddsa-and-ed25519)
