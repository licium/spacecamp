# Update Spacecamp

## About this document 
This document is designed to track the progress of the Licium Protocol demo for the Spacecamp hackathon.

- Status: Work in progress  
- Version: 0.1  
- Date: 2. September 2021  

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
- Research on Terra/CosmWasm ecosystem (Local Terra, Terra Station Wallet, CosmoWasm Smart Contracts)
- Learning CosmWasm Contract using Terra Academy (`https://academy.terra.money/`)
- Attending live community livestreams on the `Terra Bites Youtube channel`
- Communication with mentors (`@Orkun Kulce`, `@carlos`, `@Shane Vitarana`) and support to other participants of the hackathon
- Running `LocalTerra` for development environment
- Exploring specifications and contracts of CosmWasm Plus repository (`cw-plus`)
- Experiments with `cosmwasm-template`, compilation targeting `cosmwasm-unknown-unknown` and using `rust optimizer`
- Deploying contracts on `LocalTerra`
- Development of the first version of a custom cw751 CosmWasm smart contract (link below)
- Development of demo dApp using `Next.js` and `Terra.js` in progress (link available soon)

## Additional Repositories

https://github.com/SourceCheckOrg/licium-cw721

https://github.com/SourceCheckOrg/licium-nft-ui (v0.1 available soon)

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

/// The owner of the newly minted NFT: 

`pub owner: Addr` 

/// Approvals are stored here, as we clear them all upon transfer and cannot accumulate much
pub approvals:   

`Vec<Approval>`  

/// Identifies the asset to which this NFT represents:  

`name: String`  

/// Describes the asset to which this NFT represents:  

`description: String`  

/// A URI pointing to an image representing the asset:  

`image: Option<String>`  


### ISCC Data

/// Unique id of the token: 

`token_id: String`  

/// ISCC code generated from the content:   

`iscc_code: String`   

/// Cryptographic hash:  

`tophash: String`  


### Offer (Licensing)

/// Unique id of the token:  

`token_id: String`  

/// Price asked for licensing:  

`price: Coin`  


### License Transaction

/// Unique id of the token:  

`token_id: String`     

/// Address of the licensee:  

`licensee: Addr`   

/// Price paid by the licensee:  

`price: Coin`  
