+++
categories = ["blockchain", "investment"]
date = "2021-06-30T09:23:00+08:00"
description = ""
draft = false
image = "/img/about-bg.jpg"
title = "Explaining blockchains to developers"
+++

# Explaining Blockchain to a Developer

_“Hey Eric! Did you know you can make some “internet money” if you let this daemon run on your computer?”_ a workmate told me. I’ve assumed it could be a kind of spyware/adware showing me ads and didn’t consider the idea further. Few months later, in October 2016, An ex-classmate  told me he made a good amount of money with that thing called “Ethereum”. I bought some Bitcoins and Ethereum after that via wechat. I still didn’t get what that Bitcoin or Ethereum thing was, naively thought “it’s magic internet money” and I could probably make money if I got some. The price of Ethereum was dropping a few days later and I forgot about it. Selective memory yes. 

A year later, on the train back from a holiday trip in Tainan, I saw the news about a cryptocurrency exchange. It rang a bell. “I think I’ve bought some “internet money” in that exchange”. I’ve logged in. Went to check how many tokens I had. I calculated the equivalent in USD. Calculated again, and again… “Impossible!”. My Bitcoin holding USD value increased 700% and Ethereum value 3500%! 🤯🤯

What is this daemon ? How can it take so much in value? Even as a developer, it took me a few years to understand what a blockchain really is, how it is working. I’m still sometimes  confused about it, but will try to lay out what I understand about it from a developer point of view. 


### What is a blockchain?

In simple words, it’s a **fancy database**.

For Bitcoin, this database contains a ledger only. A ledger is basically records of how much “token” has been transferred between addresses. Everyone can create a “wallet”, and make a transaction on it. Those transactions will be visible by anyone in the world. Each time you want to “write” in the blockchain, it will cost a certain amount of “fees”. 

“Dubious dev 🤔: So... why not create a huge Postgresql/MySQL/MongoDB database cluster, and make it open to everyone?” 


### Is it only “token” transactions?

