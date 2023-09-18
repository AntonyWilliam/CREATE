# **CREATE and CREATE2 Address Prediction on RSK**

This project showcases how to predict a smart contract address on RSK before its actual deployment using both standard methods and the CREATE2 scheme.

## **Overview**

- **Test 1**: Demonstrates the standard method of address calculation.
- **Test 2**: Utilizes the CREATE2 method. Specifically, it selects a salt such that the resulting contract address starts with 4 leading zeros.

## **Prerequisites**

Ensure you have Node v18 installed. If not, you can manage different versions of Node using [NVM](https://github.com/nvm-sh/nvm).

```bash
nvm install 18
nvm use 18
```

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

---

**Note**: Always ensure that your seed phrase is kept secure and never exposed or committed to public repositories.

