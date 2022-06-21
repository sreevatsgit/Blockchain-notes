---
id: 6eig527ufa86gfto2vg82zv
title: Writing your First Smart Contract
desc: ''
updated: 1655541012467
created: 1655462580025
---

So now you learnt the basics of ethereum, how the blockchain operates and the parts of the transaction. Welcome to the "developer" side of smart-contracts!

Pro Tip: If you would have any errors in your code there is always stackoverflow to solve your issues. 

K to start things off lets head over to the Remix Ethereum Integrated Development Environment. This is where we are going to code and interact with our smart contract. 

> https://remix.ethereum.org/

Remix is a very powerful tool that has features that we can see that allows us to interact with our smart contract. Slowly we would move over to our local computer environment. 

In remix there are a lot of plugins as well. Since we are using solidity, we can go and click on the solidity plugin.

Click on the contracts folder and click the page icon to create a new file.
![](/assets/images/2022-06-17-22-58-07.png)

We are going to create a new file and name it SimpleStorage.sol.

The **.sol** tells our compiler that this file is going to be a solidity file and that we are going to code solidity in this. 

**Solidity** is the primary coding language of smart contracts. There are a few others as well but solidity is the dominant smart contract out there. 

Now if you click on the button below the files button you can see a bunch of parameters to compile our solidity code that we can run it.

![](/assets/images/2022-06-17-23-04-52.png)

K the most awaited parts of the notes has finally arrived. Lets code!!

We generally whenever we are learning a new programming language we do a nice little "Hello World" message. For solidity however the first program that we are going to write is a Simple Storage.

## Steps of writing a smart contract

### Step 1: Writing the version of Solidity 
The first thing that we are going to need for any smart contract is the version of solidity that we are going to use and this should always be at the top of your solidity code. Solidity is a constantly changing and updating language. It is new as compared to something like a python or a java or a C++. So we need to tell our code "Hey, this is the version that I would want you to use."

<br>
So to add the solidity version we gotta write:

> pragma solidity < and a version that we want to use >

**Examples**:
If you would like a specifc version of solidity that you would want to use: 
> pragma solidity 0.8.6;
<br>
// current version is 0.8.12

The "//" is actually a comment in which we can type stuff after this and the compiler wont execute it. Proper use of commenting can make code maintenance much easier, as well as helping make finding bugs faster. So even though comments are not being compiled by the compiler, it is still super important.

There are other ways of mentioning the version of solidity to be used. Maybe we are ok in having a newer version of solidity by putting a '^' (or also known as a carrot). Something like this:

> pragma solidity ^0.8.6;

This is how we tell solidity any version of 0.8.6 and above is ok for this contract. So 0.8.7, 0.8.8, 0.8.9, 0.8.10 and so on would work.

If we wanna use solidity version in a particular range we use something like:

> pragma solidity >=0.8.6 < 0.9.0;

This means that we want to use the solidity version greater than and equal to 0.8.6 but less than 0.9.0. This means that any compiler between 0.8.6 and 0.9.0 would work. 

You would have also noticed a ";" in the line. That is a statement terminator and every line in solidity needs to end with a ";". This is how we can tell solidity it is the end of the line. 

### Step 2: Writing the SPDX License Identifier

At the start of the code we need to write an SPDX license identifier before our solidity version declaration. This is in a comment and its optional but some IDEs may flag a warning that you do not have one. This is to make licensing and sharing a lot easier. 
To do an SPDX License Identifier we just need to write

> // SPDX-License-Identifier: MIT

**HIT CTRL+S or CMD+S to compile whatever you have written.**

### Step 3: Defining our contract

To define our contract you need to write the key word **contract**. This tells solidity that the next pieces or section of code is going to be a contract. You can think of a contract to be similar to "class" in any object oriented programming. So to define it we can write:

> **contract** SimpleStorage {
    <br>}

So the name SimpleStorage is the name of our contract that we are defining. Now lets compile it again.

Hypothetically, we can deploy this contract right now and it can become a valid contract. Yayyy! you wrote your first contract!

![](/assets/images/2022-06-18-16-29-31.png)

