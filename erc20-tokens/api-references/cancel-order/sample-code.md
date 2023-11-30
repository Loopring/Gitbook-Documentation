# Sample code

### Header

```
X-API-KEY = bEef7a3Nzk7lgaHm85E0O1JO5ufu0iQ96p3bCmrsZz8TLGG83jTpPDYwcjUC0vlF
X-API-SIG = 0xeb14773e8a07d19bc4fe56e36d041dcb0026bf21e05c7652f7e92160deaf5ea9c4fe56e34773e86d041dcbeb1a07d19b002652f7e92160deaf5e6bf21e05c7a9002652f7e92160deaf5e6bf21e05c7a9eb14773e8a07d19bc4fe56e36d041dcb
```



### Request

{% code overflow="wrap" %}
```
DELETE  api/v3/order?accountId=10010&orderHash=0x05a97490e92ded027f65c4bebf3bad63813f4ce8c7255335894566b2eee90206 
```
{% endcode %}



### Response

```
{
	"hash": "0x05a97490e92ded027f65c4bebf3bad63813f4ce8c7255335894566b2eee90206",
	"clientOrderId": "Test",
	"status": "processing",
	"isIdempotent": false
}
```
