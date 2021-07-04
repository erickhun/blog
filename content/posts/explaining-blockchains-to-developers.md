+++
categories = ["blockchain"]
date = "2021-06-30T09:23:00+08:00"
description = ""
draft = false
images = ["/img/explaining-blockchain-developers/blockchain-miners-pick-transactions.jpg"]
title = "Explaining blockchains to developers"
+++

What is a blockchain?  Why are some people using it? Even as a developer, it took me a few years to understand what a blockchain really is,how it is working from inside out. I'll share here what I believe is a comprehensive explanation of what is a blockchain from a developer point of view.

## What is a blockchain?

In simple words, it’s a **slow database**.

For Bitcoin, this database contains a ledger only. A ledger is basically records of how much “token” has been transferred between addresses. Everyone can create a “wallet”, and make a transaction on it. Those transactions will be visible by anyone in the world. Each time you want to “write” in the blockchain, it will cost a certain amount of “fees”. 

“Dubious dev: So... why not create a huge Postgresql/MySQL/MongoDB database cluster, and make it open to everyone? 🤔” 


## What looks like a “blockchain”?

At a really high level, a blockchain is made of blocks containing some data. They are linked with each other with a reference (a hash) of its previous block:

![Bitcoin structure](/img/explaining-blockchain-developers/blockchain-high-level.jpg)

