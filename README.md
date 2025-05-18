# Coinbase Wallet SDK

A developer SDK for integrating Coinbase Wallet functionality into your web or mobile applications. This SDK allows users to connect, authenticate, and interact with Coinbase Wallet seamlessly.

## Features

- **Easy Integration**: Simple setup for web and mobile apps.
- **Secure Authentication**: Connect and authenticate users via Coinbase Wallet.
- **Transaction Management**: Send, receive, and sign transactions securely.
- **Account Management**: Access wallet balance, history, and account details.
- **Customizable UI**: Adapt wallet connection prompts to your brand.

## Installation

### npm

```bash
npm install coinbase-wallet-sdk
```

### yarn

```bash
yarn add coinbase-wallet-sdk
```

## Usage

### Import and Initialize

```javascript
import CoinbaseWalletSDK from 'coinbase-wallet-sdk';

const coinbaseWallet = new CoinbaseWalletSDK({
  appName: "Your App Name",
  appLogoUrl: "https://yourdomain.com/logo.png",
  darkMode: false
});
```

### Connect Wallet

```javascript
const ethereum = coinbaseWallet.makeWeb3Provider(
  "https://mainnet.infura.io/v3/YOUR_INFURA_PROJECT_ID",
  1
);

// Request accounts
const accounts = await ethereum.request({ method: 'eth_requestAccounts' });
console.log(accounts);
```

### Send Transaction

```javascript
const tx = await ethereum.request({
  method: 'eth_sendTransaction',
  params: [
    {
      from: accounts[0],
      to: '0xRecipientAddress',
      value: '0xValueInWei',
      gas: '0x5208'
    }
  ]
});
```

## Security

- Do not expose sensitive keys in client-side code.
- Always verify user actions before signing transactions.
- Follow best practices for wallet security and data privacy.

## Contributing

1. Fork the repository.
2. Create a new branch: `git checkout -b feature/your-feature`.
3. Commit your changes: `git commit -m 'Add your message'`.
4. Push to the branch: `git push origin feature/your-feature`.
5. Open a pull request.

## Issues

If you encounter any bugs or have feature requests, please use the [Issues](https://github.com/nodoubtz/coinbase-wallet-sdk/issues) section.

## License

This project is licensed under the MIT License.

---

**Note:** This SDK is not affiliated with or endorsed by Coinbase, Inc. Use at your own risk.
