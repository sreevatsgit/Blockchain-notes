---
id: f0dtjjzyv7elu6fynzdff3x
title: Under the hood of Ethereum!
desc: ''
updated: 1655456190961
created: 1655210082300
---
At this point technically we could just dive right into the coding, (and you are welcomed to do so) but if we learn what is happening under the hood it would certainly make you a better programmer. 

## Hashing
Hashing is one of the key concepts in the working of a blockchain. So what is it?

Well a Hash is just a **unique** string of fixed length, that is meant to identify a piece of data. They are created by putting a piece of data into a hash function.

Ethereum uses a hashing algorithm called "Keccak256"

You could go to this website to see how the hashing works
> https://andersbrownworth.com/blockchain/hash

This uses SHA256 hash function (which is basically a way to hash data). As you type in the data whatever you would like (your name, or a thing etc.), you going to see that the hash output below changing too. That is cause the data that you typed in gets feeded into the SHA256 function to give a desired unique fixed string to update a data piece. And you can see that if you put more and more data in the text box, the length of the string never changes.
![](/assets/images/2022-06-14-20-48-30.png)

![](/assets/images/2022-06-14-20-50-15.png)

## Block
A block in a blockchain is basically a list of transactions mined together.
Now that we understood what a Hash is, we can then move on to a block! You could head over to this link right here:
> https://andersbrownworth.com/blockchain/block

Its literally the same thing as the hashing function but, instead of just having "data" there is a Block, Nonce and Data. So instead of just hashing data, its going to hash all the block, the nonce and the data and give out a fixed length hash string.
![](/assets/images/2022-06-14-20-52-18.png) 

Now let's hit the mine button. Now you can see the nonce changed!!! You can also see that the hash starts with 4 0s and the color of the box goes from red to green.

![](/assets/images/2022-06-14-20-53-06.png)

When we talk about **mining** we talking about miners solving a problem. Now in this website, the problem that the miners had to solve was that they had to find a nonce value that when hashed with block 1 with the data, it would start with 4 zeros. The only way for them to really do that is a brute force (meaning starting the nonce value from 1,2,3 until when the nonce value allows them to solve the problem ie start the hash with 4 zeroes).  The nodes get paid for mining the blocks. When the nonce was incorrect, it hasn't yet solved the problem thus keeping the box red, only when it was green when it shows that the nonce has solved the issue. 

The specific problem changes from blockchain to blockchain, ethereum has a problem that miners to solve, bitcoin has another problem etc. But the concept is going to be the same. A block, data and nonce. So the **nonce** is a solution number to solve a problem. Quite interesting isn't it? 
<br>

So blockchain miners mine by going into this computational intensive process to find the nonce to solve the problem.

## Blockchain 

To understand the blockchain this is another good link that could be used:
> https://andersbrownworth.com/blockchain/blockchain

Now we can see that there are multiple blocks but with an additional column called **Previous**. The **Previous** is going to be pointing into the previous hash of the last block. So if we look at Block 2 the hash of Prev is the same as the hash in Block 1 as shown in the diagram below.
<br>
![](/assets/images/2022-06-14-21-19-12.png)
 
But have a look at Block 1. It's previous is all 0s meaning that that's the first block that there is in the blockchain. This "first block" in a blockchain is known as the **genesis** block where the previous hash points to a hash that doesn't exist (i.e 0000...). In the blockchain the hashing algorithm considers to hash the block, nonce, data and the **previous hash** to obtain the fixed string. Now the nonce solves the same 4 0s problem while also accounting into the previous hash. We can see that if we mint 1, the other blocks turn red or invalid (right nonce that solves the problem not yet found!). The previous hash changes thus changing the current hash of the block like so:
![](/assets/images/2022-06-14-21-35-40.png)

This is how we can say that blockchains are immutable. Anytime you change one thing, you ruin the rest of the chain. But if we mint each and derive the correct nonce, we could get all the blocks to come out as valid like so.
![](/assets/images/2022-06-14-21-38-45.png) 

So now to achieve this in all the blocks needless to say that it is a huge task thus becoming computationally expensive and time-consuming. And further and further down the line you get, the harder and harder it becomes to re-hash and redo the entire blockchain. It becomes very hard to change something in the past. 
You could be the owner of a blockchain and say: "Hey I can change everything, though it may be expensive", but that's where the decentralized nature comes in and makes it extremely powerful to avoid such a central authoritative power. 

