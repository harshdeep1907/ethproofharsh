# ethproofharsh
Token Management Smart Contract
This Solidity smart contract represents a simple token management system. It allows users to mint (create) and burn (destroy) tokens, effectively managing the total supply and individual balances of those tokens.

## Contract Details
- `_Token Name`: ModifiedToken
- `_Token Abbreviation`: MT
- `totalSupply`: An unsigned integer representing the total supply of the token.
The contract keeps track of the total supply of tokens and maintains a mapping of addresses to their token balances.

## Functions
- `_mintTokens`
This function allows the creation of new tokens. It takes two parameters:

- `_address _receiver`: The address to receive the newly minted tokens.
- `_uint _amount`: The amount of tokens to mint and add to the receiver's balance.
When called, this function increases the total supply by the specified _amount and increases the balance of the _receiver address by the same amount.

- `_burnTokens`
This function allows the destruction of tokens. It takes two parameters:

- `_address _holder`: The address whose tokens are being burned.
- `_uint _amount`: The amount of tokens to burn.
Before burning the tokens, the function checks if the balance of the _holder is greater than or equal to _amount. If the condition is met, the function deducts _amount from the total supply and from the _holder's balance.

Note: The burning operation will only proceed if the _holder has a sufficient balance to cover the specified _amount.

## Example Usage

1. Deploy the `MyToken` contract to a supported Ethereum network.

2. Once deployed, you can interact with the contract by calling the following functions:

   - `mint`: Creates new tokens and assigns them to a specified address.
     - Parameters:
       - `_address`: The address to which the tokens will be minted.
       - `_ammount`: The amount of tokens to be minted.

   - `burn`: Destroys existing tokens by reducing the total supply and the balance of a specified address.
     - Parameters:
       - `_address`: The address from which the tokens will be burned.
       - `_ammount`: The amount of tokens to be burned.

// Create a new token contract instance
MyToken tokenContract = new MyToken();

// Mint 100 tokens to a specified address
tokenContract.mintTokens(addressToReceiveTokens, 100);

// Burn 50 tokens from a specified address
tokenContract.burnTokens(addressToBurnTokensFrom, 50);

## License

This contract is licensed under the MIT License. SPDX-License-Identifier: MIT.
