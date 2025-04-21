# Coinbase Wallet SDK

[![npm](https://img.shields.io/npm/v/@coinbase/wallet-sdk.svg)](https://www.npmjs.com/package/@coinbase/wallet-sdk)

## Introduction

Coinbase Wallet SDK enables developers to integrate their dapps with Coinbase Wallet across multiple platforms. Users can connect via desktop, mobile, or browser extensions, unlocking seamless interaction with decentralized applications.

## Features

- **Coinbase Smart Wallet**: Offers a secure and efficient wallet solution.
  - [Docs](https://www.smartwallet.dev/)
- **Mobile Support**: Connect to dapps via QR codes or deeplinks on Android and iOS.
- **Browser Extensions**: Integration with Chrome and Brave browsers for desktop users.

## Installation

Install the SDK using your preferred package manager:

### Check Available Versions

```shell
# yarn
yarn info @coinbase/wallet-sdk versions

# npm
npm view @coinbase/wallet-sdk versions
```

### Install the Latest Version

```shell
# yarn
yarn add @coinbase/wallet-sdk

# npm
npm install @coinbase/wallet-sdk
```

### Verify Installed Version

```shell
# yarn
yarn list @coinbase/wallet-sdk

# npm
npm list @coinbase/wallet-sdk
```

## Upgrading

To upgrade the SDK, compare the installed version with the latest available:

```shell
# yarn
yarn outdated @coinbase/wallet-sdk

# npm
npm outdated @coinbase/wallet-sdk
```

Update to the latest version:

```shell
# yarn
yarn upgrade @coinbase/wallet-sdk --latest

# npm
npm update @coinbase/wallet-sdk
```

## Basic Usage

1. Initialize the SDK:

    ```javascript
    const sdk = new CoinbaseWalletSDK({
        appName: 'Your App Name',
    });
    ```

2. Create a web3 provider:

    ```javascript
    const provider = sdk.makeWeb3Provider();
    ```

3. Request accounts to connect to the wallet:

    ```javascript
    const addresses = await provider.request({
        method: 'eth_requestAccounts',
    });
    ```

4. Handle provider events:

    ```javascript
    provider.on('connect', (info) => {
        console.log('Connected:', info);
    });

    provider.on('disconnect', (error) => {
        console.error('Disconnected:', error);
    });

    provider.on('accountsChanged', (accounts) => {
        console.log('Accounts Changed:', accounts);
    });
    ```

## Local Development

Run the test dapp locally for development:

1. Fork and clone this repository.
2. Install dependencies:

    ```shell
    yarn install
    ```

3. Start the development server:

    ```shell
    yarn dev
    ```

## Contributing

Contributions are welcome! See the [Contributing Guide](CONTRIBUTING.md) for details.

## License

This project is licensed under the [MIT License](LICENSE).

## Resources

- [Official Documentation](https://docs.cloud.coinbase.com/wallet-sdk/docs)
- [Test Dapp](https://coinbase.github.io/coinbase-wallet-sdk/)
- [Migration Guide (v3 to v4)](https://www.smartwallet.dev/sdk/v3-to-v4-changes)
