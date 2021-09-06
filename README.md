# Final Submission Spacecamp

## About this document 
This document is designed to document the work on the Licium Protocol demo for the Spacecamp 2021 DeFi bootcamp:   

https://eventornado.com/event/terra-spacecamp#home.

- Status: Work in progress  
- Version: 0.3
- Date: 6. September 2021 (22:50 CET)

## Final Submission

The final submission video can be found here: 

t.b.d.

## Team members

Dino De La O – [Twitter](https://twitter.com/dinodelaomx)   

Jefferson Sofarelli – [GitHub](https://github.com/jmsofarelli/) / [Twitter](https://twitter.com/@jmsofarelli)    

Sebastian Posth – [GitHub](https://github.com/sposth) / [Twitter](https://twitter.com/posth/)

## Worklog

### Communication
- Teambuilding among all members  
- Introduction to the ‘Licium Protocol’ project 
- Discussions about 
  - the scope of the hackathon 
  - Terra integration  
  - decentralised applications, use cases, and future roadmap  
- First draft of the script for the final submissions video  

### Technical Development
- [x] Research on Terra/CosmWasm ecosystem (Local Terra, Terra Station Wallet, CosmoWasm Smart Contracts)
- [x] Learning CosmWasm Contract using Terra Academy (`https://academy.terra.money/`)
- [x] Attending community livestreams on the Terra Bites Youtube channel
- [x] Communication with mentors (`@Orkun Kulce`, `@carlos`, `@Shane Vitarana`) and support from/to other participants of the hackathon
- [x] Running `LocalTerra` on development environment
- [x] Exploring specifications and contracts from CosmWasm Plus repository (`cw-plus`)
- [x] Experiments with `cosmwasm-template`, compilation targeting `cosmwasm-unknown-unknown` and using `rust optimizer`
- [x] Deploying contracts on `LocalTerra`
- [x] Development of Licium Protocol NFT CosmWasm smart contract (v0.1 based on cw751-base link below)
- [ ] Deployment of Licium Protocol NFT smart contract to testnet
- [ ] Development of demo dApp using `Next.js` and `Terra.js` (work in progress)
  - [x] Connect dApp to Terra Blockchain using `Terra Wallet Provider`
  - [] First version of NFT Minting form 
     - [x] Generation of ISCC codes
     - [x] Upload of image to IPFS
     - [ ] Mint NFT using form (send tx to Terra Blockchain)
  - [ ] NFT Licencing form
     - [ ] License NFT using form (send tx to Terra Blockchain)
- [x] Deployment of demo dApp (v0.1 WIP)
- [ ] Deployment of demo dAPP (v0.1 beta) 

## Additional Resources
* Demo dApp (WIP)
  * https://licium.sourcecheck.org/
* Licium Protocol NFT CosmWasm smart contract
  * https://github.com/SourceCheckOrg/licium-cw721
* Licium demo dAPP
  * https://github.com/SourceCheckOrg/licium-nft-ui

## Further Notes

### Actions
The demo application will support the following actions:  

#### Minting
→ Drag & Drop digital media asset (image)  
→ Generation of ISCC  
→ Minting of NFT  
1. Creating NFT  
2. Registration of ISCC  
3. Registration of relevant metadata (licensing offer)  

#### Verification
→ Drag & Drop digital media asset (image)  
→ Generation of ISCC  
→ Resolving of the NFT  
→ Resolving of corresponding metadata (licensing offer)  

#### Licensing Transaction
→ Transfer of amount to owner    
→ Register payment TA to blockchain   
(Due to the nature of the licensing transaction the NFT remains with the user)   

## Data Components

### Token Info

/// The owner of the newly minted NFT
`pub owner: Addr` 

/// Approvals are stored here, as we clear them all upon transfer and cannot accumulate much
pub approvals
`Vec<Approval>`  

/// Identifies the asset to which this NFT represents
`name: String`  

/// Describes the asset to which this NFT represents
`description: String`  

/// A URI pointing to an image representing the asset
`image: Option<String>`  


### ISCC Data

/// Unique id of the token

`token_id: String`  

/// ISCC code generated from the content

`iscc_code: String`   

/// Cryptographic hash

`tophash: String`  


### Offer (Licensing)

/// Unique id of the token

`token_id: String`  

/// Price asked for licensing

`price: Coin`  


### License Transaction

/// Unique id of the token

`token_id: String`     

/// Address of the licensee

`licensee: Addr`   

/// Price paid by the licensee

`price: Coin`  
