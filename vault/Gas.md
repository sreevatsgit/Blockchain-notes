---
id: x06nq8a9lddm9d6pjbdom3o
title: Gas
desc: ''
updated: 1655456025296
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

Gas fees tend to change. The reason why gas fees might change is that depending on how busy the blockchain is, you have to pay more gas. An over simplified example is that, if there is a lot of people are sending transactions, there isnt going to be enough space for everyone's transaction to get through. **The more people use a chain, the more expensive it is to send a transaction**

Let's click to see more in the transaction screen. 
![](/assets/images/2022-06-17-16-13-39.png)
We can see that the gas limit is 32,377 and usage is 32,355. The above transaction used 32,355 gas and was sent 32,377 gas along with it spending about 99.93%. Sometimes, depending on the computation etc, it may use way more than what you would want it to use. So with each transactions you can set a limit and use only a certain amount of gas. 

This limit can be done in our metamask when we send each transaction and change our gas limit. 

Let's look at the next unit that is the Gas fees, we see a priority and a max base fees. So according to EIP1559, every transaction in ethereum comes in with a **base** fee. This is the minimum gas price that we would need to set to send your transaction. The unit of this is **Gwei**. 

## Gwei:

> 1 Ether = 10<sup>9</sup> Gwei = 10<sup>18</sup> Wei

The concept of Gwei is to understand tiny units of ethereum. 

The **Max** fee in the Gas fees refers to the maximum gas that the user is willing to pay for the transaction.
The **Max Priority** on the other hand is the max gass fees that we are willing to pay plus the max tip that we are giving to miners. 

In Ethereum the base fee ends up getting burnt which is the base gas fee x the usage by transaction. So in ethereum, whenever we send a transaction, a little bit of ethereum is removed from circulation forever (or also called "burnt"). So currently in ethereum, part of your transaction fee gets burnt and the other part goes to miners. 

>Amount of ethereum going to miners = Transaction fee - Burnt ethereum

Blockchains have limited blockspace for transactions. The gas price that costs for your transactions to be included changes based on how much demand there is. The Base gas fee goes up and down based on how many people are sending transactions and how many wanted to be included in a block

Congrats! Now we know how gas works, the next note we going to see under the hood of ethereum and understand what is going on with these transactions, these blockchains, the gas and the fundamental components of the blockchain.

