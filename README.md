# Error-handling
This Solidity program is a simple program writtened to test all the error handling funtions in solidity to make sure that the code is running fluently without any errors.

Description
This program is a simple contract written in Solidity, a programming language used for developing smart contracts similarly in this program we created smart contract named Air conditionor to turn on ac when temperature rises above 20 degrees celcius while making sure to handle any kind of errors.
Getting Started
Executing program
To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/. 

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., HelloWorld.sol). Copy and paste the following code into the file:

// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract AirConditionor{
    bool public On;
    int public currentTemperature;
    constructor(int initialTemperature) {
        require(initialTemperature >= -50 && initialTemperature <= 50, "Invalid temperature range");
        currentTemperature = initialTemperature;
        On = initialTemperature > 20;
    }
    function updateTemperature(int newTemperature) public {
        if (newTemperature < -50 || newTemperature > 50) {
            revert("Invalid temperature range");
        }
        currentTemperature = newTemperature;
        On = currentTemperature > 20;
        assert(On == (currentTemperature > 20));
    }
    function getACStatus() public view returns (bool) {
        return On;
    }
}
To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.4" (or another compatible version), and then click on the "Compile HelloWorld.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "AirConditionor" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by calling the elligible and license requirement function. 

License
This project is licensed under the MIT License - see the LICENSE.md file for details
