# Dummy Token

A simple dummy token. Based on the [HardHat Tutorial](https://hardhat.org/tutorial/).

## Prerequisites

- **Node.js**: Version 18.20.8 was used during development and is recommended. Newer Node versions should work as well.

## Setup

### Quick Setup (Recommended)

If you're using Node.js 18.20.8, you can use the following streamlined process:

1. Run `npm ci` to install dependencies (or `npm install` for other Node versions)
2. Run `npx hardhat test` to test the code
3. Start the local development ethereum node: `npm run hardhat:up` (in one terminal)
4. Deploy and fund your account: `WALLET_ADDRESS=<your-address> npm run hardhat:deploy` (in a different terminal), where `<your-address>` is your Ethereum address (i.e., your MetaMask account)
5. If everything went well, the contract address should be `0x5FbDB2315678afecb367f032d93F642f64180aa3`

### Legacy Setup Instructions

1. Run `npm install` to install dependencies
2. Run `npx hardhat test` to test the code
3. Start a local development ethereum node on a new terminal using `npx hardhat node --hostname 0.0.0.0`
4. Run `npx hardhat --network localhost run scripts/deploy.js` to deploy the Dummy Token contract, keep note of the `Token Address` that will output in the terminal.
5. Run `npx hardhat --network localhost faucet <token-address> <your-address>`, where `<token-address>` is the address of the Dummy Token contract deployed in the previous step, and `<your-address>` is your Ethereum address (i.e., your MetaMask account). This will fund your Ethereum account with ETH and mint DUMMY tokens.

## Wallet Setup

After completing either setup process above, you'll need to configure your MetaMask wallet:

1. Connect your MetaMask extension to the `localhost` network. You should have 1 ETH in your balance.
2. Add the Dummy Token to MetaMask:
   - Click on `Add Token`
   - Click on `Custom Token`
   - Paste on `Token Contract Address` the Dummy Token contract address (from the deployment step)
   - You should see `100 DUMMY` tokens in your wallet

## Adding a Development Network to MetaMask

To add a development network to MetaMask, follow the instructions in the [MetaMask documentation](https://docs.metamask.io/wallet/how-to/run-devnet/).

1. Open MetaMask and click on the network dropdown at the top.
2. Select "Add Network".
3. Fill in the network details:
   - Network Name: Localhost
   - New RPC URL: <http://0.0.0.0:8545>
   - Chain ID: 1337
   - Currency Symbol: ETH
4. Click "Save"
