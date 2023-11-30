# Sample code

### Header

```
X-API-KEY = l4hd4CGLLGuZ9nEultG4sfhQZDjPp9sv0kMy13cyGgkJyIWDodVSM4S4ucb5WFKN
```

### Request

```
GET  api/v3/nft/info/nfts

https://uat2.loopring.io/api/v3/nft/info/nfts?nftDatas=0x08773861a52fff62d5a76024912cca97015fcb1a838e35607d9029355f8e09e9,0x02ef08fd97866a43f811aa62c8d91448b09117e7c97ae513e283020a1e83a1db
```

### Response

```
[{
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
		"royaltyAddress": "0xd841b2b80b616f0a3e124f0ed8611743e8becfae"
	},
	{
		"nftData": "0x02ef08fd97866a43f811aa62c8d91448b09117e7c97ae513e283020a1e83a1db",
		"minter": "0x1772003f02874fccfc7cd14b334f9db8f5bb1d8b",
		"nftType": "ERC1155",
		"tokenAddress": "0x28cbd57197ec1eadfe98fbc37d042cd8e4b4c4f7",
		"nftId": "0xf7778c73467e76c5bfe11ce3fdc046d333a927e3348d62024dbb830c8ae88231",
		"creatorFeeBips": 0,
		"royaltyPercentage": 0,
		"status": true,
		"nftFactory": "0x40F2C1770E11c5bbA3A26aEeF89616D209705C5D",
		"nftOwner": "0x1772003f02874fccfc7cd14b334f9db8f5bb1d8b",
		"nftBaseUri": "",
		"royaltyAddress": "0x1772003f02874fccfc7cd14b334f9db8f5bb1d8b"
	}
]
```
