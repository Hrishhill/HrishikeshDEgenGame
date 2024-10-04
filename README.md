
# Degen Token & Game NFT Website

This project is a decentralized application (DApp) built using React.js, integrating two smart contracts: `DegenTokenContract` (an ERC20 token) and `GameNFT` (an ERC721 NFT contract). The contracts are deployed on the Avalanche Fuji Testnet, allowing users to interact with Degen tokens and Game NFTs directly from the website.

## Features

### DegenTokenContract (ERC20 Token)

- **Mint Tokens:** The owner can mint a specified number of `DGN` tokens upon contract creation.
- **Buy Tokens:** Users can purchase Degen tokens by sending Ether (in this case, Avalanche's AVAX). The price per token is defined at the time of contract deployment.
- **Transfer Tokens:** Users can transfer their `DGN` tokens to other addresses.
- **Burn Tokens:** Users can burn their `DGN` tokens, reducing the total supply.
- **Redeem Tokens for NFTs:** Users can redeem their `DGN` tokens to mint NFTs from the `GameNFT` contract.
- **Withdraw Ether:** The contract owner can withdraw AVAX accumulated from token purchases.

### GameNFT (ERC721 NFT)

- **Mint NFTs:** Users can mint unique Game NFTs with custom metadata (represented as a URI). The minting is done via the `DegenTokenContract` when users redeem their `DGN` tokens.
- **Add Mintable NFT URIs:** Admins can add new NFTs to a mintable list, which users can later redeem and mint.
- **View Minted NFTs:** Users can view the NFTs they have minted through the contract.

## Tech Stack

- **Frontend:** React.js
- **Blockchain:** Solidity, Remix IDE (for deployment)
- **Wallet Integration:** MetaMask
- **Blockchain Network:** Avalanche Fuji Testnet

## Prerequisites

Before starting, ensure you have the following installed:

- [Node.js](https://nodejs.org/)
- [MetaMask](https://metamask.io/) browser extension
- Access to Avalanche Fuji Testnet

## Smart Contracts

Two smart contracts are deployed and integrated into this project:

1. **DegenTokenContract** (ERC20)
   - Symbol: `DGN`
   - Deployed using Remix IDE on the Avalanche Fuji Testnet.

2. **GameNFT** (ERC721)
   - Symbol: `MPE` (MedicalProcedure)

### Deploying Smart Contracts Using Remix IDE

1. Open [Remix IDE](https://remix.ethereum.org/).
2. Paste the `DegenTokenContract` and `GameNFT` contract code in separate `.sol` files.
3. Compile both contracts using Solidity compiler version `^0.8.0`.
4. Connect Remix IDE to the Avalanche Fuji Testnet via MetaMask (see the MetaMask setup below).
5. Deploy the contracts using the injected web3 environment (MetaMask).
6. Copy the deployed contract addresses for use in the React application.

## Installation

To set up the project locally:

1. Clone the repository:

   ```bash
   git clone https://github.com/your-repo-url.git
   ```

2. Navigate to the project folder:

   ```bash
   cd degen-token-game-nft
   ```

3. Install the required dependencies:

   ```bash
   npm install
   ```

## Configuration

1. In the `src` folder, create a `.env` file with the following environment variables:

   ```bash
   REACT_APP_DEGEN_TOKEN_ADDRESS=<DegenTokenContract_Address>
   REACT_APP_GAME_NFT_ADDRESS=<GameNFTContract_Address>
   ```

2. Replace `<DegenTokenContract_Address>` and `<GameNFTContract_Address>` with the actual contract addresses deployed using Remix on the Avalanche Fuji Testnet.

## Running the App

To start the React development server:

```bash
npm start
```

The app will run on `http://localhost:3000`. Open this in your browser to interact with the smart contracts via MetaMask.

## MetaMask Setup for Avalanche Fuji Testnet

To interact with the Avalanche Fuji Testnet through MetaMask, follow these steps:

1. Open MetaMask in your browser.
2. Click on the network dropdown at the top and select "Add Network."
3. Add the following network details:

   - **Network Name:** Avalanche Fuji C-Chain
   - **New RPC URL:** `https://api.avax-test.network/ext/bc/C/rpc`
   - **Chain ID:** `43113`
   - **Currency Symbol:** `AVAX`
   - **Block Explorer URL:** `https://testnet.snowtrace.io/`

4. Click "Save."

5. Now, your MetaMask is connected to the Avalanche Fuji Testnet. You can send AVAX, interact with the smart contracts, and test your DApp on this network.

## Usage

### Buy Degen Tokens

1. Connect MetaMask to the application and ensure you're on the Avalanche Fuji Testnet.
2. Enter the amount of `DGN` tokens you want to buy.
3. Click "Buy Tokens" and confirm the transaction in MetaMask using AVAX.

### Mint NFTs

1. Once you have `DGN` tokens, navigate to the "Mint NFT" section.
2. Enter the NFT URI from the available mintable NFTs.
3. Confirm the redemption and minting process.

### View Minted NFTs

1. Users can view the NFTs they have minted in the "My NFTs" section.

### Add New Mintable NFT URIs

1. Admin users can add new NFT URIs to the list of available mintable NFTs through the "Admin" section.

## License

This project is licensed under the MIT License.

## Acknowledgments

- [OpenZeppelin](https://openzeppelin.com/contracts/) for providing secure smart contract libraries.
- [Remix IDE](https://remix.ethereum.org/) for smart contract development and deployment.
- [Avalanche](https://www.avax.network/) for providing a scalable blockchain network.
