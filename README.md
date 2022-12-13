# Hardhat Fund Me

# Getting Started

## Requirements

- [git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
  - `git --version`
- [Nodejs](https://nodejs.org/en/)
    - `node --version`
- [Yarn](https://yarnpkg.com/getting-started/install) instead of `npm`
    - `yarn --version`
    - Might need to [install it with `npm`](https://classic.yarnpkg.com/lang/en/docs/install/) or `corepack`

## Quickstart

```
git clone https://github.com/akshtsng/HardhatFundMe
cd hardhat-fund-me
yarn
```

# Usage

Deploy:

```
yarn hardhat deploy
```

## Testing

```
yarn hardhat test
```

### Test Coverage

```
yarn hardhat coverage
```


# Deployment to a testnet or mainnet

1. Setup environment variables

- Set `GOERLI_RPC_URL` and `PRIVATE_KEY` as environment variables. Add them to a `.env` file.

- `PRIVATE_KEY`: The private key of account (like from [metamask](https://metamask.io/)). **NOTE:** FOR DEVELOPMENT, USE A KEY THAT DOESN'T HAVE ANY REAL FUNDS ASSOCIATED WITH IT.
  - [learn how to export it here](https://metamask.zendesk.com/hc/en-us/articles/360015289632-How-to-Export-an-Account-Private-Key).
- `GOERLI_RPC_URL`: This is url of the goerli testnet node we're working with. We can get setup with one for free from [Alchemy](https://alchemy.com/?a=673c802981)

2. Get testnet ETH

- Go to [goerlifaucet.com](https://goerlifaucet.com/) get some tesnet ETH.

3. Deploy

```
yarn hardhat deploy --network goerli
```

## Scripts

After deploying to a testnet or local net, run the scripts. 

```
yarn hardhat run scripts/fund.js
```

or
```
yarn hardhat run scripts/withdraw.js
```

## Estimate gas

Estimate how much gas things cost by running:

```
yarn hardhat test
```

We get output file called `gas-report.txt`

### Estimate gas cost in USD

To get a USD estimation of gas cost, we'll need a `COINMARKETCAP_API_KEY` environment variable.  Get one for free from [CoinMarketCap](https://pro.coinmarketcap.com/signup). 


## Verify on etherscan

If we deploy to a testnet or mainnet, we can verify it if we get an [API Key](https://etherscan.io/myapikey) from Etherscan and set it as an environemnt variable named `ETHERSCAN_API_KEY`.

In it's current state, if we have our api key set, it will auto verify goerli contracts!

However, we can manual verify with:

```
yarn hardhat verify --constructor-args arguments.js DEPLOYED_CONTRACT_ADDRESS
```

# Linting

`solhint` installation: [Documentation](https://protofire.github.io/solhint/#installation)

To check linting / code formatting:
```
yarn lint
```
or, to fix: 
```
yarn lint:fix
```

# Formatting 

```
yarn format
```


# Thank you!

[![Akshat Singh Linkedin](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/akshat-singh-a90bab1ba/)
