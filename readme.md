# Token Contract

This solidity Program is a basic representation of Tokens. It allows minting and burning of tokens through a contract called myToken. 

## Description

The code represents a token contract called MyToken. It allows minting and burning of tokens. The contract has public variables for the token's name, abbreviation, and total supply. It includes a mapping to track token balances per address. The mint function int he code increases the total supply and adds tokens to the sender's balance and  The burn function in the code deducts tokens from the total supply and the sender's balance, but only if the sender has enough tokens to burn.

## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., Tokens.sol). Copy and paste the following code into the file:

```javascript 
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

/*
       REQUIREMENTS
    1. Your contract will have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply)
    2. Your contract will have a mapping of addresses to balances (address => uint)
    3. You will have a mint function that takes two parameters: an address and a value. 
       The function then increases the total supply by that number and increases the balance 
       of the “sender” address by that amount
    4. Your contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens. 
       It will take an address and value just like the mint functions. It will then deduct the value from the total supply 
       and from the balance of the “sender”.
    5. Lastly, your burn function should have conditionals to make sure the balance of "sender" is greater than or equal 
       to the amount that is supposed to be burned.
*/

contract MyToken {

    // public variables here

    string public token_name="KRISH";
    string public token_abbrv="KRS";
    uint public ttl_sply=100;
    
    // mapping variable here

    mapping (address => uint ) public balances; 

    // mint function

    function mint (address add, uint value) public {
        ttl_sply += value;
        balances[add] += value;
    }

    // burn function

    function burn (address add, uint value) public {
        if(balances[add] >=value)    // if the statement is correct then the tokens will burn
        {
            ttl_sply -= value;
            balances[add] -= value;
        }
    }
}

```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.18", and then click on the "Compile Tokens.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "Tokens" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with the contract and can mint or burn tokens by inputing the arguments passed i.e the value and the address and then you can call the function to see the balance left. If you don't have an address then  you can copy the address from Accounts Box in the deploy and transactions menu.


## Authors

Chinmay Rajwanshi

## License

This project is licensed under the MIT License
