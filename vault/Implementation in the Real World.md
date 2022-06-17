---
id: 68rc9nuismowpr8krdzevhp
title: Implementation in the Real World
desc: ''
updated: 1655462538303
created: 1655456207238
---
In this note we are going to see how the blockchain is being implemented in the real world.

Traditionally when we run a website or any application that runs on a server, you technically interacting with a central entity. I mean yeah, it could be run by different servers, but it still those servers are still going to be controlled by a centralized group. Blockchain as we saw, runs on a network of different independent nodes. When we saw peer A, B and C those were different independent users that run on their own node. So, what is a node??

## Node
A node is a single instance in a decentralized network. The interaction of these nodes are the ones that create this blockchain. What's interesting is that, anybody can join the network. The barrier to entry however is the powerful hardware requirements that you may require to run the software. You can go to Github and run your own ethereum node too!

Blockchains are resilient. If one node screws up or is malicious, since there are multiple independent nodes running, it doesn't matter the system will always persist so long as to only one node running. 

Nodes keeps the list of transactions that occur and makes sure nothing can be change or corrupted thus giving the immutability trait. 

## Consensus

Proof of work and Proof of stake fall in this umbrella of **consensus**. Consensus is defined as the mechanism used to reach an agreement on the single value or the state of the blockchain.

Remember the peer system in the previous note wherein if one peer acts sus and the other 2 does not validate it it kicks that peer out? This is part of that consensus mechanism.

A consensus protocol in a decentralized system can be broken down into 2 pieces. 
1. A chain selection algorithm
2. Sybil Resistance Mechanism

The mining part which we were doing, or the proof of work algorithm is a sybil resistance mechanism is what ethereum and bitcoin are using. 

## Sybil Resistance

Sybil Resistance is a blockchain ability to defend against users creating a large number of pseudo-anonymous identities. Its basically a way for a blockchain to defend against someone who is making a bunch of fake nodes so that they can get more rewards. So there are 2 types of sybil resistance mechanism: Proof of work (PoW) and Proof of stake (PoS).

## Proof of Work (PoW)

So Proof of work is known as a sybil resistance mechanism because it defines a way to figure out the block author and defines a way to figure out who is the block author or which node is going to be the node that did the work to find that mine and be the author of that block.     

A single node has to go through a very expensive computation process called "mining". In PoW, it works cause no matter how many pseudo anonymous accounts you make, each one has to undergo this computationally expensive activity of finding the answer to the proof of work problem that it's trying to solve. Now you need to combine this with a chain selection rule to create this consensus. 

## Chain Selection Rule

How do we know which blockchiain is the real and true blockchain? Bitcoin and Ethereum uses this consensus called the "**Nakamoto Consensus**". This is a combination of proof of work and longest chain rule. The decentralized network says that whichever blockchain has the longest chain or the most number of blocks or number of block confirmations on it are going to be the chain that they use. 

The number of block confirmation is the number of additional blocks added on after the transaction is being added into the block. 

Proof of work also tells us where these transaction fees and block rewards go to. In this proof of work system, all these nodes are competing with each other to find the answer to the blockchain riddle (in the prev note example it was the 4 0s hash riddle). All these nodes compete to solve the answer and uses a lot of energy. Why do they compete? Cause the first node that solves the problem, gets the transaction fee and gets paid from that. They get paid in 2 different ways. One is going to be the **transaction fee** and the other is going to be the **block reward**. The block reward increases the circulating amount of whatever cryptocurrency is being rewarded. 

Some blockchains have a set time where they no longer going to give a block reward and the miners and nodes are only going to be paid via the transaction fee. The gas fees are being paid by whoever makes the transactions.

## Attacks that could happen on the blockchain 
### 1. Sybil Attack
A sybil attack is when a person creates psudo anonymous accounts to try to influence the network. On ethereum and bitcoin, it is extremely difficult as he needs to do all this work in PoW. 

### 2. 51%
The more prevalent attack is the 51% attack. Now as we saw in the consensus protocol, these blockchains are going to agree that the longest chain is the one that they are going to go with as long as it matches up with 51% of the network. Which means if you have more than 51% of the network you can fork the network and bring the network onto your longest chain. Whichever blockchain has the most buy in and is the blockchain that the whole system is going to corroborate. When nodes produce a new block and add to the longest chain, the other nodes would follow the longest chain that the rest of the network is agreeing with and add blocks to their chain and follow up. If a group of nodes had enough nodes and enough power, they can essentially be 51% of the network and influence the network in whatever direction they want it. This did happen on a blockchain called **ETH Classic**. This is why the bigger the blockchain is, the more secure it becomes.

## Disadvantage of PoW
Every single network is trying to run as fast as they can to win the problem solving race to get the rewards. So this leads to obviously an environmental impact as it consumes a lot of energy. Now due to this, a lot of other protocols have taken this idea and gone in a different sybil resistance protocol that are "environmentally" friendly and that right now is "Proof of Stake".

## Proof of Stake (PoS)
Some chains are already using the proof of stake protocol like avalanche, solana, polygon , polkadot etc. Ethereum decided to upgrade to "ETH2.0" (pronounced as eth TWO) which will also have the PoS in it as well. 

Instead of solving this difficult problem, PoS nodes put a collateral that they are going to behave honestly (aka stake!). An example is that nodes put out some ethereum as a stake that they are going to behave honestly in the network. If they misbehave in the network, they are going to remove some of their stake. Now this is pretty cool mechanism. If you try creating many pseudo-anonymous accounts, you gonna have to put stake in each of those accounts and if you misbehave you are going to have the risk of losing the money that you put up in the collateral. In this system, miners are called "Validators", they are actually just validating other nodes. Now, unlike proof of work with a concept of a race to solve the problem, in proof of stake nodes are randomly chosen to propose the new block and the rest of the validators will validate if that node has proposed the block honestly. 

#### Randomness:
So how does the blockchain choose these random nodes? ETH2.0 is using Rand DOW. This is a decentralized autonomous organization, that collectively chooses the random number and chooses which node to run next.


#### Pros of PoS
- Great sybil resistance mechanism and tells who the author of the block should be.
- Way less computationally expensive. Instead of a bunch of nodes trying to do this, only one node does it and the rest of the nodes just validates it.

#### Cons of PoS
- Considered as a slightly less decentralized network due to the upfront staking cost it costs to participate.


YAAYYY!  Now you know the non-developer side, the basics and fundamentals of the blockchain. The next note onwards we are going to begin the developer journey of a smart contract developer. The most awaited side! The coding side of developing smart contracts on the blockchain. So the question is:

![](/assets/images/2022-06-17-18-41-32.png)
