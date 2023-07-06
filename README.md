# Eth-Intermediate
**Aim of the project**

Integrating a Smart Contract

**Project Description**

This project is an application to deploy and integrate a smart contract with the help of an ATM application by allowing users to connect with their MetaMask wallet.

**Features of the application**

1. It allows connecting the ATM application user interface with the MetaMask wallet.
   
2. User can display their account address and also view their account balance.
   
3. An individual can deposit and withdraw ETH to and from the ATM account.

**Code Functionality**

1. Open the project repository from GitHub and clone it with Gitpod.

2. From the left pan, open the pages folder and then the index.js file for working from the explorer.

3. Create three different terminals in the Gitpod inside the project directory.

4. In the first terminal, type: npm i. This will download all the dependencies for the project.

5. In the second terminal, type: npx hardhat node. This will create a local Ethereum node to work with on our system. It also provides various accounts that can be imported manually on our network in the meta mask wallet.

6. In order to deploy the smart contract, type: npx hardhat run --network localhost scripts/deploy.js.
   
7. In the third terminal, type:  npm run dev. This will start the contract successfully on localhost.

8. Click and open the provided localhost link to open the User interface.

9. Connect the MetaMask wallet and manually add a network by entering the required account details.

10. Import an account using the private keys provided in the Gitpod terminal.

11. Deposit and Withdraw ETH using the MetaMask wallet.

**User Interface(FRONTEND)**

(https://github.com/SK-4518/Eth-Intermediate/assets/136696857/2fc175b9-3db8-4c10-9b54-1008d5fa7da4)


**Code for the tutorial**

     // SPDX-License-Identifier: UNLICENSED
     
      pragma solidity ^0.8.9;

      //import "hardhat/console.sol";
      

    contract Assessment {

    //owner of the account and balanceAmount contained in the account 
    
    address payable public owner;
    uint256 public balanceAmount;

    event deposit_eth(uint256 amount);
    event withdraw_eth(uint256 amount);

    constructor(uint initBalance) payable {
        owner = payable(msg.sender);
        balanceAmmount = initBalance;
    }

    function getBalance() public view returns(uint256){
        return balanceAmount;
    }

    function depositAmount(uint256 _amount) public payable {
        uint _previousBalance = balanceAmount;

        // make sure this is the owner
        require(msg.sender == owner, "You are not the owner of this account");

        // perform transaction
        balanceAmount += _amount;

        // assert transaction completed successfully
        assert(balanceAmount == _previousBalance + _amount);

        // emit the event
        emit deposit_eth(_amount);
    }

    // custom error
    error InsufficientBalance(uint256 balanceAmount, uint256 withdrawAmount);

    function withdrawAmount(uint256 _withdrawAmount) public {
        require(msg.sender == owner, "You are not the owner of this account");
        uint _previousBalance = balanceAmount;
        if (balanceAmount < _withdrawAmount) {
            revert InsufficientBalance({
                balanceAmmount: balanceAmmount,
                withdrawAmount: _withdrawAmount
            });
        }

        // withdraw the given amount
        balanceAmount -= _withdrawAmount;

        // assert the balance is correct
        assert(balanceAmount == (_previousBalance - _withdrawAmount));

        // emit the event
        emit withdraw_eth(_withdrawAmount);
    }
        function ownerDetails() public pure returns(string memory(name,country,status)){
            string memory name="Sehaj_21BCS4518";
            string memory country="India";
            string memory status="Eligible candidate for the transaction";
            return (name,country,status);
        }
    }


**Code Logic**

1. Create a contract assessment.

2. Declare two variables to hold the address and balance amount of the account.

3. getBalance function return the balance of the account.

4. depositAmount function checks that the sender owns the account. If yes then it performs the transaction by adding the balance amount with the amount to be deposited. assert statement updates the balance of the account. Then we emit the event.

5. Create the custom error for insufficient balance.

6. withdrawAmount function checks that the sender owns the account. If balanceAmount < _withdrawAmount, the revert the message of insufficient balance. Else deduct withdraw the amount from the balanceAmount. assert statement updates the balance of the account. Then we emit the event.

7. The function ownerDetails returns the name, country, and status of the owner assuring the legal transaction.

**Video walkthrough**
https://www.loom.com/share/f707651b300b417dbca436b802ad1ab0?sid=c26e1e6c-b302-4c75-a4a8-411b9ed53c64

**Author**

Sehajpreet Kaur (21BCS4518@cuchd.in)
   
