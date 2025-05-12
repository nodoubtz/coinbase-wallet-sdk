# Coinbase Wallet SDK

![npm](https://img.shields.io/npm/v/@coinbase/wallet-sdk)

The **Coinbase Wallet SDK** enables developers to seamlessly connect their decentralized applications (dApps) to Coinbase Wallet. This SDK supports multiple platforms and provides a rich set of features for integrating Coinbase Wallet functionality.

---

## Features

- **Wallet Connectivity**: Easily connect dApps to Coinbase Wallet via mobile, desktop extensions, or Coinbase Smart Wallet.
- **Cross-Platform Support**:
  - Mobile: [Android](https://play.google.com/store/apps/details?id=org.toshi) | [iOS](https://apps.apple.com/app/apple-store/id1278383455?pt=118)
  - Desktop: Quick integration with code scanning or extension-based connectivity.
  - Coinbase Smart Wallet: [Docs](https://www.smartwallet.dev/)
- **Event Handling**: Listen for wallet events like account changes, chain changes, and disconnects.
- **Custom Configuration**: Easily configure wallet settings to meet your dApp’s requirements.

---

## Getting Started

### Prerequisites

Before using the SDK, ensure the following dependencies are installed globally:

- [Node.js 20.11+](https://nodejs.org/en/download/releases)
- [Yarn v3](https://yarnpkg.com/getting-started/install)

---

### Installation

Install the latest version of the SDK via `npm` or `yarn`:

```bash
# Using Yarn
yarn add @coinbase/wallet-sdk

# Using NPM
npm install @coinbase/wallet-sdk
```

To check available versions:

```bash
yarn info @coinbase/wallet-sdk versions
npm view @coinbase/wallet-sdk versions
```

---

### Upgrading

To ensure you're using the latest version of the SDK, follow these steps:

```bash
# Using Yarn
yarn outdated @coinbase/wallet-sdk
yarn upgrade @coinbase/wallet-sdk --latest

# Using NPM
npm outdated @coinbase/wallet-sdk
npm update @coinbase/wallet-sdk
```

---

## Basic Usage

### Initialize the SDK

```javascript
const sdk = new CoinbaseWalletSDK({
  appName: 'SDK Playground',
});
```

### Create a Web3 Provider

```javascript
const provider = sdk.makeWeb3Provider();
```

### Request Accounts

```javascript
const addresses = await provider.request({
  method: 'eth_requestAccounts',
});
```

### Handle Events

```javascript
provider.on('accountsChanged', (accounts) => {
  console.log('Accounts changed:', accounts);
});

provider.on('chainChanged', (chainId) => {
  console.log('Chain changed:', chainId);
});

provider.on('disconnect', () => {
  console.log('Wallet disconnected');
});
```

---

## Development

### Running Locally

To run the SDK and test dApp locally:

1. Clone the repository:
   ```bash
   git clone https://github.com/nodoubtz/coinbase-wallet-sdk.git
   ```
2. Install dependencies:
   ```bash
   yarn install
   ```
3. Start the development server:
   ```bash
   yarn dev
   ```

You can view the test dApp [here](https://coinbase.github.io/coinbase-wallet-sdk/).

---

## Linting and Formatting

The project uses [Biome](https://github.com/biomejs/biome) for linting and formatting. Configure your editor using the [Biome docs](https://biomejs.dev/guides/editors/first-party-extensions/).

---

## Contributing

We welcome contributions! Please follow these guidelines:

- **Bug Reports**: Search existing [issues](https://github.com/coinbase/coinbase-wallet-sdk/issues) before creating a new one.
- **Enhancements**: Suggest features by opening a [new issue](https://github.com/coinbase/coinbase-wallet-sdk/issues/new).
- **Pull Requests**:
  - Fork the repository and create a branch from `master`.
  - Follow the [Conventional Commits](https://www.conventionalcommits.org/) specification for commit messages.
  - Include screenshots for visual changes.

For more details, see [CONTRIBUTING.md](CONTRIBUTING.md).

---

## License

The Coinbase Wallet SDK is licensed under the [BSD 3-Clause License](./LICENSE).
