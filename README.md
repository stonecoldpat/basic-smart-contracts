# Basic smart contracts

You will need to update `secrets.config.ts` with the following:

- **Private key** - A private key associated with Goerli funds
- **Provider ID** - Infura ID to connect to the Goerli network
- **Etherscan** - An Etherscan API key to assist with verifying deployed code

Once configured, you can set up the project:

```
npm i
npm run build
npm run test
```

You can checkout `package.json` to review how the 'run' commands are defined for compilg/testing using hardhat.

## Smart contracts

There are three smart contracts:

- `Echo.sol` - Broadcasts a message via an event
- `HandlePayments.sol` - An example of handling ETH deposits and withdrawals
- `CallContract.sol` - Interacting with another smart contract using interfaces or .call()

## Scripts

We have put together four scripts:

- `echoDeploy.ts` - Deploy the Echo smart contract to a network (Goerli)
- `echoHistoricalEvents.ts` - Fetch historical events for the Echo smart contract (eth_getLogs)
- `echoSendBroadcast.ts` - Send a transaction to the network (Goerli) that invokes the broadcast function
- `echoWatchEvent.ts` - Logs events in real-time for the Echo smart contract

**Deploy your own Echo.** You can use `echoDeploy.ts` to deploy a new Echo smart contract. You will need to update `config.ts` before the other scripts will adopt the new address. Another option is to use an already deployed Echo smart contract and we have included a default address that works on Goerli. Challenge: Change the Echo.sol code slighty, deploy a new instance of it on Goerli, and then try to verify its code on Etherscan.

**Watch events.** You can turn on `echoWatchEvent.ts` to log new events that are emitted by Echo.sol and see it working by broadcasting a transaction to the Echo smart contract using `echoSendBroadcast.ts`

# Unit tests

We cover the following in the unit tests:

- Checking the owner of a smart contract
- Fetching a value stored in a smart contract
- Checking if an event (with specific arguments)
- Encoding function signature and interacting with another smart contract
- Depositing and withdrawing funds
