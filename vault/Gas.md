---
id: x06nq8a9lddm9d6pjbdom3o
title: Gas
desc: ''
updated: 1655210062670
created: 1655137039292
---
This is one of the most trickest concepts to understand in the book. 

Remember that the blockchain is run by a collection of nodes. Well all these nodes are ran by the blockchain because they all get paid for all the transactions that happen in the blockchain. 

Whenever we make a transaction, there's a node or miner or a validitator, someone is going to get paid a tiny bit of that native blockchain currency. This payment is to incentivise people to continue to run nodes and calculates how much you pay and how much the node operators get paid based on how much gas you use. 

### SO WHAT IS GAS?
Gas is a computational unit of measure. The more computation a transaction uses the more gas you need to pay. (Fairly simple?)
 
Let's go back to our etherscan transaction. We can see the gas limit and gas usage by TXN (Gas usage by transaction)

![](/assets/images/2022-06-14-03-09-22.png)

We could see that there is a limit of 249,271 units of gas on the transaction and out of that 244,204 units of gas (or 97.97%) gas was used. Now for sending things like ether technically, the units of gas is very cheap. For more complex things like miniting an NFT, depositing into a De-Fi contract etc would technically cost more gas as they are more computationally expensive.

If you have noticed there is a relationship between the transaction fee, Gas usage by the transaction and the gas price which is:

> **Transaction fee = Gas Price x Usage by TXN**

Any transaction on the blockchain comes with paying a transaction gas fee.

Gas fees tend to change. The reason why gas fees might change is that depending on how busy the blockchain is, you have to pay more gas. An over simplified example is that, if there is a lot of people are sending transactions, there isnt going to be enough space for everyone's transaction to get through. 

Congrats! Now we know the surface level on how it works, the next note we going to see under the hood of ethereum and understand what is going on with these transactions, these blockchains, the gas and the fundamental components of the blockchain.

