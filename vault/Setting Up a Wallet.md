---
id: c1k7l1u52kydjq3nbo6bkp9
title: Setting Up a Wallet
desc: ''
updated: 1655128902552
created: 1655126375333
---

To do anything related to developing smart contracts it is needed to have a wallet. Personally (well and also according to the majority of the general public) **MetaMask** is one of the best wallets out there.

## Setting up your ethereum wallet:

**Step 1:** Go to this website: 
> https://metamask.io/download/

**Step 2:** Add the browser extension

**Step 3:** If its your first brand new wallet then click on create a wallet here:

![](/assets/images/2022-06-13-21-28-39.png)

If you already do have a crypto wallet then just click on Import wallet
<br>

![](/assets/images/2022-06-13-21-29-20.png)

**Step 4:** Just agree and fill out and follow whatever they are asking LOL. (I'm Sree the Web3 Developer not Sree the Indian Tech Support.) Remember to store **Secret Recovery Phrase and the Private key.**  
THIS IS SUPER IMPORTANT NEVER SHARE IT. Its gonna be a bunch of random words SAVE THAT!! 


## Etherscan.io
So once you created a new wallet you can view your address at etherscan.io a block explorer
> https://etherscan.io/

So a block explorer is basically a way to view different addresses, transactions and other happenings in a blockchain. Here is an example of my address and what would it look like when we make ethereum transactions in etherscan.io. 

![](/assets/images/2022-06-13-21-37-07.png)

Its absolutely fine for people to keep their addresses public. **DO NOT KEEP THE RECOVER PHRASE AND THE PRIVATE KEY PUBLIC.** 

We wont be using the main net for our smart contract development. Instead, we'll be using test nets like rinkeby, Ropsten, Kovan etc. To find these test networks you need to hit **"Show/Hide"** test networks in the browser extention. Move all the way to the show test networks and keep it switched on.

![](/assets/images/2022-06-13-21-43-42.png)

So now we would be able to see the other test networks when we click on the extention.
<br>
![](/assets/images/2022-06-13-21-44-35.png)
    
So what are these test networks?
These test networks ressemble ethereum which acts like "ethereum" where we can use fake eth money as a way to develop and use our smart contracts. These fake ethereum or (fake eth) can be obtained through the server ethereum faucets like:

> Rinkeby Faucet: https://rinkebyfaucet.com/

Note: This is fake money. Don't get over excited when you have 48 ethereum in the Kovan server in your wallet 😂😂😂😂
You can connect your wallet to these test faucets and play around with test ethers.
Now after you got some test ether go back to etherscan (use etherscan rinkeby this time) and you can see the transaction there that you recieved some test ether! 

Now if you click on the transaction hash you can see more details on what went down in this transaction!
I always look at understanding what went down in a transaction in etherscan as a super important concept when developing smart contracts.

![](/assets/images/2022-06-13-21-58-50.png)

Components of a transaction:
<br>
- From: The wallet that sent the transaction
- To: The wallet that recieved the transaction
- Value: Amount transfered.
- Transaction fee: Amount paid to the miner to process the transaction
- Gas Price: Cost of unit of gas specified in a transaction in Ether and Gwei. Higher the gas price, higher the chance of getting included in the block,

In the next part, we gonna tackle the most confusing part about blockchain. GAS!⛽⛽⛽⛽⛽


