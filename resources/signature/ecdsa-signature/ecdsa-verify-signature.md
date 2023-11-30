# ECDSA verify signature

The algorithm to **verify a ECDSA signature** takes as input the signed message _**msg**_ + the signature {_**r**_, _**s**_} produced from the signing algorithm + the public key _**pubKey**_, corresponding to the signer's private key. The output is boolean value: _**valid**_ or _**invalid**_ signature. The **ECDSA signature verify** algorithm works as follows (with minor simplifications):

1. Calculate the message **hash**, with the same cryptographic hash function used during the signing: _**h**_ = hash(_**msg**_)
2. Calculate the modular inverse of the signature proof: _**s1**_ = $$s^{-1} \pmod n$$
3. Recover the random point used during the signing: _**R'**_ = (_**h**_ \* **s1**) \* **G** + (_**r**_ \* _**s1**_) \* _**pubKey**_
4. Take from _**R'**_ its x-coordinate: _**r'**_ = _**R'**_**.x**
5. Calculate the signature validation **result** by comparing whether _**r'**_ == _**r**_

The general idea of the signature verification is to **recover the point** _**R'**_ using the public key and check whether it is same point _**R**_, generated randomly during the signing process.

[Source](https://cryptobook.nakov.com/digital-signatures/ecdsa-sign-verify-messages)
