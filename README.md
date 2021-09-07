# Final Submission Spacecamp

## About this document 

This document is designed to document the work on the Licium Protocol demo for the Spacecamp 2021 DeFi bootcamp:   

https://eventornado.com/event/terra-spacecamp#home.

- Status: Work in progress  
- Version: 0.3
- Date: 6. September 2021 (22:50 CET)

## Final Submission

The final submission video can be found here: 
[https://www.youtube.com/watch?v=GZU5pYaeIlc](https://www.youtube.com/watch?v=GZU5pYaeIlc)

## Team members

* Jefferson Sofarelli – [GitHub](https://github.com/jmsofarelli/) / [Twitter](https://twitter.com/@jmsofarelli)    
* Sebastian Posth – [GitHub](https://github.com/sposth) / [Twitter](https://twitter.com/posth/)
* Dino De La O – [Twitter](https://twitter.com/dinodelaomx)   


## Additional Resources
* Demo dApp (v0.1 beta, connnected to Bombay network)
  * https://licium.sourcecheck.org/
* Licium Protocol NFT CosmWasm smart contract
  * https://github.com/SourceCheckOrg/licium-cw721
* Licium demo dApp
  * https://github.com/SourceCheckOrg/licium-nft-ui


## Use cases and actions

* The demo application supports the following use cases:  

### Minting
* Uploading of digital media asset (image)
* Generation of ISCC code
* Minting of NFT
  1. Creating NFT  
  2. Registration of ISCC
  3. Registration of relevant metadata (licensing offer)

### Verification
* Uploading of digital media asset (image)  
* Generation of ISCC  
* Resolving of the NFT associated with the content
* Resolving of corresponding metadata (licensing offer)  

### Licensing Transaction
* Transfering of license amount to NFT owner
* Registering license in the smart contract
* Due to the nature of the licensing transaction the NFT remains with the user 


## Worklog

### Communication
- Teambuilding among all members  
- Introduction to the `Licium Protocol` project 
- Discussions about 
  - The scope of the hackathon 
  - Terra integration  
  - Ddecentralised applications, use cases, and future roadmap  
- First draft of the script for the final submissions video  

### Technical Development
- [x] Research on Terra/CosmWasm ecosystem (Local Terra, Terra Station Wallet, CosmoWasm Smart Contracts)
- [x] Learning CosmWasm Contract using Terra Academy (`https://academy.terra.money/`)
- [x] Attending community livestreams on the Terra Bites Youtube channel
- [x] Communication with mentors (`@Orkun Kulce`, `@carlos`, `@Shane Vitarana`)
- [x] Support from/to other participants of the hackathon
- [x] Running `LocalTerra` on development environment
- [x] Exploring specifications and contracts from CosmWasm Plus repository (`cw-plus`)
- [x] Experimenting with `cosmwasm-template`, compilation targeting `cosmwasm-unknown-unknown` and using `rust optimizer`
- [x] Deploying contracts on `LocalTerra`
- [x] Development of Licium Protocol NFT CosmWasm smart contract (v0.1 based on cw751-base, link below)
- [x] Deployment of Licium Protocol NFT smart contract to testnet
- [x] Development of demo dApp using `Next.js` and `Terra.js`
  - [x] Connect dApp to Terra Blockchain using `Terra Wallet Provider`
  - [x] NFT Minting form 
     - [x] Generation of ISCC codes
     - [x] Upload of image to IPFS
     - [x] Mint NFT using form (send tx to Terra Blockchain)
     - [x] Aggregation of ISCC and licensing data to the NFT
  - [x] NFT Licencing form
     - [x] Generation of ISCC codes
     - [x] Resolution of NFT token based on the ISCC generated data 
     - [x] Performing of the licensing transaction, sending the payment direct to the NFT owner
- [x] Deployment of demo dAPP (v0.1 beta, link bellow) 


### Technical Considerations 

- Because of the short duration of the Spacecamp, we did not focus on creating a perfect, bug-free, production-level product
- Rather we have used our time and resources to learn the technology stack, explore the tools and implement a decentralized application (dApp) connected to a smart contract that captures the core ideas of our project
- In order to create a more robust and professional solution we need to design and implement some other smart contracts, each one focused on a specific aspect of our use cases
- Following the CW721 specification, our protocol can easily be integrated into other NFT platforms and marketplaces, bringing numerous opportunities to generate revenue through licensing
- The potential is huge!


### Data Components

#### Token Info (CW721 specification)

```
/// The owner of the newly minted NFT
pub owner: Addr

/// Approvals are stored here, as we clear them all upon transfer and cannot accumulate much
pub approvals: Vec<Approval>

/// Identifies the asset to which this NFT represents
name: String

/// Describes the asset to which this NFT represents
description: String

/// A URI pointing to an image representing the asset
image: Option<String>
```

#### ISCC Data

```
/// Unique id of the token
token_id: String

/// ISCC code components
meta_id: String

content_id: String

data_id: String

instance_id: String

/// Cryptographic hash
tophash: String
```

####  Licensing Offer

```
/// Unique id of the token
token_id: String  

/// URL of the document containig the terms of the license
url: String

/// Price asked for licensing
price: Coin
```

#### License (Licensing transaction)

```
/// Unique id of the token
token_id: String

/// Address of the licensee
licensee: Addr

/// Price paid for the license
price: Coin
```
