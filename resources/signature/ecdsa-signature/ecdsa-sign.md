# ECDSA sign

The ECDSA signing algorithm ([RFC 6979](https://www.rfc-editor.org/rfc/rfc6979#section-3.2)) takes as input a message _**msg**_ \*\*\*\*+ a private key _**privKey**_ \*\*\*\*and produces as output a **signature**, which consists of pair of integers {_**r**_, _**s**_}. The **ECDSA signing** algorithm is based on the [ElGamal signature scheme](https://en.wikipedia.org/wiki/ElGamal\_signature\_scheme) and works as follows (with minor simplifications):

1. Calculate the message **hash**, using a cryptographic hash function like SHA-256: _**h**_ = hash(_**msg**_)
2. Generate securely a **random** number _**k**_ in the range \[1.._**n**_-1]
   * In case of **deterministic-ECDSA**, the value _**k**_ is HMAC-derived from _**h**_ + _**privKey**_ (see [RFC 6979](https://www.rfc-editor.org/rfc/rfc6979#section-3.2))
3. Calculate the random point _**R**_ = _**k**_ \* **G** and take its x-coordinate: _**r**_ = _**R**_**.x**
4. Calculate the signature proof: _**s**_ = $$k^{-1} * (h + r * privKey) \pmod n$$
   * The modular inverse $$k^{-1} \pmod n$$ is an integer, such that $$k * k^{-1} \equiv 1 \pmod n$$
5. Return the **signature** {_**r**_, _**s**_}.

The calculated **signature** {_**r**_, _**s**_} is a pair of integers, each in the range \[1..._**n**_-1]. It encodes the random point _**R**_ = _**k**_ \* **G**, along with a proof _**s**_, confirming that the signer knows the message _**h**_ and the private key _**privKey**_. The proof _**s**_ is by idea verifiable using the corresponding _**pubKey**_.

**ECDSA signatures** are **2 times longer** than the signer's **private key** for the curve used during the signing process. For example, for 256-bit elliptic curves (like `secp256k1`) the ECDSA signature is 512 bits (64 bytes) and for 521-bit curves (like `secp521r1`) the signature is 1042 bits.

[Source](https://cryptobook.nakov.com/digital-signatures/ecdsa-sign-verify-messages)
