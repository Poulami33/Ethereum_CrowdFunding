# 🪙 CrowdCoin — A Web3 Platform for Decentralized Crowdfunding

CrowdCoin is a blockchain-based Web3 platform designed to revolutionize the crowdfunding ecosystem by eliminating intermediaries and empowering creators and contributors through smart contracts, transparency, and decentralization.

## 🚀 Project Overview

Traditional crowdfunding platforms suffer from high fees, lack of transparency, and centralization. CrowdCoin addresses these limitations by leveraging the **Ethereum blockchain**, **smart contracts**, and **MetaMask wallet integration** to build a decentralized crowdfunding platform.

Users can:
- Create fundraising campaigns.
- Contribute securely using crypto wallets.
- Track contributions transparently on the blockchain.

## 🎯 Objectives

- Minimize transaction fees by eliminating middlemen.
- Ensure secure and immutable donation records using Ethereum.
- Empower users with real-time insights into campaign progress.
- Automate fund distribution through self-executing smart contracts.
- Create a scalable, transparent, and user-friendly crowdfunding platform.

## 🛠️ Tech Stack

| Layer           | Technology Used                         |
|----------------|------------------------------------------|
| Blockchain      | Ethereum (Sepolia Testnet)              |
| Smart Contracts | Solidity                                |
| Wallet          | MetaMask                                |
| Frontend        | React.js, HTML, CSS, Tailwind CSS       |
| Blockchain Bridge | Web3.js                                |
| Dev Tools       | Hardhat, Etherscan                      |

## 🧩 Features

- **Campaign Creation:** Set title, description, target amount, deadline, and image.
- **Smart Contracts:** All campaign logic and donation handling executed on-chain.
- **Investor Dashboard:** Personalized dashboard to track contributions and updates.
- **Tokenization (optional):** Projects can issue tokens representing ownership or rewards.
- **Decentralized Access:** No central authority—full user control and trust.

## 📦 Modules Used

- `web3.js`: Connect frontend to Ethereum.
- `Solidity`: Build and deploy smart contracts.
- `MetaMask`: User wallet and transaction signing.
- `Hardhat`: Local blockchain development and testing.
- `Tailwind CSS`: UI styling and responsiveness.

## 🔐 Security Considerations

- All transactions recorded on an immutable public ledger.
- Smart contract logic ensures only campaign owners receive funds.
- Feature selection and behavioral analysis techniques aim to detect fraud.
- Compliance with data privacy standards (e.g., GDPR).

## ⚙️ Sample Smart Contract Snippet

```solidity
function donateToCampaign(uint256 _id) public payable {
    uint256 amount = msg.value;
    Campaign storage campaign = campaigns[_id];

    campaign.donators.push(msg.sender);
    campaign.donations.push(amount);

    (bool sent,) = payable(campaign.owner).call{value: amount}("");
    if(sent) {
        campaign.amountCollected += amount;
    }
}
