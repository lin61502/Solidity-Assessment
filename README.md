Solidity Assessment 

Overview:
This Solidity program demonstrates a basic custom token contract with minting and burning functionalities. It manages the total supply of tokens and tracks the balances of addresses.

Description:
The contract defines a custom token with public variables for the token name, abbreviation, and total supply. It includes functions for minting and burning tokens, along with a mapping to track token balances.

Getting Started:
To get started with this Solidity program, go to [Remix](https://remix.ethereum.org) and create a new file named MyToken.sol. Copy and paste the provided code into this file:

// SPDX-License-Identifier: MIT
pragma solidity 0.8.25;

contract MyToken {

    // Public variables
    string public tokenName = "META";
    string public tokenAbbrv = "MTA";
    uint public totalSupply = 0;

    // Mapping to store balances
    mapping(address => uint) public balances;

    // Mint function
    function mint(address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    }

    // Burn function
    function burn(address _address, uint _value) public {
        if (balances[_address] >= _value) {
            totalSupply -= _value;
            balances[_address] -= _value;
        }
    }
}

Next, compile the code using the "Solidity Compiler" tab, ensuring the compiler version is set to "0.8.25" (or another compatible version). After successful compilation, deploy the contract by navigating to the "Deploy & Run Transactions" tab and selecting the "MyToken" contract from the dropdown menu, then click on the "Deploy" button. Once the contract is deployed, you can interact with it by calling the mint and burn functions to manage the token balances.
