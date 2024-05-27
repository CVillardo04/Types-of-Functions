# Types-of-Functions

For this project, you will write a smart contract to create your own ERC20 token and deploy it using HardHat or Remix. Once deployed, you should be able to interact with it for your walk-through video. From your chosen tool, the contract owner should be able to mint tokens to a provided address and any user should be able to burn and transfer tokens.

# description 

# Getting Started

### Executing program 

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


