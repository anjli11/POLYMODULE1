# ERC721 Nft transfer from Georli to Mumbai

This project demonstrates How we can create Nft's Using ERC721 And then trandfer those NFT's from Georli testnet to Mumbai Testnet.

Mumabi Account Address :0xBEEFD38465e3f4985BA179dD9dbDcEF37FDc8DFc <br/>
Goerli Accout Address: 0xbeEf967A7a323002Ad2ceBE3369418867A8Ef3Ce<br/>
Goerli Contract Address: 0x4f2a7A9640eDFBC83b262F89DcFa8F779749B2C2<br/>
Mumbai Contract Address: 0xDB26478f5384f61dc363201CB188eD0563B312D7<br/>
The Below Contract Address is taken from this Website https://wiki.polygon.technology/docs/pos/design/bridge/l1-l2-communication/fx-portal/#goerli<br/>
ERC721RootTunnel Contract Address:0xF9bc4a80464E48369303196645e876c8C7D972de

## Discription
The Project will be able to do the following tasks

Deploy an ERC721 or ERC1155 to the Goerli Ethereum Testnet
will Mint 5 NFT'S
transfer all NFTs from Ethereum to Polygon Mumbai using the FxPortal Bridge
Approve the NFTs to be transferred
Deposit the NFTs to the Bridge
Test balanceOf on Mumbai

## Executing program
to run the program first we will need a .env File in out root Directory
The .Env file Should contain
```shell

GTOKEN_ADDRS=""  #update it if you have deployed a new contract
MTOKEN_ADDRS=""  #update it if you have Mapped a new contract
FX_ADDRS="" #FxERC721RootTunnel address
PRIVATE_KEY="" #for goerli testnet user Accout
M_ADDRS="" #it can also be same as G_Addrs or guerli Address 
G_ADDRS=""
IPFS="" #please use it Carefully it depends upon your IPFS project structure 
```

After setting it up Run the Following Commands

```shell
#this will Install All the Dependencies
npm i
#this will depoly or contract to Goerli network
npx hardhat run GtoM/deploy.js
#This will Batch Mint 5 nfts Please make sure your Ipfs Structure as it may be different per user
npx hardhat run GtoM/batchMint.js
#This Will Map our token to Mumbai
npx hardhat run GtoM/mapToken.js
#this will give the child contract address
npx hardhat run GtoM/getMappedToken.js
#this will Approve the Fxroot tunnel to prcess the transfer
npx hardhat run GtoM/approve.js
#this will tranfer the nfts from Goerli to Mumbai
npx hardhat run GtoM/transfer.js
#this will display the Balance of both The networks you can call it at any point of time to check balance
npx hardhat run GtoM/GetBalanceBoth.js

```
