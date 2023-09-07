# Solidity Token
 Creating the token
 This Solidity program demonstrates the basic syntax and functionality of the Solidity programming language. The purpose of this program is to create a new token and use the mint, burn and 
 other functions which I learnt in solidity beginner course.

 # Description
 In this program I have used basic solidity functions such as mint and burn to show how the token works.

 # Getting Started

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., HelloWorld.sol). Copy and paste the following code into the file:



    pragma solidity ^0.8.0;
    contract MyToken {
    string public name;
    string public symbol;
    uint256 public totalSupply; 

    mapping(address => uint256) public balances;

    constructor(string memory _name, string memory _symbol, uint256 _totalSupply) {
        name = _name;
        symbol = _symbol;
        totalSupply = _totalSupply;
        balances[msg.sender] = _totalSupply;
    } 

    function mint(address _to, uint256 _value) public {
        totalSupply += _value;
        balances[_to] += _value;
    }

    function burn(address _from, uint256 _value) public {
        require(balances[_from] >= _value, "Insufficient balance");
        totalSupply -= _value;
        balances[_from] -= _value;
    }
      }

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.4" (or another compatible version), and then click on the "FirstToekn.sol" button.


