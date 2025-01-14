# Foundry Fund Me Contract

This repository contains a simple `FundMe` smart contract built using [Foundry](https://getfoundry.sh/), a blazing fast, portable, and modular toolkit for Ethereum application development.

## Overview
The `FundMe` contract allows users to contribute funds and provides a mechanism for the owner to withdraw the collected funds. This project is designed to demonstrate the following key concepts:

- Writing and deploying Solidity contracts.
- Handling Ether transactions within smart contracts.
- Implementing access control mechanisms for secure fund withdrawals.

## Features
- **Fund**: Anyone can send Ether to the contract.
- **Withdraw**: Only the contract owner can withdraw the collected funds.
- **Balance Query**: Anyone can query the contract's balance.
- **Contributor Query**: View the total contributions made by a specific address.

## Prerequisites
- [Foundry](https://getfoundry.sh/) installed on your system.
- Node.js (for additional tooling, if needed).
- A supported Ethereum wallet for testing (e.g., MetaMask).

## Setup

1. **Clone the Repository**
   ```bash
   git clone <repository-url>
   cd <repository-folder>
   ```

2. **Install Dependencies**
   Install any required libraries (e.g., OpenZeppelin contracts):
   ```bash
   forge install OpenZeppelin/openzeppelin-contracts
   ```

3. **Compile the Contracts**
   ```bash
   forge build
   ```

4. **Run Tests**
   ```bash
   forge test
   ```

## Contract Details

### Functions

1. **`fund()`**
   - Allows users to send Ether to the contract.
   - Validates a minimum contribution amount.

2. **`withdraw()`**
   - Allows the owner to withdraw all collected funds.
   - Implements a secure access control mechanism.

3. **`getBalance()`**
   - Returns the current Ether balance of the contract.

4. **`getContribution(address contributor)`**
   - Returns the total contributions made by the specified address.

### Variables
- **`owner`**: The address of the contract owner.
- **`contributions`**: Mapping of contributor addresses to their contribution amounts.

## Deployment
1. **Set Up Environment**
   - Create a `.env` file to store private keys and RPC URLs securely.

2. **Deploy the Contract**
   Use the `forge` command to deploy the contract to your desired network:
   ```bash
   forge script script/FundMe.s.sol --rpc-url <RPC_URL> --private-key <PRIVATE_KEY> --broadcast
   ```

## Testing
The repository includes unit tests to validate the contract functionality. Run the tests using:
```bash
forge test
```

## Security Considerations
- Ensure to keep your private key secure when deploying the contract.
- The contract is for educational purposes; audit thoroughly before using in production.

## Contributing
Feel free to fork this repository and submit pull requests with improvements or new features. Open an issue if you encounter bugs or have suggestions.

## License
This project is licensed under the MIT License. See the `LICENSE` file for details.
