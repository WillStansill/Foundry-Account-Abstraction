# Account Abstraction

This project demonstrates **Account Abstraction (AA)** with **Ethereum** and **zkSync** using a minimal **Smart Wallet** deployment, showcasing contract deployments on **Arbitrum**, **zkSync** (Sepolia), and local zkSync networks.

## 🚀 Features

-   **Account Abstraction**: Transitioning from externally owned accounts (EOAs) to smart contract accounts.
-   **Smart Wallet**: Minimal wallet using **Account Abstraction** and **alt-mempool** for Ethereum and **native AA** for zkSync.
-   **Deployment**: Deploy on **Arbitrum**, **zkSync local network**, **zkSync Sepolia**, and **zkSync Mainnet**.
-   **User Operations**: Sending and managing transactions via **zkSync** and **Arbitrum** networks.

## 🛠 Tech Stack

-   **Smart Contracts**: Solidity
-   **Deployment**: Foundry, zkSync, Arbitrum
-   **Blockchain**: Ethereum, zkSync, Arbitrum

## 🚀 Quickstart

### 1.  **Clone the repository**:

    ```bash
    git clone [https://github.com/yourusername/minimal-account-abstraction](https://github.com/yourusername/minimal-account-abstraction)
    cd minimal-account-abstraction
    ```

### 2.  **Install dependencies**:

    ```bash
    make
    ```

### 3.  **Deploy on Arbitrum**:

    ```bash
    make deployEth
    ```

### 4.  **Send User Operation on Arbitrum**:

    ```bash
    make sendUserOp
    ```

### 5.  **Deploy on zkSync local network**:

    ```bash
    make zkbuild
    make zktest
    ```

### 6.  **Deploy on zkSync Sepolia or Mainnet**:

    1.  **Set up .env and encrypt your private key**:

        ```bash
        make encryptKey
        ```

    2.  **Deploy the contract**:

        ```bash
        make zkdeploy
        ```

### 7.  **Send AA Transaction**:

    ```bash
    make sendTx
    ```

## 🌐 Example Deployments

-   **zkSync (Sepolia):**

    -   zkMinimal Account
    -   USDC Approval via native zkSync AA

-   **Ethereum (Arbitrum):**

    -   Minimal Account
    -   USDC Approval via EntryPoint

## 💡 Account Abstraction Flow

-   **First-time deployment**:

    -   Calls `createAccount` or `create2Account` on the `CONTRACT_DEPLOYER` system contract to deploy on L1.

-   **Subsequent deployments**:

    -   Checks if the contract hash is already deployed and associated.

## 📝 FAQ

-   **What happens if I don't add the contract hash to factory deps?**

    -   The transaction will revert. The `ContractDeployer` checks if the hash exists before deploying.

-   **Why can't we use Foundry or Cast for deployments?**

    -   Foundry and Cast don't support the required `factoryDeps` transaction field or type 113 transactions.

-   **Can I use `forge create --legacy` to deploy a regular contract?**

    -   Yes, `foundry-zksync` supports legacy deployments but not EIP-1559 or account creation yet.

## 🔐 Security Disclaimer

This project is for educational purposes only. It has not undergone a security audit and should not be used in production environments.

## 📬 Contact

📧 Email: willstansill@gmail.com

💼 LinkedIn: linkedin.com/in/will-stansill

🐙 GitHub: github.com/yourusername

Explore Account Abstraction and deploy smart contract wallets with zkSync and Arbitrum 🚀
