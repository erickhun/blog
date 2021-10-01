+++
categories = ["blockchain"]
date = "2021-09-30T09:16:00+08:00"
description = ""
draft = false
images = [""]
title = "When code is law"
+++

How can you trust an individual, company, or government with the money you send to them? What tells you there are no hidden fees, or middleman in the contract you’re signing for? How do you make sure terms won’t be changed?
Those are one of the exciting things I’m excited about smart contracts on public blockchains, The “Code is Law” feature (also called “immutability”). They are the promises of what a smart contract can fulfill. They can become a powerful tool for companies, governments and individuals to trust each other. 


## The _immutability_ of a smart contract

Smart contracts can be seen as any traditional website/contract today. However it removes the human component of it.

 With a traditional website, it doesn't mean you know what will happen behind the scenes. Some (often) unreadable lawyer words (with TOS)  will try to make you think they promise _x_ or _y_. But **what will guarantee you _x_ or _y_ will happen? How do you know traditional websites fulfill their promise(s)**? 

This is where smart contracts become useful. 

When you interract with it (call an specific action in the smart contract), they’ll be executed the way it was written, and not in another way, because there is only a single and unique way to run the code that is written in the smart contract. 

Let’s take this example where for project-memento, the 3 creators (Simon, David and me) are the ones taking the profit of the project: 

We’ve agreed for the project to split the profit by 3. In the contract we simply create this function in the smart contract: 

```
    // admin function to withdraw paid fees in the contract (everyone can call it!)
    function adminWithdraw() public {

        // divide the amount for owners
        uint256 perFounder = address(this).balance / 3;

		// pay everyone
        payable(address("simon.eth")).transfer(perFounder); 
        payable(address("david .eth")).transfer(perFounder); 
        payable(address("eric.eth")).transfer(perFounder); 
    }
```

And this code will always be as it is, unless a new contract is written. Once the smart contract is deployed on the blockchain, there is no way of coming back. The only way to change the code is to deploy a new contract. If you do so, users will notice you changed the contract (the address and the code will change).  
No interpretations in smart contracts 
How many times have you heard “this is subject to one’s interpretation”? There are so many texts written in traditional contracts or in the law that aren’t clear. Why do we need a professional (mostly lawyers and CPA). Why are texts in the law so blurry, and “subject for interpretation”? Especially when it comes to something as important as money or ownership?  How many times did we need to “seek professional advice” to make sure we interpret the text as it is intended to be? And sometimes, even when you’re asking for “professional advice” you’re in doubt because the interpretations are different from various professionals.
Users of those institutional systems (you and me) can benefit from smart contracts because there is a single way to run the code in the smart contract, and the output will be as we expect it to be. 
Ownership - we’re currently seeing it with NFT (that is marketed as jpeg ownership now) , can be used for that. 
One of are the tax law. Why don’t we simple , and the , without anyone? 
Send money to that contract, and that's all. If we’re not sure, we can use a “testnet” to run with our , and see the results. Simply no interpretation, only code running as it should be running.

<!-- Everyone can use the blockchain -->

## Nothing to hide here

The other beautiful feature is transparency. Ethereum, among other blockchain (bitcoin doesn't have the ability to run smart contracts  - yet ) gives you the transparency of any interactions that happens with that money. You know in real time how much money has been sent to this smart contract, what this money has been then sent to. 
Let’s take an example of NGOs that promis. How do we know this has been done? Reports? Can you trust those reports? 

A simple way is to check the interaction than might have happened with the (fictive) Red Cross smart contract: 

```
    // admin function to withdraw paid fees in the contract (everyone can call it!)

    function makeDonation(value) public {

		uint256 red_cross_fee = value * 3 / 100;

        payable(address("redcross.eth")).transfer(); 

		// pay the beneficiary 
        payable(address("entity.eth")).transfer(value - red_cross_fee); 

```
That smart contract, show the red cross takes 3%  but then fulfill the promise of forwarding the entity it want to help 

## Mistakes aren’t allowed
Humans make mistakes, not computers ( when well programmed ).

As said previously. you can’t change the code once the smart contract is deployed on the blockchain. If an unintentional (or intentional?) logic exists in the code, and is harmful for users, a malicious individual that might try to use it. This is where we talked about “hack” in a smart contract. Code of the smart contract are visible on the blockchain, so it’s easier for hacker to discover vulnerabilities, so they are subject to attack. 
From a developer or entrepreneur point of view, this isn’t ideal. In the startup world, when done properly, a product (mvp) is usually buggy and not perfect, a good product often starts really buggy, and never really reaches perfection. 
Testnets exist so you can test it, and you can also. Also smart contract audits become more and more common, but often too expensive. A good idea could be to use battle tested standards, like the ERC 721 for NFTs,  where new code is minimized and mistakes less prone to happen.


**Next read**: [Explaining blockchains to developers](/posts/explaining-blockchains-to-developers)

