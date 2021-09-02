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
- Discussions about Terra integration  
- Discussions about decentralised applications, use cases, and future roadmap  
- First draft of the script for the final submissions video  

### Technical Development
- Research on CosmWasm (Wallet, Smart Contracts, Events)   
- Attending the live community livestreams on the Terra ecosystem   
- Communication with mentors  

## Additional Repositories
Repositories with code will be published soon.  

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

#### Payment Transaction
→ Transfer of amount to owner    
→ Register payment TA to blockchain   
(Due to the nature of the licensing transaction the NFT remains with the user)   

## Data Components

### CW721 Smart Contract
- token_id    
- name (String)  
- description  
- owner  

### ISCC Data
- token_id  
- ISCC  
- tophash  

### Offer
- token_id  
- license_price  

### License Transaction
- token_id  
- licensee: addr  
- licence_price  
- IPFS_URL  


