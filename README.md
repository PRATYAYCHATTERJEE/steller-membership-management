# Nero Membership Management

A secure, decentralized membership platform built on **Nero Chain** EVM smart contracts. This application allows you to register members, manage membership tiers, renew subscriptions, and handle member suspensions all on-chain.

## Features

✨ **Key Capabilities:**

- **Member Registration** - Register new members with name, email, membership tier, and join date
- **Tier Management** - Upgrade members to higher tiers (Basic → Silver → Gold → Platinum)
- **Subscription Renewal** - Extend membership expiration dates with automatic tracking
- **Member Controls** - Suspend and reactivate member accounts (Admin only)
- **Query Functions** - Look up individual members or view the complete member directory
- **Wallet Integration** - Seamless MetaMask/EVM wallet connection

## Technology Stack

- **Blockchain**: Nero Chain (EVM Compatible)
- **Smart Contracts**: Solidity ^0.8.24
- **Frontend**: React 19 + Vite
- **Wallet**: MetaMask / EVM Wallets
- **Provider**: Ethers.js v6
- **Development**: Hardhat

## Getting Started

### Prerequisites

- Node.js 18+ and npm
- MetaMask browser extension
- NERO testnet tokens

### Installation & Setup

1. **Clone the repository:**
```bash
git clone <repository-url>
cd steller-membership-management
```

2. **Install dependencies:**
```bash
npm install
```

3. **Configure Environment:**
Create a `.env` file from the template:
```bash
cp .env.example .env
```
Add your private key to `.env`.

4. **Deploy Smart Contract:**
```bash
npx hardhat run scripts/deploy.js --network neroTestnet
```

5. **Update Frontend:**
Update `src/lib/nero.js` with your deployed contract address:
```javascript
export const CONTRACT_ADDRESS = "YOUR_CONTRACT_ADDRESS_HERE";
```

6. **Start Development Server:**
```bash
npm run dev
```

## Smart Contract

The Solidity contract (`contracts/MembershipManagement.sol`) implements:

- **Member Struct**: Stores member details, tier, status, and dates
- **Membership Tiers**: Basic, Silver, Gold, Platinum
- **Access Control**: Admin restricted functions for suspension and activation

## Project Structure

```
steller-membership-management/
├── contracts/             # Solidity smart contracts
├── src/
│   ├── App.jsx            # Main React component
│   ├── App.css            # Application styling
│   └── lib/
│       └── nero.js        # Nero Chain integration (Ethers.js)
├── hardhat.config.cjs     # Hardhat configuration
├── package.json
└── README.md
```

## Environment Variables

| Variable | Description |
| --- | --- |
| `PRIVATE_KEY` | Your EVM wallet private key for deployment |

## Security Considerations

⚠️ **Important:**
- Never share your private keys or commit `.env` files.
- Test thoroughly on Nero Testnet before mainnet deployment.
- Admin functions are restricted to the contract deployer address.

---

**Built for the Nero Chain Track**
