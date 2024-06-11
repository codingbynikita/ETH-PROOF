# ETH-PROOF
This Solidity application functions as a straightforward example of a token contract with burning and minting features. Its goal is to give users a basic understanding of how to use the Solidity programming language to create and interact with smart contracts.
## Description
In compliance with the above specifications, this contract, called MyToken, implements fundamental token functionalities. Public variables are used to record information about the token, like its name, abbreviation, and total supply. It also tracks token balances for every address via a mapping. The contract additionally serves two key roles: burn, which destroys tokens to lower the total supply, and mint, which creates new tokens to increase the total supply.
## Getting Started
To interact with this contract:
1.	Visit https://remix.ethereum.org/, an online Solidity IDE.
2.	Create a new file and save it with a .sol extension (e.g., MyToken.sol).
3.	Copy and paste the provided code into the file.
4.	Ensure the compiler version is set to 0.8.26 or another compatible version.
5.	Compile the code by clicking on the "Solidity Compiler" tab and then clicking the "Compile MyToken.sol" button.
6.	Once compiled, deploy the contract by clicking on the "Deploy & Run Transactions" tab, selecting the MyToken contract from the dropdown menu, and clicking the "Deploy" button.
7.	After deployment, you can interact with the contract by calling its functions. For minting tokens, use the mint function by providing an address and a value. To burn tokens, use the burn function with the address and value parameters.
## Executing Program
```pragma solidity 0.8.26;

contract MyToken {

    // public variables
    string public tokenName = "META";
    string public tokenAbbrv = "MTA";
    uint public totalSupply = 0;

    // mapping variable
    mapping(address => uint) public balances;

    // mint function
    function mint(address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    }

    // burn function
    function burn(address _address, uint _value) public {
        if (balances[_address] >= _value) {
            totalSupply -= _value;
            balances[_address] -= _value;
        }
    }
}
```
## Author
Nikita Raj Jaiswal
