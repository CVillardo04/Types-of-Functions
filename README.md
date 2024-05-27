# Types-of-Functions

For this project, you will write a smart contract to create your own ERC20 token and deploy it using HardHat or Remix. Once deployed, you should be able to interact with it for your walk-through video. From your chosen tool, the contract owner should be able to mint tokens to a provided address and any user should be able to burn and transfer tokens.

# description 

This smart contract is an unique implementation of an ERC20 token written in Solidity with the OpenZeppelin library. The code creates a new token called "ChesterToken" with the symbol "ETH" and provides functionality for minting, transferring, and burning tokens. Here's a comprehensive look at the contract's structure and working properly.

# Getting Started

### Executing program 

To execute this program, you may use Remix, an online Solidity IDE; to get started, go visit https://remix.ethereum.org/.

Once on the Remix website, click the "+" symbol in the left-hand sidebar to create a new file. Save the file as Types-of-Functions.sol. Copy and paste the code below into the file.

Contract Declaration and Imports:

* The contract imports ERC20 from OpenZeppelin, which offers the standard ERC20 implementation.
* It also imports Ownable, which isn't utilized in this contract but is commonly used for ownership management.

State Variable:

* address public owner: This variable contains the address of the contract owner, who has unique powers like as minting new tokens.

Constructor:

* The constructor defines the token's name as "ChesterToken" and its symbol as "BIT".
* It also designates the deploying address (msg.sender) as the owner and produces an initial quantity of 100,000 tokens (adjusted for decimals) for the owner.

Modifiers:

* OnlyAdmin: This modification restricts some functions to being called only by the owner.

Minting Function:

* createTokens(address recipient, uint256 amount): This method enables the owner to make new tokens and send them to any given address.

Transfer Function:

* transferTokens(address recipient, uint256 amount): This method allows anybody to send tokens to another address. However, this method is superfluous because the ERC20 standard already has a transfer function that achieves the same objective.

Burn Function:

* destroyTokens(uint256 amount): This method enables any user to burn a specific number of tokens from their own account.
 
      // SPDX-License-Identifier: MIT
      pragma solidity >=0.6.12 <0.9.0;

      import "@openzeppelin/contracts/token/ERC20/ERC20.sol";
      import "@openzeppelin/contracts/access/Ownable.sol";

      contract ChesterToken is ERC20 { 
      address public owner;

      // Constructor to set the token name and symbol
      constructor() ERC20("ChesterToken", "ETH") {
        owner = msg.sender;
        _mint(msg.sender, 10000 * (0 ** 18));
      }
 
      // A modifier that restricts function access to the owner/admin
      modifier onlyAdmin() {
        require(msg.sender == owner, "Caller is not the owner");
        _;
      }

      // Function to mint new tokens, restricted to the owner
      function ChesterTokens(address Address1_recipient, uint256 amount) external onlyAdmin {
        _mint(Address1_recipient, amount);
      }

      // Function to transfer tokens, not needed to override transfer function from ERC20
      function transferTokens(address Address2_recipient, uint256 amount) external returns (bool) {
        _transfer(msg.sender, Address2_recipient, amount);
        return true;
      }

      // Function to burn tokens from the caller's account
      function burnTokens(uint256 amount) external {
        _burn(msg.sender, amount);
      }
      }

## Author 
Chester Villardo
8215358@ntc.edu.ph

## License  
 This project is licensed under the MIT  License - see the .README.mdfile for details

