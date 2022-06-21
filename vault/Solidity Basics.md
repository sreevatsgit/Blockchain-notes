---
id: w4opqid1if14hcqfq5ayknt
title: Solidity Basics
desc: ''
updated: 1655843545301
created: 1655543766173
---
## Data Types

The 4 most basic types are: 
1. boolean: Defines a true or false
2. uint: Unsigned integer which is only positive
3. int: Positive and negative whole number
4. address (bytes): An address (literally)
5. String: words and characters

There are many other types. The reason as to why we have so many types is that we use them to define what variables are. Variables are basically holders for values.

## Defining a variable
To define a variable we use this format:
> data type < variable name >;

 For example
> **uint number;**

So this "number" variable is going to represent a uint value.
We can also initialize these variables with values like so:
> uint number = 32 ;

uint is a special data type as we can specify how many bits or bytes we would want to allocate to this number variable.
Bits and bytes are fundamental units in Computer Science. To specify how many bits you would want to allocate for this variable you can say:

> uint64 number = 32;

This means that we are allocating 64 bits to that particular variable. If you do not specify how many bits, uint would default it to 256. The lowest you could go is 8 and we go by steps of 8 (8,16,32,64... all the way to 256 (max))

We could do the same thing for int

> int256 FavoriteNumber = -20

We could also do address where we can grab our meta mask address and store it in a variable like so:

> address myaddress = 0x50C179B8553D77f0fAB72dc7e940C8A819F21b1A;

We could even have a bytes and string objects like so
>bytes32 pet = "dog";  
// allocating 32 bytes to the variable pet.
<br>
string NumberinText = "Five";

We cannot write bytes64 cause the maximum size a bytes object can be is 32. So it will throw a "declaration error" in our remix compiler.

Let's go back to our simple storage contract that we created in the previous note. We can see that it is a blank slate that does nothing but it is defined as a contract.

Let's add a couple of variables that we would like to store in our smart contract.

> //SPDX-License-Identifier: MIT
<br>
pragma solidity ^0.8.6;
<br>
contract SimpleStorage {
<br>    uint256 StoreNumber;
<br>}

In solidity if we do something like this wherein we do not initialize any value inside "StoreNumber", the "StoreNumber" actually gets set to the default value. The default value for solidity is whatever the null value is i.e 0.


## Functions

Functions or methods are self-contained modules that will execute some specific set of instructions for us when we call it. Functions get identified by the compiler by the keyword: "**function**" 

Let's create a function called "store" that will change the value of the given number to some new value. And the number that we are going to be changing it to is going to be the variables that are passed to our store function. So we are going to allow our store function to taken in a variable of type uint256. And after that we are going to 

> //SPDX-License-Identifier: MIT
<br>
pragma solidity ^0.8.6;
<br>
contract SimpleStorage {
<br>    uint256 StoreNumber;
<br>
<br> ** function store (uint256 _number) public {
       <br> StoreNumber = _number;
    }
**<br>}
  
Let's compile this program. When we have a green check mark and no errors we can move forward in deploying the contract to the blockchain. 

## Deploying

Now to see the smart contract in action we need to deploy it in a fake environment blockhchain. We are going to deploy it on a local network. Head over to the deploy and run transactions tab. 

![](/assets/images/2022-06-18-18-34-08.png)

We are going to deploy it to a Javascript VM. A javascript VM is a fake local blockchain which we can simulate transactions quickly without waiting for them to go on a test net. 

The next section is the **account** section. When we run with our fake JavaScript VM, we are given a fake bunch of accounts from where to deploy from and we are given 100 eth to each of these fake accounts.

For our transactions we are also given a gas and we can also choose which contract we would like to deploy.
Now we just hit the "deploy" button. 

![](/assets/images/2022-06-18-18-36-54.png)

If we scroll down we can see the deployed contract and tells us that simple storage was deployed at the given address (0XD91....)

Every single smart contract has an address, just like how our wallets have an address. When we deploy the contract its actually the same as deploying a transaction. Anytime, we modify any value in the blockchain, we are sending a transaction. Ethereum Remix sort of acts as a simulator like deploying it on a testnet.

Now let's look at the orange button. The orange button represents the store function that we have created. So if we type on the textbox next to the store button we actually call the function and execute a transaction on our fake Javascript blockchain. Let's hit the store button now. 

![](/assets/images/2022-06-18-18-43-57.png)

We can see below that we have created a new transaction and now the new StoreNumber is 444 (cause I entered 444 in my textbox).

So how do we know whether the StoreNumber is saved as 444? Well the visibility of our StoreNumber is not set to public. So we can't see anything. So all we need to do is change the visibility of the number as public as so. 


> //SPDX-License-Identifier: MIT
<br>
pragma solidity ^0.8.6;
<br>
contract SimpleStorage {
<br>    uint256 **public** StoreNumber;
<br>
<br> function store (uint256 _number) public {
       <br> StoreNumber = _number;
    }
<br>}
  
