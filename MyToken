// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

// Contract Code
contract MyToken {
    string public tokenName;
    string public tokenAbbreviation;
    uint256 public totalSupply;

    // Mapping to track balance of addresses
    mapping(address => uint256) public balance;

    // Constructor to initialize the token with a token name, token abbreviation, and total supply
    constructor(string memory _tokenName, string memory _tokenAbbreviation, uint256 _totalSupply) {
        tokenName = _tokenName;
        tokenAbbreviation = _tokenAbbreviation;
        totalSupply = _totalSupply;
        balance[msg.sender] = _totalSupply;
    }

    // Minting function to increase total supply and add tokens to a specific address
    function mint(address _receiver, uint256 _value) public {
        require(_value > 0, "Value must be greater than 0");
        totalSupply += _value;
        balance[_receiver] += _value;
    }

    // Burning function to decrease total supply and remove tokens from a specific address
    function burn(address _sender, uint256 _value) public {
        require(_value > 0, "Value must be greater than 0");
        require(balance[_sender] >= _value, "Insufficient balance");
        totalSupply -= _value;
        balance[_sender] -= _value;
    }
}
