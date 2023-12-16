# Request signing

The Loopring API involves two different categories of signatures.&#x20;

* API Request Signature - is used to verify that the API invocations have been authenticated
* Off-chain Request Signature - is used by Loopring to verify that off-chain requests have been authenticated. We will explain each of these two categories separately.

{% hint style="info" %}
### References <a href="#references" id="references"></a>

You can learn more about the Poseidon hash and EdDSA signature through the following literature and github repositories.

1. **ethsnarks**: [https://github.com/HarryR/ethsnarks.git](https://github.com/HarryR/ethsnarks.git)
2. **SHA256 Hash**: [https://en.wikipedia.org/wiki/SHA-2](https://en.wikipedia.org/wiki/SHA-2)
3. **EdDSA**: [https://en.wikipedia.org/wiki/EdDSA](https://en.wikipedia.org/wiki/EdDSA)
4. **Poseidon Hash**: [https://www.poseidon-hash.info/](https://www.poseidon-hash.info/)

You can also refer to our [example code](https://docs-protocol.loopring.io/sdk/sdk-guides) for more details.
{% endhint %}

### &#x20;<a href="#references" id="references"></a>