Now let's re-compile the contract. Go to our deploy tab. 

Delete (press the x) of the previous contract view so that you don't get confused. 

Deploy.

We can see that there is a new StoreNumber blue button. This blue button represents the public variable and resemmbles a function that tells us to show what StoreNumber is.

![](/assets/images/2022-06-18-18-50-57.png)

Let's click the StoreNumber Button you can see the number is 0. That is because we haven't given any value to it and the default value is 0 for uint256. Now let's type on the text box (say 56). Hit the store function button and now click on the StoreNumber. You can see that the number that StoreNumber get's updated to 56. 

![](/assets/images/2022-06-18-18-53-58.png)


## Visibility Specifiers

Functions and variables can have one of these 4 visibility specifiers. 
### Public
Allows visible externally and internally. This means anyone who interacts with this contract or sees this contract can see what is stored in the variable/ function. It creates a getter function for storage/ state variables. When we add the keyword public what we are actually doing is that we are creating a getter function that returns a value of the variable. That's why the blue button pops up. The blue button is a function that returns the value of StoreNumber.

### Private
Private means only this specific contract can call this function. They are only visible to the current contract

### External
Extrnal functions are only visible externally meaning thta somebody outside this contract can call this function. 

### Internal
Internal visibility means only this contract and the children contracts are able to read it. 

Default visibility => Internal which means that these internal functions and variables can only be called by this specific contract or derived contracts.

Note: The more computationally expensive its going to be, the more gas you are going to spend. As you can see from the transaction logs, it took more gas as it was doing something that required more computation. 
The more stuff you do in your function, the more the gas is going to cost.

## Scope

So lets take a dive into scope. Our StoreNumber is in something called as the global scope meaning anything inside that SimpleStorage contract brackets can access the favorite number variable. 

When you create variables they can only be used in the scope that they are (as in inside their curly brackets "{ }" )

Now let's try adding a retrieve function inside our contract.

> function retrieve() public view returns(uint256)
<br>
{ return StorageNumber;
<br>}

Compile and deploy. Now we can see that there are 2 blue functions but one orange. So what's the difference??

So the difference in it lies in the "view" keyword. There are 2 keywords that notate a function that doesnt actually spend gas to run. Those keywords are "**view**" and "**pure**"

**View functions** are those functions in which we are just going to read state from the contract. For example our retrieve function is just reading what our StorageNumber function's value is. A view function does NOT allow any modification of state. You cannot update the blockchain at all with a view function.

**Pure Functions** are those functions that also does not allow any modification of state variables. Not only that they do not allow reading the state of the blockchain, which means we couldn't read StorageNumber either. Instead what we can do: 

> function add() public pure returns (uint256) {
    <br>return (1+1);<br>
}

Now if we call a view function or a pure function, we do not need to spend any gas, since we are just reading from the blockchain. Remember: We spend gas only if we modify the blockchain state. Clicking the blue buttons, will not make any transactions. If there is a function that is updating state that calls a view or pure function that is the only time it will cost gas. 

For example if our store() calls the retrieve() function, since store() isn't a view/pure function, we would need to pay the cost of retrieve since reading from the blockchain, costs computation and gas. So note:

> ***Calling view functions is free unless you are calling it inside a function that costs gas.***

The "returns" keyword in our function tells us what the function would give us after we call it. So we say the retrieve() is going to return a uint256 when we call it.

## The Struct

In our SimpleStorage contract our StoreNumber allows us to store a one simple uint256. Now what if we want to store a range of numbers? Or a whole bunch of people who have different numbers?
There are several ways in which we can approach this. One way is to create a "struct" of people. Struct is basically a defining our own new type in solidity. It creates an object that holds different datatypes inside it. So we can create a people's object that holds someone's name and their number. To that we code in:

> struct People {
    <br> uint256 StoreNumber;
    <br> string name; <br>
}

Now we created like uint256, bytes etc. we created our very own new type called "People". Like how we created a variable like:  

uint256 public StoreNumber; 

We can say

> People public person = People({
    StoreNumber = 55, name: "Sree"
});

The "()" signifies that we are creating a new person and since we made it a struct we add "{ }" to let solidity know that we are getting from these struct variables.

Now compile and deploy we get this output:

![](/assets/images/2022-06-21-13-06-56.png)

You see that there is a 0 and a 1. These show the index of the variables. Typically in computer science we start with the number 0. So our 0th index stores our uint256 which stores our StoreNumber which is 55 and at index 1 it stores a name that stands for "Sree". Whenever we have a list of variales inside an object in solidity, they get automatically indexed. So favorite number gets indexed to 0 slot. Now let's change our struct a bit.

> struct People {
    <br> uint256 StoreNumber;
    <br> **string StoreAlphabet;**
    <br> string name; <br>
}

If we compile the contract again we can see that the StoreAlphabet gets stored at index 1 and name gets stored at index 2. 
(Remove the StoreAlphabet line to continue with the example)