## The Distributed Blockchain: 
NO DECENTRALIZED AUTHORITY!!

![](/assets/images/2022-06-14-22-19-31.png)

Lets go to the next link which explains how a decentralized nature blockchain works:
> https://andersbrownworth.com/blockchain/distributed

So we got the same structure as we seen before in a blockchain with the block, nonc, prev and hash solving the same 4 0s in the hash string problem. But we another added component that is Peer A, Peer B and Peer C that are running this blockchain technology that are weighted equally (having the same power). We can see that all 3 Peers have the same final hash.

Now lets do the same block changing data thing on Peer A. We get a couple of invalid, and then we re-mine to fix the correct nonces. Notice how the last hash of Peer A was different as compared to the last hash of  Peer B and Peer C. So when peer B and C has the same hash it acts as a validator and would say to peer A:

![](/assets/images/2022-06-14-21-56-24.png) 

And Peer A would stop participating in the mining rewards as they literally just forked and started their own isolated blockchain with a different historical data. So that's how in the blockchain world there isn't any centralized entity. Peer A might wanna start adding in their own data but in the blockchain always remember democracy rules. Peer B and Peer C's majority validation, would show that peer A is wrong thus excluding it completely. 

## Tokens:
Hashing with strings may be dope and stuff but lets make it more sophisticated. Let's use the token's link in the same website:
> https://andersbrownworth.com/blockchain/tokens

Instead of data, we are using transactions to give a more sophistication to our hash function. So this represents all the transactions that are happening in this block. It literally uses the same concept of a decentralized validity check in a decentralized blockchain.

So we observed how a simple hash function grew up to be a decentralized blockchain that hashes transactions.
Now the way how the real-world blockchain works instead of random stuff put into the data section, it's going to be solidity code being put inside of it that defines ways to interact with the protocols on chains.


## Public and Private Keys:

For this tutorial, we still going to use Anders Brownworth's website on how public and private keys work.
> https://andersbrownworth.com/blockchain/public-private-keys/keys

As recalled earlier, a private key is something that you wanna keep it secret and is only known to the key holder to sign transactions. It's basically a secret password for your transactions LOL. 

So we can feed in any private key that we would want and it would spit out a public key like so:

![](/assets/images/2022-06-14-22-27-10.png)

So what happens here is (for ethereum and bitcoin) they use the "**Elliptic Curve Digital Signature Algorithm**"  or the **ECDSA** which uses elliptic curve cryptography and creates this public key. The public key is derived from your private key. If you would like to read on how the algorithm works its here:
> https://cryptobook.nakov.com/digital-signatures/ecdsa-sign-verify-messages

Now that public key is what everyone can access to. The whole world can see it. Similarly, the private key we don't want the public to see it. 

**So what is its uses?**
Well, a private key acts as a passoword to sorta sign transactions. On the other hand the public key acts as a verification to verify the transaction

## Signatures
Let's move over to the signing signatures tab at:
> https://andersbrownworth.com/blockchain/public-private-keys/signatures

Similar to using the SHA256 in hashing, the message gets converted to a "message signature" using the ECDSA once we hit the sign button:

![](/assets/images/2022-06-15-22-49-58.png)
 
Now what's really powerful about this ECDSA is that you can create your message signature from your private key but you cannot derive the private key from the message signature. Signing is a process in which a user with a private key signs with a transaction by their private key being hashed with the transaction data. 
<br>
Now if we move to the verify tab, it basically verifies that signature is yours. 

Now if someone tries to like "alter" the signature, its gonna give an invalid and the system says that signature is a fake and not verified to the public key. (The Black lines are indicators that I have created to show that I changed the signature)
![](/assets/images/2022-06-15-23-08-55.png)

## Transactions

Let's take the concepts on public and private keys and apply them to a transaction
> https://andersbrownworth.com/blockchain/public-private-keys/transaction

Lets say I want to transfer $30 to a wallet. Your private key (or the person who is sending $30) will sign the transaction and churn out a message signature 
(hashes the amount, sender's address and reciever's address) which is the public key. The public key is then used as a verification tool which anybody else in the world can use it to verify the transaction. As you can see below the message signature = Message verification

>Message Signing
![](/assets/images/2022-06-17-15-56-56.png)

>Message verification
![](/assets/images/2022-06-17-15-57-35.png)

Amazing! Now that we know what moves under the hood of ethereum let's look at how it is being implemented in the real world.