Not only. Some blockchains can store and execute some code, such as the Ethereum blockchain. The Ethereum “database” can store code and get the code executed. The code store is called a “smartcontract”. In Ethereum, the programming language is “[Solidity](https://docs.soliditylang.org/)”. For example:  

```
receiveMoneyEvent(amount) {
	facilitatortFee = amount * 2/100
	splitMoneyAmount = (amount - facilitatortFee) / 2
	sendTo(charityAddressX, splitMoneyAmount)
	sendTo(charityAddressY, splitMoneyAmount)
	sentTo(facilitatortAddress, facilitatortFee)
}
```

In this example, each time the smart contract receives money, it will forward it to 2 charities. In between, the “facilitator” will take a 2% fee.  Pretty simple isn’t it?

Once you publish this code to the blockchain ( you’ll have to pay each time you want to do that, it’s like an expensive git push command), anyone who wants to can call this contract. In this smartcontract, addresses that will send Ether (ETH) to this contract, those actions will be executed. 

“Dubious dev 🤔: Well,  s[ome databases such as MySQL/ Oracle](https://en.wikipedia.org/wiki/Stored_procedure) can also store and execute code?”


### The Security of a blockchain: Decentralization, Consensus, and Immutability

A “normal” database will allow anyone who has its credential to add/remove/edit records at their will. Want to delete a transaction you’ve made? Add a higher amount in your own wallet? **How would you know this database will always be managed the way it said it will**? How do you make sure the one managing the system will never attempt to change the transactions or the data in it? This is where decentralization, consensus, and smart contract immutability comes into play. 


#### Protecting the blockchain with “Consensus” and Decentralization

Blockchains “validate” transactions when a consensus is reached. A consensus is an agreement about the state of the ledger. It agrees on things like account balances and the order of transactions. The most famous consensus protocol being the proof-of-work protocol. It requires people running the daemon (also called miners) to go through a **brute force algorithm **to find the answer of a puzzle, also called _the nonce_. If a miner find the nonce, they’ll be rewarded with the cryptocurrency of the blockchain they are mining for. 

“Dubious dev 🤔: What if I solve the puzzle and add a fake transaction?” 

It's _almost impossible_ to create new blocks that erase transactions or create fake ones. There are 1,000,000 miners in Bitcoin, and everyone's competing against each other. Malicious miners will need to always be solving _the puzzle_ faster than everyone else to incorporate new changes, what’s _almost_ impossible. Some new consensus such as Proof of Stake (particularly the [Avalanche](https://docs.avax.network/learn/platform-overview/avalanche-consensus) and [Tendermint Byzantine Fault Tolerance](https://arxiv.org/abs/1807.04938)  consensus).


#### Immutability

The logic in those contracts never changes and will be on-chain forever. The contract you agree to interact will always do what it said it will. No one will ever be able to change the logic. The ones creating this contract won’t be able to change it, even if they published it. So there is no risk of 1 party changing terms, because the contract can’t be changed. It will be on the chain as long as the network is alive. 

As a developer, you might think it’s a bad thing. What if there is a bug?  Well you better write perfect code 😉. There are [many ways](https://www.dasp.co/) to “hack” smart contracts. Some (really expensive) services , often owned by famous  security companies, exist to review your smart contracts before you publish them.


### Transparency (or Privacy?)

Privacy is one of the hottest topics in 2021. We don’t want to be tracked anymore, and try to hide from Internet giants like Facebook or Google. Bitcoin or Ethereum are however fully transparent. The ledger is public and anyone that has your wallet address can see the full history. Cool or uncool? You decide. It’s like a database where you can query any transaction you are doing on it. You can for example see [here how many Ethereum (and other coin) Vitalik](https://etherscan.io/address/0xab5801a7d398351b8be11c439e05c5b3259aec9b) has. But what’s most interesting is that  you can see the full history of his wallet. You can see here that he received $375 millions worth of [“AKITA” token](https://www.akitatoken.net/), and then [forwarded that "unwanted money)](https://etherscan.io/tx/0x2fb8b58f85ab4773da00771f7f1e1a9eacf99af0ef3310b75ebcd017099f7b3c) to an India Covid Relief Fund: 



![ Vitalik](/img/explaining-blockchain-developers/vitalik-akita.png)


Some blockchains such as zCash or Monero are public but used because in order to hide transactions or information. (Read on to understand how). 

Some blockchain are private only. 

An interesting use case could be when sharing confidential data, between a set of  specific set of persons. For example an interesting use case could be applied for the CRS ([Common Reporting Standard, for preventing tax avoidance](https://www.oecd.org/tax/automatic-exchange/common-reporting-standard/)). Governments  will share information of bank account into that blockchain. No one could alter the data in it, and it will be available only to the one in that Consortium. 


### Why “crypto”?

**Cryptocurrencies** use **cryptographic** functions to maintain security and fidelity in various parts of the blockchain software/protocol. “Cryptos” is actually a shortcut used for “cryptocurrencies” and used by many, but cryptographers don't like people using it since just a few of them work in the cryptocurrency space, so be aware if one is around you 😉

Those functions used in cryptos are similar functions such as SHA-256 used in SSL certificates or AES for VPNs. 

Cryptocurrencies use cryptography functions multiple ways, mainly: 



*   **To make sure you’re the real owner of a wallet to perform a transaction**. It is also called signing a transaction. You can do that with a “secret key” (or commonly called private key). You can “sign” transactions with that private key to finalize an action. It’s like a real-world signature. In the cryptographers world, it is called “asymmetric cryptography” or  “public-key cryptography” in the developer's world.
*   **To anonymize transactions / information** zk SNARK has been a proof cryptography algorithm. ZK (Zero Knowledge) are mathematical functions that allow to confirm something without revealing what that information is. It’s a “cryptographic proof” that allows a system without knowing all the information. So validators wouldn’t need the full blockchain to validate transactions. 
*   **To make blockchain size smaller**:  [Mina Protocol](https://minaprotocol.com/tech) uses zk SNARK to make their blockchain really light (22kb). 



### Conclusion

Blockchain are giant databases that store a ledger with all transactions of its users. It  sometimes stores code that can be executed. The decentralization and consensus algorithm built into them make them _almost_ impossible to be compromised by “bad actors”. With today’s blockchains valuation ($1.39Trillion!) It feels like the world is somehow betting blockchains could be tomorrow's new way to exchange money and share information. Or is that valuation only [blowing smoke](https://crypto-anonymous-2021.medium.com/the-bit-short-inside-cryptos-doomsday-machine-f8dcf78a64d3) 🤔?

<!-- Want to explore more?



*   Tesla CTO exploring Bitcoin the “hard way”: [https://karpathy.github.io/2021/06/21/blockchain/](https://karpathy.github.io/2021/06/21/blockchain/)
*    -->