It’s really similar to a [linked list](https://en.wikipedia.org/wiki/Linked_list), but there are some fundamental differences between the two, notably the mechanism of how blocks are added and the data it contains. 


#### How are “blocks” built?

The way new blocks get added is quite sophisticated and isn’t quite instant. 

When you want to make a new transaction on the blockchain - let’s say someone wants to transfer 5BTC to someone else - this will create a new “transaction” but is not immediately added to the blockchain: 



1. The transaction first gets added to **the mempool** 
2. From this mempool, a **miner** will pick the transactions that he likes (the one that give him the most reward). The total size of all transaction transactions must be below 1MB. 
3. The miner will run a “brute-force” algorithm to solve a puzzle. Once he find it, it will have the possibility to add the transactions he picked to the blockchain , [but not always](https://medium.com/f2pool/into-the-mempool-empty-blocks-b368c6fbaad6) (I’ll come to that one later).

**The Mempool** is a sort of waiting room with a priority ticket for transactions that are willing to pay more. The ship contains only a few seats (1MB), so it’s up to the **miner** to decide if he let you in or not. But you might end up in a ship going nowhere. 

![Bitcoin structure](/img/explaining-blockchain-developers/blockchain-miners-pick-transactions.jpg)


You can check all the unconfirmed transactions waiting to be validated in the Bitcoin blockchain [here](https://www.blockchain.com/btc/unconfirmed-transactions). You can also read here a bit about the controversy to have a bigger block size .

Well, this mempool/miner/puzzle architecture looks quite complicated for a database. Why is it needed?


## Protecting the blockchain with Consensus and Decentralization

A “classic” database will allow anyone who has its credential to add/remove/edit records at their will. Want to delete a transaction you’ve made? Add a higher amount in your own wallet? **How would you know this database will always be managed the way it said it will**? How do you make sure the one managing the system will never attempt to change the transactions or the data in it? This is where decentralization, consensus, and immutability comes into play. 


### The race to add a block to the chain proof and work

A blockchain “validates” and permanently stores the data after a consensus is reached. Consensus is an agreement about the state of the ledger. It agrees on things like account balances, the order of transactions, or even if transactions look legitimate. The [most infamous](https://cbeci.org/cbeci/comparisons) consensus protocol is “Proof-of-Work” and used by Bitcoin and Ethereum.


#### Finding the “nonce”: Miners and Rewards 

“Proof of Work” blockchains have an interesting concept where you have to solve a puzzle to be able to add a block to to chain. This puzzle is run by miners. It is a brute-force algorithm where **the first miner who solved it gets a reward** (and the privilege to add a block to the chain 😉). And this happens every time a new block needs to be added. Today, 1,000,000 miners are competing against each other in the hope to solve the puzzle. 

![Bitcoin Miners Adding blocks](/img/explaining-blockchain-developers/blockchain-miners-adding-block.jpg)



#### Increasing difficulty

Bitcoin has a built-in algorithm to try to get a target of 10 minutes to mine a block. If it takes a lot shorter to mine, the difficulty increases, if it takes longer, difficulty decreases. It means the more “hashpower”, the more difficult is the hash function to find the nonce. 

Since 2017, the difficulty has exponentially increased, requiring more powerful computation resource if you want to be lucky enough to mine a block. This is what lead to [today’s heated discussion related to climate change and energy consumption](https://www.ft.com/content/1aecb2db-8f61-427c-a413-3b929291c8ac): 

![Bitcoin difficulty over time graph](/img/explaining-blockchain-developers/bitcoin-difficulty.png)

 


#### How long would that take to mine a block with my computer?

A difficulty of 1 corresponds to 2^32 = 4,3 trillion hashes. Your computer will have to hash a random number (via bruteforce) 4.3T times in the hope to find the nonce with the lowest difficulty possible. 

If we take today’s difficulty of [about 20 trillions](https://www.blockchain.com/charts/difficulty) we will have to to go through 8.6 × 10^22 (it’s 86000000000000000000000 trillions 🤪) operation to try.

Now let’s use a standard [processor a core i7 2600](https://en.bitcoin.it/wiki/Non-specialized_hardware_comparison)  with pretty good hashing power of 23.9 MHash per second, or 2.3e7 hashes/second (or 23,000,000 operation/second). It would take the computer 8.6 × 10^22 / 2.3e7 = 3.7e15 seconds to try all the possibilities, or about **118,567,000 years**. In comparison, if the difficulty was at 1 (when Bitcoin was created) it only took 186 seconds to go through all the possibilities and find the nonce. I know, we would all be rich now right?

This difficulty increase is why miners buy more and more GPUs (CPUs aren't fast enough) to put in those gigantic “[mining warehouses](https://youtu.be/f0HC1Udk6-E?t=159)”, in the hope to find that _lucky number_.

Some new consensus starts to emerge to solve those issues. Ethereum is currently moving to [a “Proof-of-Stake” consensus](https://ethereum.org/en/developers/docs/consensus-mechanisms/pos/). The current Ethereum blockchain [will "merge" (in 2022?) into the proof-of-stake system](https://ethereum.org/en/eth2/merge/). Some (really) interesting variations of the Proof of Stake consensus are adopted in the blockchain space, particularly the [Avalanche](https://docs.avax.network/learn/platform-overview/avalanche-consensus) and [Tendermint Byzantine Fault Tolerance](https://arxiv.org/abs/1807.04938) consensus. Bitcoin however will keep the proof-of-work mechanism. 


## Securing the blockchain with decentralization and cryptography

_“Dubious dev: What if I solve the puzzle and add a fake transaction 🤔?”_

It's _almost impossible_ to create new blocks that erase transactions or create fake ones. If you were lucky enough to find the nonce, this doesn’t mean it will be added to the blockchain: 



1. You will broadcast the information to other other miners 
2. Other miners will check carefully if the transactions if the block submit are actually legit transactions. 
3. If 51% agree on the legitimacy of the block, **consensus is reached**, and the block is permanently added 

The 2nd step is where the “crypto” in “cryptocurrency: plays its main role. Blockchains use cryptography functions in many ways, but the first use case is **to make sure one’s doing a transaction is actually the “owner” of the transaction**. It is also called signing a transaction. You can do that with a “secret key” (or commonly called private key). You can “sign” transactions with that private key to finalize an action. It’s like a real-world signature. In the cryptographers world, it is called “asymmetric cryptography” or  “public-key cryptography” in the developer's world.  With Bitcoin and Ethereum, miners will use the [ECDSA (Elliptic Curve Digital Signature Algorithm)](https://en.wikipedia.org/wiki/Bitcoin#Design) function to make that check. 

![Bitcoin Merging blockchain blocks](/img/explaining-blockchain-developers/blockchain-merging-block.jpg)


## More than value transaction

Some blockchains can store and execute some code, such as the Ethereum blockchain. The Ethereum “database” can store code and get the code executed. The code store is called a “smartcontract”. In Ethereum, the programming language is “[Solidity](https://docs.soliditylang.org/)”. For example:  

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


#### Smart Contract Immutability

The logic in those contracts never changes and will be on-chain forever. The contract you agree to interact will always do what it said it will. No one will ever be able to change the logic. The ones creating this contract won’t be able to change it, even if they published it. So there is no risk of 1 party changing terms, because the contract can’t be changed. It will be on the chain as long as the network is alive. 

As a developer, you might think it’s a bad thing. What if there is a bug?  Well you better write perfect code 😉. There are [many ways](https://www.dasp.co/) to “hack” smart contracts. Some (really expensive) services , often owned by famous  security companies, exist to review your smart contracts before you publish them.


### Transparency (or Privacy?)

Privacy is one of the hottest topics in 2021. We don’t want to be tracked anymore, and try to hide from Internet giants like Facebook or Google. Bitcoin or Ethereum are however fully transparent. The ledger is public and anyone that has your wallet address can see the full history. It’s like a database with read privilege where you can query any balance or operations that happened for any wallet. For example see [here how many Ethereum has Vitalik](https://etherscan.io/address/0xab5801a7d398351b8be11c439e05c5b3259aec9b) (Ethereum's dad), or how he received $375 millions worth of [“AKITA” token](https://www.akitatoken.net/), and then [forwarded that "unwanted money)](https://etherscan.io/tx/0x2fb8b58f85ab4773da00771f7f1e1a9eacf99af0ef3310b75ebcd017099f7b3c) to an India Covid relief fund: 


![ Vitalik Akita covid19](/img/explaining-blockchain-developers/vitalik-akita.png)



If you're looking for privacy, some blockchains such as zCash or Monero make that information hidden. (Read on to understand how). But they're still public since anyone can use them.

Some blockchains are private only. An interesting use case could be sharing some confidential data, between a group of  specific persons. An idea could be applied for the CRS ([Common Reporting Standard, for preventing tax avoidance](https://www.oecd.org/tax/automatic-exchange/common-reporting-standard/)). Governments could share information of bank accounts into that blockchain. With decentralization, no government will have the "privilege" to delete transactions in it. If a change needs to be made, the full history of changes will be written in the ledger. 


### Conclusion

A Blockchains is giant database that stores a ledger with all transactions of its users. It sometimes stores code that can be executed. The decentralization and consensus algorithm built into them make them _almost_ impossible to be compromised by “bad actors”. With today’s [blockchains aggregated valuation ($1.39Trillion!)](https://coinmarketcap.com/charts/), it feels like the world is somehow betting that blockchains could be tomorrow's new way to exchange money and share information. Or is that valuation only [blowing smoke](https://crypto-anonymous-2021.medium.com/the-bit-short-inside-cryptos-doomsday-machine-f8dcf78a64d3) 🤔?


**Dig deeper**: Tesla CTO exploring[ Bitcoin the “hard way”](https://karpathy.github.io/2021/06/21/blockchain/) with Python


<!-- 
*   **To anonymize transactions / information** zk SNARK has been a proof cryptography algorithm. ZK (Zero Knowledge) are mathematical functions that allow us to confirm something without revealing what that information is. It’s a “cryptographic proof” that allows a system without knowing all the information. So validators wouldn’t need the full blockchain to validate transactions. 
*   **To make blockchain size smaller**:  [Mina Protocol](https://minaprotocol.com/tech) uses zk SNARK to make their blockchain really light (22kb).  -->