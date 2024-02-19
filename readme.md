# MyToken - ERC-20 Token

## Introduction

MyToken is an ERC-20 token deployed on the Ethereum blockchain. It allows the contract owner to mint new tokens, burn tokens, and users to transfer tokens.

## Token Information

- **Name**: MyToken
- **Symbol**: MTK

## Getting Started

To use MyToken, you need to deploy the smart contract on the Ethereum blockchain. Follow the steps below to deploy and interact with the contract.

### Deployment

1. Deploy the MyToken contract using your preferred development environment (Remix, Hardhat, etc.).

2. During deployment, ensure that you specify the initial owner address. This address will have the exclusive right to mint tokens.

### Interacting with the Contract

#### Minting Tokens

The contract owner can mint new tokens to a specified address.

```solidity
function mint(address to, uint256 amount) external onlyOwner {
    _mint(to, amount);
}
To mint tokens, call the mint function, providing the recipient's address (to) and the amount of tokens to mint (amount).

Burning Tokens
The contract owner can burn a specified amount of tokens.

solidity
Copy code
function burn(uint256 amount) external onlyOwner {
    _burn(msg.sender, amount);
}
To burn tokens, call the burn function with the amount of tokens to be burned (amount).

Transferring Tokens
Users can transfer tokens to other addresses.

solidity
Copy code
function transfer(address to, uint256 amount) public override returns (bool) {
    require(amount <= balanceOf(msg.sender), "Insufficient balance");
    _transfer(msg.sender, to, amount);
    return true;
}
To transfer tokens, call the transfer function, providing the recipient's address (to) and the amount of tokens to transfer (amount).

Ensure that the sender has a sufficient balance before initiating a transfer.

License
This smart contract is released under the MIT License.