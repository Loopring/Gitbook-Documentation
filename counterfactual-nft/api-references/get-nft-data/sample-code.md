# Sample code

### Header

```
X-API-KEY = l4hd4CGLLGuZ9nEultG4sfhQZDjPp9sv0kMy13cyGgkJyIWDodVSM4S4ucb5WFKN
Request
```

### Request

```
GET  api/v3/user/nft/info/nftData

https://uat2.loopring.io/api/v3/nft/info/nftData?minter=0xd841b2b80b616f0a3e124f0ed8611743e8becfae&tokenAddress=0x43dc24584f1ab1c23d391c7b93ab0b8d33dda52f&nftId=0x710584dd9f17f0eb13c2177aa118ac6001d47e973813770fa6ad614392faa743
```

### Response

```
{
	"nftData": "0x08773861a52fff62d5a76024912cca97015fcb1a838e35607d9029355f8e09e9",
	"minter": "0xd841b2b80b616f0a3e124f0ed8611743e8becfae",
	"nftType": "ERC1155",
	"tokenAddress": "0x43dc24584f1ab1c23d391c7b93ab0b8d33dda52f",
	"nftId": "0x710584dd9f17f0eb13c2177aa118ac6001d47e973813770fa6ad614392faa743",
	"creatorFeeBips": 10,
	"royaltyPercentage": 10,
	"status": true,
	"nftFactory": "0x25315F9878BA07221db684b7ad3676502E914894",
	"nftOwner": "0xd841b2b80b616f0a3e124f0ed8611743e8becfae",
	"nftBaseUri": "",
	"royaltyAddress": "0xd841b2b80b616f0a3e124f0ed8611743e8becfae",
	"originalMinter": "0xd841b2b80b616f0a3e124f0ed8611743e8becfae"
}
```
