# Defi Application(My Atm)

## Description

This Solidity program, named "My ATM," implements a simple ATM (Automated Teller Machine) functionality on the Ethereum blockchain. It allows users to deposit, withdraw, and transfer Ethereum (ETH) funds. The contract also provides functions to check the account balance. This program serves as a basic example of a decentralized finance (DeFi) application and can be used as a learning resource for understanding Solidity smart contract development.

## Getting Started

### Executing program
To interact with the My ATM contract, you need to follow these steps:

Install MetaMask or any other Ethereum wallet extension in your browser.

Access a web3-enabled browser such as Google Chrome or Mozilla Firefox.

Visit a web application or website that integrates the My ATM contract.

Connect your MetaMask wallet to the application by clicking on the connect button.

Once connected, you can deposit, withdraw, and transfer ETH using the provided interface.
```solidity
  //Tranfer Function
  function transfer(address _receiver, uint256 _amount) public
   {
        require(_receiver != address(0), "Invalid receiver address");
        require(_receiver != owner, "Cannot transfer to owner");

        uint256 _previousBalance = balance;
        require(balance >= _amount, "Insufficient balance");

        balance -= _amount;
        payable(_receiver).transfer(_amount);

        emit Transfer(msg.sender, _receiver, _amount);
    }

```
To compile the project:
After cloning the github, you will want to do the following to get the code running on your computer.

1.Inside the project directory, in the terminal type: npm i

2.Open two additional terminals in your VS code

3.In the second terminal type: npx hardhat node

4.In the third terminal, type: npx hardhat run --network localhost scripts/deploy.js

5.Back in the first terminal, type npm run dev to launch the front-end.

After this, the project will be running on your localhost. Typically at http://localhost:3000/

![image](https://github.com/Mehak051003/AVX-assessment-2/assets/118992603/53ba0a23-265b-4a15-9535-1aae6288e83d)

![image](https://github.com/Mehak051003/AVX-assessment-2/assets/118992603/bb3de14c-e3cf-4718-b885-c51523fc466d)


## Authors

Mehak Thakur
[mehakthakur051003@gmail.com]


## License

This project is licensed under the MIT License - see the LICENSE.md file for details
