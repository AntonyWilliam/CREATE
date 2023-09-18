# **CREATE and CREATE2 Address Prediction on RSK**

## **Table of Contents**
- [Introduction](#introduction)
- [Use Cases](#use-cases)
- [Flow Diagram](#flow-diagram)
- [Dependencies](#dependencies)
- [Setup & Installation](#setup--installation)
- [Expected Outputs](#expected-outputs)
- [Troubleshooting](#troubleshooting)
- [FAQs](#faqs)
- [Feedback and Contribution](#feedback-and-contribution)

## **Introduction**
This project showcases how to predict a smart contract address on RSK before its actual deployment using both standard methods and the CREATE2 scheme.

## **Use Cases**
- **Smart Contract Upgrades**: Predicting addresses can be useful when planning for smart contract upgrades, ensuring that data links remain consistent.
  
- **User Experience**: DApps can provide users with an address to monitor or interact with even before a contract is deployed.
  
- **Security**: In certain scenarios, knowing the address beforehand can be used to ensure that only a specific contract can occupy that address.

## **Flow Diagram**

![flowCREATE](https://github.com/AntonyWilliam/CREATE/assets/54343267/7bdc1c00-ca87-4b3c-a0e6-6bd497d3d23f "The current diagram is a flowchart that represents the steps involved in initializing the environment, configuring it, predicting and deploying an address, and checking for troubleshooting. Here is a text description of the flow:
Start")

## **Dependencies**
- **Node.js (v18)**: Essential for running the scripts and tests.
  
- **Hardhat**: Used for compiling, testing, and deploying smart contracts.
  
- **Ethers.js**: A library to interact with the Ethereum blockchain.

## **Setup & Installation**

1. **Configuration**:
   - Rename `.template.secret.json` from the repository root to `.secret.json`.
   - Update `.secret.json` with your account's seed phrase.

2. **Dependencies Installation**:
   ```bash
   npm install
   ```

3. **Running Tests**:
   ```bash
   npx hardhat test --network rsktestnet
   ```

## **Expected Outputs**

When you run the tests, you should see the following outputs:

```plaintext
  Calculate address
'ContractFactory' was deployed on rsktestnet with address 0xc3417e16e59a9b67AE577F1e8315EC91B1350204
    ✔ Should predict Child address (90881ms)
    ✔ Should deploy Child to the address starting with four zeros (83643ms)

    Picked up a salt '0x02b170d84f848d2b6ac490e51f96c9d225cd79a0a392e03981ad42260e17507f' such that the deployed s/c address is 0x00009DD0dE4f46153821dbF8c0ab3B18F99f0467
```

## **Troubleshooting**
- **Mismatched Address**: If the predicted address doesn't match the deployed one, ensure the bytecode, sender address, and nonce (or salt for CREATE2) are consistent with what was used for prediction.

- **Failed Deployment**: Ensure you have enough gas and that the RSK testnet is responsive. Check your internet connection.

- **Missing Dependencies**: If you encounter errors related to missing modules, run `npm install` again.

## **FAQs**
- **Q: What's the difference between CREATE and CREATE2?**
  - A: While both are used for contract creation, CREATE2 allows for more predictable address generation using a "salt" and init code.

- **Q: Can I use this method for mainnet deployments?**
  - A: Yes, but always ensure to test on testnets first and be aware of the gas costs.

- **Q: Is there a risk of someone else deploying to my predicted address before I do?**
  - A: With CREATE2 and a unique salt, this risk is minimized. However, always be cautious and monitor the address if it's critical.

## **Feedback and Contribution**
Your feedback is invaluable. If you find errors or have suggestions, please raise an issue or submit a pull request on GitHub.

For more assistance, reach out to our support team or visit the [Rootstock Developer Portal](https://dev.rootstock.io/).

Was this article helpful?
| ✅ Yes | ❌ No |
|---|---|
