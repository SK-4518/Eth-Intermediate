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

4. In the first terminal, type: npm i . This will download all the dependencies for the project.

5. In the second terminal, type: npx hardhat node. This will create a local Ethereum node to work with on our system. It also provides various accounts which can later be imported manually on our network in the meta mask wallet.

6. In order to deploy the smart contract, type: npx hardhat run --network localhost scripts/deploy.js.
   
7. In the third terminal, type:  npm run dev. This will start the contract successfully on localhost.

8. Click and open the provided localhost link to open the User interface.

9. Connect the MetaMask wallet and add a network manually by entering the required details of the account.

10. Import an account using the private keys provided in the Gitpod terminal.

11. Deposit and Withdraw ETH using the MetaMask wallet.  

   
