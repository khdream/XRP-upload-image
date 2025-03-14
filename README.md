# Image Uploader for XRP Easy NFT (https://xrpeasynft.com)

## Purpose

This is an image uploading service specifically built for (https://xrpeasynft.com), which is a platform that simplifies the process of creating and minting NFTs on the XRP Ledger. The tool handles the image uploading component of the NFT creation process.


## How It Works

The repository provides a service that:

1. Accepts image uploads
2. Processes these images for NFT compatibility
3. Likely stores them using Pinata's IPFS service (based on the commit messages)
4. Makes them available for NFT minting on the XRP Ledger

## Integration with XRP Ledger

This tool is part of the broader XRP NFT ecosystem, specifically designed to work with the XRP Easy NFT platform. It handles the image storage aspect of NFT creation, which is a critical component since NFTs on the XRP Ledger typically store metadata and image references off-chain (likely on IPFS through Pinata in this case).

This project demonstrates how the XRP Ledger ecosystem is developing tools to make NFT creation more accessible to users who may not be familiar with all the technical aspects of blockchain and distributed storage.

## Development
### Build Image
`docker build -t xrp-easy-nft-uploader .`

### Run Service
`docker run --name=xrp-easy-nft-uploader --rm -p=8080:8080 xrp-easy-nft-uploader:latest`

### RUN script
`curl -X POST "http://localhost:8080/2015-03-31/functions/function/invocations" -d '{"key":"value"}'`


## Deploy
### Tagging
`docker tag xrp-easy-nft-uploader:latest ${ACCOUNTID}.dkr.ecr.${REGION}.amazonaws.com/xrp-easy-nft-uploader:latest`

### Login ECR
`aws ecr get-login-password | docker login --username AWS --password-stdin ${ACCOUNTID}.dkr.ecr.${REGION}.amazonaws.com`

### Push
`docker push ${ACCOUNTID}.dkr.ecr.${REGION}.amazonaws.com/xrp-easy-nft-uploader:latest`

