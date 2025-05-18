[![CodeQL Advanced](https://github.com/nodoubtz/coinbase-wallet-sdk/actions/workflows/2codeql.yml/badge.svg)](https://github.com/nodoubtz/coinbase-wallet-sdk/actions/workflows/2codeql.yml)

# Coinbase Wallet SDK

[![License](https://img.shields.io/github/license/nodoubtz/coinbase-wallet-sdk)](LICENSE)
[![Issues](https://img.shields.io/github/issues/nodoubtz/coinbase-wallet-sdk)](https://github.com/nodoubtz/coinbase-wallet-sdk/issues)
[![Pull Requests](https://img.shields.io/github/issues-pr/nodoubtz/coinbase-wallet-sdk)](https://github.com/nodoubtz/coinbase-wallet-sdk/pulls)

A developer SDK for integrating with Coinbase Wallet, enabling seamless blockchain interactions in your application.

---

## Table of Contents

- [Features](#features)
- [Installation](#installation)
- [Quick Start](#quick-start)
- [Usage](#usage)
- [API Reference](#api-reference)
- [Configuration](#configuration)
- [Security](#security)
- [Contributing](#contributing)
- [License](#license)
- [Support](#support)

---

## Features

- 🔗 Connect your app to Coinbase Wallet
- 💸 Send and receive crypto assets
- 🔒 Secure transaction signing
- 📡 Real-time blockchain event listening
- 🚀 Easy integration with popular frameworks

---

## Installation

Install via npm:

```bash
npm install coinbase-wallet-sdk
```

Or with yarn:

```bash
yarn add coinbase-wallet-sdk
```

---

## Quick Start

```javascript
import CoinbaseWalletSDK from 'coinbase-wallet-sdk';

const wallet = new CoinbaseWalletSDK({
  appName: "My DApp",
  appLogoUrl: "https://myapp.com/logo.png",
  darkMode: false
});

// Connect to wallet
const provider = wallet.makeWeb3Provider("https://mainnet.infura.io/v3/<INFURA_KEY>", 1);

// Enable provider (request accounts)
provider.enable().then(accounts => {
  console.log("Connected accounts:", accounts);
});
```

---

## Usage

- **Connect Wallet:** Prompt users to connect their Coinbase Wallet.
- **Sign Transactions:** Request users to sign and send transactions securely.
- **Listen to Events:** Subscribe to blockchain events and wallet changes.

### Example: Sending a Transaction

```javascript
provider.send('eth_sendTransaction', [{
  from: accounts[0],
  to: "0xRecipientAddress",
  value: "0x2386F26FC10000", // 0.01 ETH
}]);
```

---

## API Reference

For the full list of available methods and options, see the [API documentation](./docs/API.md).

---

## Configuration

| Option      | Type    | Description                           |
| ----------- | ------- | ------------------------------------- |
| appName     | String  | Name of your application              |
| appLogoUrl  | String  | URL of your app logo                  |
| darkMode    | Boolean | Enable dark mode for UI (default: false) |

---

## Security

- Always keep your dependencies up to date.
- Never expose sensitive credentials in the frontend.
- Review the [SECURITY.md](./SECURITY.md) for guidelines.

---

## Contributing

Contributions are welcome! Please read the [CONTRIBUTING.md](./CONTRIBUTING.md) for guidelines.

---

## License

This project is licensed under the [MIT License](./LICENSE).

---

## Support

- [Open an issue](https://github.com/nodoubtz/coinbase-wallet-sdk/issues)
- [Pull requests](https://github.com/nodoubtz/coinbase-wallet-sdk/pulls)
- Email: [maintainer@example.com](mailto:maintainer@example.com)

---

> _Powered by Coinbase Wallet SDK. Not affiliated with Coinbase, Inc._
