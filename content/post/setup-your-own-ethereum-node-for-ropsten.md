+++
categories = ["Ethereum", "Blockchain", "Ropsten", "Dev"]
date = "2018-02-03T11:16:22+01:00"
description = ""
draft = false
image = "/img/ethereum-logo.png"
tags = ["ethereum", "blockchain", "dapp", "infrastructure", "digitalocean", "geth", "dev"]
title = "Setup you own Etheureum node with geth on the Ropsten test network"
+++

You're on the right place for a step by step guide to setup your own Ethereum node on the Ropsten. At the end of this guide you'll be able to: 

- Run your own ethereum node 
- Making sure to keep your node in sync with your chosen network
- Be able to communicate via the json rpc API of your node

### Why ?

- Once your dAPP and Smart Contract are working locally, you'll want to test it on a real network with (almost) real condition. 
- There is a service called [Infura](https://infura.io), allowing you to communicate easily with Ropsten via json-rpc without having your own node. However, Infura doesn't allow you to [listen to events](http://solidity.readthedocs.io/en/develop/contracts.html#events) that  your smart contract fired. Events are useful when you want start to do some fancy thing like real time data replication on a second database or simply notify your users in your [dApp](https://ethereum.stackexchange.com/tags/dapp-development/info). If you do not need events, you should definitely use Infura :)
- 

### Prerequis : 
- Your own instance. I have a [Digital Ocean](https://m.do.co/c/8cd97ac64536) one with Ubuntu. If you're a student, you can have a nice [$50 free credits for testing purpose](https://education.github.com/pack).
- 5GB availlable of space disk. The Ropsten chain takes about 6GB on my server disk (3rd  February 2018) . The "real" ethereum blockchain requires about [50GB of diskspace](https://etherscan.io/chart2/chaindatasizefast).

### Step1: Setup geth (go ethereum)
`geth` will allow you to sync the Ethereum blockchain, but also and run a rpc client

To set that up : 
```
sudo apt-get install software-properties-common
sudo add-apt-repository -y ppa:ethereum/ethereum
sudo apt-get update
sudo apt-get install ethereum -y
```

Some people might prefer `parity`. This guide will focus on `geth`

### Step2: Sync your node with the Ropsten network (only once)

The sync took about 3 hours totaly. I'm running the command in a `screen` console, just in case I lose the ssh connection or want to do something else in the server. You can also use `tmux` if you prefer. 

Optional : Before syncing it , make sure to not have any obsolete chain : 
```
geth --testnet removedb
```

And sync the full ropsten blockchain network (only onces)
```
geth --testnet --fast --bootnodes "enode://20c9ad97c081d63397d7b685a412227a40e23c8bdc6688c6f37e97cfbc22d2b4d1db1510d8f61e6a8866ad7f0e17c02b14182d37ea7c3c8b9c2683aeb6b733a1@52.169.14.227:30303,enode://6ce05930c72abc632c58e2e4324f7c7ea478cec0ed4fa2528982cf34483094e9cbc9216e7aa349691242576d552a2a56aaeae426c5303ded677ce455ba1acd9d@13.84.180.240:30303" console
```

Those flags are useful for: 

- `--testnet` : you'll sync with the Ropsten network. Alternatively you can use other flags
- `--fast` : you're enabling [fast syncing](https://ethereum.stackexchange.com/a/11300) 
- `--bootnodes` : Through these bootnodes a node can join the network and find other nodes. The one I've given are valid for the 3rd Feb 2018, and might change in the future. Check the [ropsten official repo](https://github.com/ethereum/ropsten) to get the updated bootnodes.
- `console`: I attached the console to know the current state of the sync . Without that, you'll be a bit blind on the progress of the sync

The Ethereum blockchain will store the data in the default directory (`/YOUR_HOME/.ethereum/testnet/geth/chaindata`). You can also check the size of the blockchain with `du -hs /YOUR_HOME/.ethereum/testnet/geth/chaindata` 


### (optional) Step2.1: Check the progress of the sync : 

Because you attached the console to the geth command, you'll be able to know the progress of the sync by running  that command inside the console : 
`> eth.syncing`
It will return : 
```
{
  currentBlock: 914011,
  highestBlock: 2579729,
  knownStates: 7383,
  pulledStates: 480,
  startingBlock: 914001
}
```

Note: `highestBlock: 2579729` should match the last block in [Ropsten Etherscan website](https://ropsten.etherscan.io/)


### (optional) Step2.2: restart the sync when `geth` error-out : 
It happened to me (several times) that `geth` errored-out during the sync. I didn't find out why, but simply run the following command, and the sync will continue from where it exited : 
```
geth --testnet console
```
Note: I didn't specify the  `--bootnodes` and `--fast` flags since `geth` kept it in memory. `--testnet` is needed or `geth` will try to read in the main ethereum database that you don't have (yet).


### Step3: Activate the JSON-RPC API (and keep your node in sync):

As a developer, sooner or later you'll want to start interacting with Geth and the Ethereum network via your own programs and not manually through the console. `geth` has built in support for a JSON-RPC based APIs (standard APIs and Geth specific APIs). These can be exposed via HTTP, WebSockets and IPC (unix sockets on unix based platforms).


```
geth --testnet --cache=1048 --rpc --rpcapi "eth,net,web3" --rpccorsdomain '*' --rpcaddr 0.0.0.0 --rpcport 8080
```

- `--rpc` Enable the HTTP-RPC server
- `--rpcaddr` HTTP-RPC server listening interface
- `--rpcport` HTTP-RPC server listening port
- `--rpcapi` API's offered over the HTTP-RPC interface
- `--rpccorsdomain` `*` for allowing everything access to it

When running that command, `geth` will keep your node in sync with the network. You can let that one run in a `screen` or `tmux` terminal to keep it alive. The best thing would be to let the process managed by `supervisord` or `systemd` 

### Step4: Query the JSON-RPC API:

You can test if the api is working with `curl`:

```
curl -X POST --data '{"jsonrpc":"2.0","method":"net_version","params":[],"id":67}' http://0.0.0.0:8080
```

If all is fine, you should get a response that looks like : `{"jsonrpc":"2.0","id":67,"result":"3"}`

### (optional) Open the firewall:
If you want your dApp or Metamask to communicate with your node, you'll need to open the port of your server. On Digital Ocean, it's quite easy via [their console](https://www.digitalocean.com/community/tutorials/how-to-troubleshoot-digitalocean-firewalls). With my example, I've opened the port `8080` in the Inbound settings.

Then you can query the api via : 
```
curl -X POST --data '{"jsonrpc":"2.0","method":"net_version","params":[],"id":67}' http://X.X.X.X:8080
```
with replacing `X.X.X.X` the ip of your instance.

Also, please understand the security implications of opening up an HTTP/WS based transport before doing so! Hackers on the internet are actively trying to subvert Ethereum nodes with exposed APIs!


### Next blog post?:
I hope this guide was helpful for anyone starting. Please let me know if there is any mistakes. I'm also thinking writing about:

 - How to run easily your own ETH blockchain with `truffle` and `ganache` on a remote server. That one is useful if you do not want to sync the full chain, and have the same blockchain available quickly for your teamate.
 - How to have a realtime data replication of your smart contract using events to an other DB. That one could be useful because querying the Ethereum blockchain might not be as fast and easy as we wish :)
 