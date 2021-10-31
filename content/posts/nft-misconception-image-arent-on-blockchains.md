+++
categories = ["blockchain", "nft"]
date = "2021-10-31T13:08:00+08:00"
description = ""
draft = false
images = [""]
title = "NFT misconception: JPEG aren't on the Blockchain"
+++

Today's biggest miscconcepions about NFTs is that they're "jpeg" image stored on the Ethereum blockchain, it's not. Probably because those digital art can be easy to vizualize, and famous artists attempt today to sell their digital art as an NFT on platform such as Opensea, it has gained lot of attentions this past months. 

Artists starts creating their on a piece of paper, then their computer. But when they convert it to an NFT, what makes you the owner of it? Isn't the artist still have the original one on his desk or computer? The process to convert it to an NFT? Are they really on the blockchain? But they're not. They're on one server, and that's not on the blockchain. 


## The "digital art" isn't even store on the blockchain

[ERC-721](https://eips.ethereum.org/EIPS/eip-721#implementations) is the standard that dictates how one should be create an NFT. Each ERC721 NFT must have a `tokenURI` field, that is an external link to a json file stored on an external server (and commonly are not the Ethereum blockchain!). This json file have the the `metadata` information will describe the NFT. It looks like that: 

```json
{
    "title": "Asset Metadata",
    "properties": {
        "name": {
            "description": "Identifies the asset to which this NFT represents"
        },
        "description": {
            "description": "Describes the asset to which this NFT represents"
        },
        "image": {
            "description": "A URI pointing to a resource with mime type image/* 
            representing the asset to which this NFT represents. Consider making 
            any images at a width between 320 and 1080 pixels and aspect ratio 
            between 1.91:1 and 4:5 inclusive."
        }
    }
}
```

You can notice the `image` field, that is a link to an image. If we take example [Project Memento](https://project-memento.com/), an NFT and basically allow the owner of the NFT to change the letters he owns. You can basically trade "coordinates" on the website, and there is NO NEED of an image for the project itself to work. 

For the NFT [8,9] (that [just got sold for 0.5ETH - about ~$2000](https://etherscan.io/tx/0x5b9eb844062c9806e4fd5c831d26ad0c76466cc4d62d46610d5f4efbd1035cac)), the [metadata file](https://project-memento.com/metadata/8-9.json) looks like:  
```json
{
    "name": "Project Memento [8,9]",
    "image": "https://memento.pages.dev/images/8-9.svg",
    "attributes": [
        {
            "trait_type": "Coordinate X",
            "value": "8"
        },
        {
            "trait_type": "Coordinate Y",
            "value": "9"
        }
    ]
}
```
 You can notice the `"image"` field that point to [https://memento.pages.dev/images/8-9.svg](https://memento.pages.dev/images/8-9.svg). Our NFT doesn't need an image. However, it could be great to have a representation of it, especially if the project ends up on [opensea](https://opensea.io/collection/project-memento). We had to use a bit of our imagination, and decided to make a marker on a square representing relatively where would be the tile you get on our grid. 


![Memento representation](/img/nft/project-memento-8-9.svg)

The `tokenURI` field is read on platform like Opensea or Rarible. If you follow the ERC-721 standard, it instantly make your NFT tradable on those platforms. Having appealing image can help you make your NFT project more visible. So even though Project-Memento isn't an NFT that is "art" related, we could attach an image to it. 


## Why not store the jpg them on the blockchain?
We could actually store them on the blockchain, but that would be excessively expensive. The Etheruem blockchain isn't designed for this. Each action you want to do , and every information you store on the blockchain has a cost. You've certainly hear about the excessively high price of Ethereum transaction. And the high price are for tiny code program that weigh few 1 or 2 Kilobyte.  If we would store an image on it: 

- The cost of data storage is 640k gas per kilobyte of data.
- The current gas price is approximately 50 Gwei (or 0.000000050 ETH).
- At today's price (30th october 2021), 1 ETH is approximately $4000.
- Each kilobyete for an image would cost $40

If we assume a jpg weight about 500kb, that will bring the cost to store an image of $20,000! And what if you want to go fancy and store something with High Resolution? I let you make the math

## Conclusion

Because of the high price, most of the NFT use the technique I've describe above. There are other technique such as using solution like IPFS, 


The most famous "Art NFTs" such as cryptokitty or Cryptopunk use all similar techniques. All those images are hosted on external servers, and they're not on the Ethereum blockchain itself. 


