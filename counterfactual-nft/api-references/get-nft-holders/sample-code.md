# Sample code

### Header

```
X-API-KEY = l4hd4CGLLGuZ9nEultG4sfhQZDjPp9sv0kMy13cyGgkJyIWDodVSM4S4ucb5WFKN
Request
```

### Request

```
GET  api/v3/user/nft/info/nftHolders

https://uat2.loopring.io/api/v3/nft/info/nftHolders?nftData=0x0e19fcee373a003b77bd0fbcd15c406f092c7961106be08d31a3864d4eba9ee2
```

### Response

<pre><code>{
	"totalNum": 1,
	"nftHolders": [{
		accountId": 10388,
<strong>		"address": "0x72aa8A62087348c4a67EcaE15370f34586a7553E",
</strong>		"tokenId": 32783,
		"amount": "123"	
	}]
}
</code></pre>