## The Arrays
Now this is nice. But imagine you want to store a bunch of people's numbers. Well you could copy and paste the people and change each entry. Or we can do the pro way is that we can use a data structure called as an array.

An array is a sequence of objects. Creating an array is similar to creating othe variables.

> People **[]** public individuals;

We can also use it for a regular datatype like so:

> uint256 **[]** public StoreNumberList;

Now if we compile we have a blue people variable. Since it is public and a variable it is automatically given a view function. And instead of giving us a single button its giving us a form to fill out. It wants to take a uint256 and give us an input parameter. But no matter what you put in the box right now we get nothing back. 

When we say "[]" and put nothing inside the brackets,  type of array is known as a dynamic array as the size of the array is not given at the array initialization.

If we were to say:

> People [3] public individuals;

This shows that the people array can only hold 3 people. If we don't give it a size it could be any size and the size of the array can grow and shrink as we add and subract people.

So lets go ahead and add an "individual" to the array. We are going to create an "add" function

> function addPerson(string memory _name, uint256 _StoreNumber ) public {
    <br> individuals.push(People(_StoreNumber, _name));
}

".push()" is an array adding function wherein we "push" a value into the array. So we are pushing a new "People" into the array that grabs the StoreNumber and the name

We can also create a new variable of type people like and push that variable into the array

> function addPerson(string memory _name, uint256 _StoreNumber ) public {<br>
    <br> People memory newPerson = People({StoreNumber: _StoreNumber, name: _name});
    <br> people.push(newPerson); <br>
    <br>}

Now lets compile it lets add on our addPerson textbox as Sree, 7 and now lets click the people and add the 0th person  button we would get it saved!

![](/assets/images/2022-06-21-14-59-43.png)

We could write another name say Jay and put the store number as 430. But in our people box we gotta put 1 (as it is a new person and since we are dealing with array indexes the next index after 0 is 1) to view the entry.

![](/assets/images/2022-06-21-15-02-07.png)

Another way to do push into an array is that we can remember the order of which the struct was written. For example the first thing that was written was the StoreNumber and the second was the name. So a way more simpler way to write it is by just putting the parameter variables of the functton and deploying it:

> function addPerson(string memory _name, uint256 _StoreNumber ) public {<br>
    <br> People memory newPerson = People **(_StoreNumber, _name)**;
    <br> people.push(newPerson); <br>
    <br>}

 
## Calldata, Memory and Storage

EVM can access and store information in 6 places:
1. Stack
2. Memory
3. Storage
4. Calldata
5. Code
6. Logs

Let's focus only on Calldata, memory and storage

Calldata and memory mean that the variable is only going to exist temporarily. Looking at the above addPerson function, we can see that the "_name" is a "memory" variable meaning that it only exists temporarily during the transaction this addPerson transaction is called. 

Storage variables exist even outside the function execution. Even though we don't specify at StorageNumber, it automatically cast to be a storage variable. 

Since we do not need the name variable any more as the function runs, we can keep it as "memory" or "calldata".

We only use calldata when we don't modify that variable. So if we say:

> function addPerson(string **calldata** _name, uint256 _StoreNumber ) public {
    <br> **_name = "Sreevatsan"**
    <br> People memory newPerson = People **(_StoreNumber, _name)**;
    <br> people.push(newPerson); <br>
    <br>}

It's gonna throw an error. (LOL)

But if you put memory and save it, that error goes away. So in summary:

- **Calldata** is temporary variables that we can't be modify

- **Memory** is temporary variables that can be modified

- **Storage** is permanent variables that can be modified

So you might be wondering, "why aren't we putting a calldata/ memory for _StoreNumber but we putting for _name??"

Well try it out! You will get an error LOL. So when we compile it we get an error saying: 
**
"TypeError: Data location can only be specified for array, struct or mapping types, but memory was given"**

Well, arrays, structs and mappings are considered special types in solidity. Solidity automatically knows where uint256 is going to be. It's gonna know that the uint256 is going to live in memory. But it's not sure what a string is going to be. To tear down bare bones on what a string is, string is basically an array of bytes. Since its an array, we need to tell solidity the data locations of arrays structs and mappings.


So, structs, mappings and arrays, need to be given this memory or calldata keyword when adding them as a parameter to functions.


## Mapping

Well finding people outta a tiny array seems easy. But what if we need to find these people with a huge array list? We cannot use brute force by keying in every index to search the entry. So let's find a "quicker" way to store information that allows quicker access.

Another excellent data structure that we can use is mapping. Mapping is like a dictionary. It is a data structure where a key is mapped to a single value. So to create our mapping variable we just create it like how we create all our other variables.

> **mapping (string => uint256) public NameToNumber;**

This line of code means that we are creating a public mapping variable called NameToNumber that maps the string to a uint256 value. Now that we have created the variable lets add value to it

Let's go back to our addPerson function and add inside 

> NameToNumber [_name] = _StoreNumber

Let's compile and deploy this contract. We can see a new button. To create a new button 