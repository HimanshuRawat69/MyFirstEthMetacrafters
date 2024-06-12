
# Project Title

Solidity
Project: Create a Token

## Description

 The contract will include the following features:

1)The contract will have public variables that store the details about your coin (Token Name, Token Abbreviation, Total Supply).

2)The contract will have a mapping of addresses to balances (address => uint).

3)It will have a mint function that takes two parameters: an address and a value. The function will then increase the total supply by that amount and increase the balance of the specified address by the same amount.

4)The contract will have a burn function, which works the opposite of the mint function by destroying tokens. It will take an address and a value, then deduct the value from the total supply and from the balance of the specified address.

5)Lastly, the burn function will have conditionals to ensure the balance of the account is greater than or equal to the amount that is supposed to be burned.

## Getting Started
### Installing

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., mytoken.sol). Copy and paste the following code into the file:

```
//SPDX-License-identifier:MIT
pragma solidity 0.8.18;

contract MyFirstToken{
    //Public variable to store token details
    string public name="MyFirstToken";
    string public symbol="MFTK";
    uint256 public totalSupply;

    // mapping addresss to balances
    mapping(address=>uint256)public balances;
    //Mint function to create new token 
    function mint(address _to , uint256 _value) public {
        totalSupply += _value;
        balances[_to] += _value;
    }

    //function to destroy tokens
    function burn(address _from,uint256 _value) public{
        require(balances[_from]>=_value,"Insufficient balance to burn");
        totalSupply -= _value;
        balances[_from] -= _value;
    }
}
```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.18" (or another compatible version), and then click on the ("Compile "the name of the file" ") for ex. comple MyFirstToken.sol button.
Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "MyFirstToken.sol" contract from the dropdown menu, and then click on the "Deploy" button.
then u can see a the below of the option ' Deployed/Unpinned Contracts ' expand it and balances mint burn etc and now u can see our code is ready to run .


## Authors

Contributors names and contact info

Himanshu

email : himanshur9034@gmail.com

## License
This project is licensed under the MIT License - see the LICENSE.md file for details
