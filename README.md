// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract ErrorHandling {

    // Function using require to check conditions
    function checkRequire(uint256 _value) public pure returns (string memory) {
        require(_value > 0, "Value must be greater than zero");
        return "Value is valid";
    }

    // Function using assert to enforce invariants
    function checkAssert(uint256 _value) public pure returns (string memory) {
        uint256 result = _value * 2;
        // Assert is used to check for internal errors and invariants
        assert(result >= _value);
        return "Assert passed";
    }

    // Function using revert to handle errors
    function checkRevert(uint256 _value) public pure returns (string memory) {
        if (_value == 0) {
            revert("Value cannot be zero");
        }
        return "Value is non-zero";
    }
}
