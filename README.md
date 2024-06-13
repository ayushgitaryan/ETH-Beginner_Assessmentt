myToken Smart Contract

Description
The `myToken` smart contract is an implementation of a demo token on the Ethereum blockchain. It allows users to mint and burn tokens, manage balances, and retrieve token details such as name, abbreviation, and total supply.

Getting Started
Executing program
To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.
Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g.Token.sol). Copy and paste the following code into the file:
The contract satisfies the following requirements:
1. Public Variables: The contract contains public variables to store the details of the token, including the token name, token abbreviation, and total supply.
2. Mapping: A mapping is maintained to store the balance of each address.
3. Mint Function: A function to mint new tokens by increasing the total supply and the balance of a specified address.
4. Burn Function: A function to burn tokens by decreasing the total supply and the balance of a specified address, with a check to ensure sufficient balance.

 Public Variables
- string public TokenName: Stores the name of the token. For this contract, the token name is set to "DEMON".
- string public TokenAbbrv: Stores the abbreviation of the token. For this contract, the abbreviation is set to "DM".
- uint public TotalSupply: Stores the total supply of the token, initialized to 0.

 Mappings
- `mapping(address => uint) public balances`: Maps addresses to their respective token balances.

 Functions
Mint Function

function mint(address _address, uint _value) public {
    TotalSupply += _value;
    balances[_address] += _value;
}

-  Increases the total supply of tokens and updates the balance of the specified address.
- Parameters:
  - `_address`: The address to which the tokens will be minted.
  - `_value`: The number of tokens to mint.

 Burn Function
function burn(address _address, uint _value) public {
    if (balances[_address] >= _value) {
        TotalSupply -= _value;
        balances[_address] -= _value;
    }
}
-  Decreases the total supply of tokens and updates the balance of the specified address, provided that the address has enough tokens to burn.
- Parameters:
  - `_address`: The address from which the tokens will be burned.
  - `_value`: The number of tokens to burn.
- Condition: Ensures that the balance of the specified address is greater than or equal to the number of tokens to burn.

Authors
Ayush Aryan
github.com/ayushgitaryan

License
This project is licensed under the MIT License.
