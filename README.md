
# Project Title

TokenMint: A Smart Contract for Creating, Managing, and Burning Tokens.

For the purpose of creating, maintaining, and burning tokens on the Ethereum blockchain, TokenMint is a smart contract. Users can create their own tokens with a name, shorthand, and maximum quantity. Additionally, the contract offers the ability to burn tokens from particular addresses and mint more tokens to specific addresses.


## Description
**TokenMint** is a flexible and powerful smart contract framework for creating, managing, and burning custom tokens on the Ethereum blockchain. It streamlines the process of issuing and controlling digital tokens, making it ideal for developers and organisations looking to deploy their own cryptocurrencies or digital assets. The contract includes public variables for key token details such as name, abbreviation, and total supply, as well as a mapping to track each address's balance. TokenMint includes a mint function that increases the total supply by crediting tokens to specific addresses, as well as a burn function that securely destroys tokens while ensuring the sender's balance is sufficient before reducing their tokens. This project caters to a range of applications, from developing in-app currencies and reward systems to managing tokenized assets, providing a secure, efficient, and adaptable foundation for a variety of blockchain-based projects.







## Getting Started
To get started with TokenMint, follow these steps to configure your development environment, deploy the smart contract, and interact with it. This guide assumes you're familiar with basic Ethereum concepts and Solidity programming.

Step 1: Open Remix.
Visit the Remix website.

Step 2: Add TokenMint Code Paste the following code into your new file:


// SPDX-License-Identifier: MIT pragma solidity 0.8.26;

/* REQUIREMENTS 1. Your contract will have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply) 2. Your contract will have a mapping of addresses to balances (address => uint) 3. You will have a mint function that takes two parameters: an address and a value. The function then increases the total supply by that number and increases the balance of the “sender” address by that amount 4. Your contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens. It will take an address and value just like the mint functions. It will then deduct the value from the total supply and from the balance of the “sender”. 5. Lastly, your burn function should have conditionals to make sure the balance of "sender" is greater than or equal to the amount that is supposed to be burned. */

contract MyToken {

// public variables here

   string public t_Name = "mikisa";
   string public t_Abbry = "MKS";
   int public total_Supply = 90;

// mapping variable here

   mapping(address => int) public balances;

// mint function

   function mint (address my_Add,int my_value) public {
    total_Supply  +=  my_value;
    balances[my_Add]  +=  my_value;
   }

// burn function

    function burn (address my_Add,int my_value) public {
        if (balances[my_Add] >= my_value){
             total_Supply  -=  my_value;
            balances[my_Add]  -=  my_value;
        }    
    }

   
}

Step 3:

1.To deploy and run the TokenMint smart contract, first navigate to Remix, an online Solidity IDE. Once there, click the "+" icon in the left-hand sidebar to create a new file named TokenMint.sol. Copy and paste the TokenMint contract code into this file. This contract allows you to efficiently create, manage, and burn custom tokens. The code defines the fundamental operations of your token, so make sure it is correct.

2.After pasting the code, navigate to the "Solidity Compiler" tab on the left sidebar. Set the compiler version to 0.8.4 or a compatible version that matches the Solidity code. To compile your contract, click the "Compile TokenMint.sol" button. This step checks for syntax errors and gets the contract ready for deployment. Compilation is crucial because it Converts your Solidity code to bytecode that can be deployed on the Ethereum blockchain.

3.After compiling the contract, navigate to the "Deploy & Run Transactions" tab. Choose the "TokenMint" contract from the dropdown menu. Fill in the following fields on the deployment form: _name with your desired token name (e.g., MyToken), _symbol with the token's abbreviation (e.g., MTK), and _initialSupply with the starting supply of tokens (e.g., 1000). Once you've entered these details, click the "Deploy" button to send your contract to the network. This process generates an instance of your TokenMint contract, which can now be interacted with.

4.After deploying the contract, you can interact with it through the available functions. To view the token details, click the name, symbol, and totalSupply buttons. To mint new tokens, navigate to the mint function, enter the recipient's address, and specify the number of tokens to mint, and then click "transact". To burn tokens, use the burn function, enter the address to burn from and the amount to burn, and then click "transact". Finally, to check the balance of an address, use the balanceOf function, enter the address, and click "call" to obtain the current balance. This interactive process helps you manage your token effectively.

## Authors

- [@doro26]

