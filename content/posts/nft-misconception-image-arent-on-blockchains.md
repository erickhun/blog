+++
categories = ["blockchain", "nft"]
date = "2021-10-31T13:08:00+08:00"
description = ""
draft = false
images = [""]
title = "NFT misconception: JPEG aren't on the Blockchain"
+++

Today's biggest misconception about NFTs is that they're "jpeg" images stored on the Ethereum blockchain, it's not. Probably because that digital art can be easy to visualize, and famous artists attempt today to sell their digital art as an NFT on a platform such as Opensea, it has gained lot of attention these past months. 

Artists start creating them on a piece of paper, then their computer. But when they convert it to an NFT, what makes you the owner of it? Isn't the artist still have the original one on his desk or computer? The process to convert it to an NFT? Are they really on the blockchain? But they're not. They're on one server, and that's not on the blockchain. 


## "Digital art" isn't even stored on the blockchain

[ERC-721](https://eips.ethereum.org/EIPS/eip-721#implementations) is the standard that dictates how one should create an NFT. Each ERC721 NFT must have a `tokenURI` field, that is an external link to a JSON file stored on an external server (and commonly are not the Ethereum blockchain!). This JSON file has the `metadata` information that will describe the NFT. It looks like that: 

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

You can notice the `image` field, which is a link to an image. If we take example [Project Memento](https://project-memento.com/), an NFT allowing change tiles you own to the desired letter. You basically trade "coordinates" on the website and there is NO NEED of an image for the project itself to work. 

For the NFT [8,9] (that [just got sold for 0.5ETH - about ~$2000!](https://etherscan.io/tx/0x5b9eb844062c9806e4fd5c831d26ad0c76466cc4d62d46610d5f4efbd1035cac)), the [metadata file](https://project-memento.com/metadata/8-9.json) looks like:  
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
 You can notice the `"image"` field that points to [https://memento.pages.dev/images/8-9.svg](https://memento.pages.dev/images/8-9.svg). Our NFT doesn't need an image. However, it could be great to have a representation of it, especially if the project ends up on [opensea](https://opensea.io/collection/project-memento). We had to use a bit of our imagination, and decided to make a marker on a square representing relatively where would be the tile you get on our grid. 


![Memento representation](/img/nft/project-memento-8-9.svg)

The `tokenURI` field, which is in the ER721 standard, is read on platforms like Opensea or Rarible. If you follow the ERC-721 standard, it will make your NFT instantly tradable on those platforms. Having an appealing image can help you make your NFT project more visible. So even though Project-Memento isn't an NFT that is "art" related, we could attach an image to it. 

<!-- ## What could go wrong? -->


## Why not store the image on the blockchain?
We could store them on the blockchain, but that would be excessively expensive. The Etheruem blockchain isn't designed for this. Each action you want to do, and every information you store on the blockchain has a cost. You've certainly heard about the excessively high price of Ethereum transactions. And the high price is for a tiny code program that weighs a few 1 or 2 Kilobytes.  If we would store an image on it: 

- The cost of data storage is 640k gas per kilobyte of data.
- The current gas price is approximately 50 Gwei (or 0.000000050 ETH).
- At today's price (30th October 2021), 1 ETH is approximately $4000.
- Each kilobyte for an image would cost $40

If we assume a jpg weight of about 500kb, that will bring **the cost to store an image to $20,000**! And what if you want to go fancy and store something with High Resolution, or even better, raw images? I let you do the maths!

## Conclusion

Because of the high price, most of the NFT use the technique I've described above. There are other techniques such as using a solution like [IPFS](https://ipfs.io/), a type of "decentralized" service.  

The most famous "Art NFTs" such as cryptokitty or Cryptopunk use all similar techniques. All those images are hosted on external servers, and they're not on the Ethereum blockchain itself. Metadata and the NFT are not one. Rather, your NFT — the digital asset itself — includes a link that points to the metadata, which lives elsewhere online. If you're a regular internet user, you know that sometimes, links die (cue the infamous “404 Page Not Found” web page). Hosting platforms don’t exist forever, and if your NFT exists on a regular website, you could potentially lose it along with all the associated value if that site shuts down for any reason.

So before buying any NFT, try to understand what you buy and even better, how it works!
