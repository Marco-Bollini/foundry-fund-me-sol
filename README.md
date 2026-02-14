## Foundry

## Documentation

https://book.getfoundry.sh/

### Build

```shell
$ forge build
```

## foundry-fund-me-sol

This repository is a Foundry-based Solidity example project that implements a simple "Fund Me" contract and supporting utilities. It demonstrates
best practices for local development, unit and integration testing with mocks, deployment scripts, and interactions using Foundry tooling (`forge`, `anvil`, `cast`).

Key features

- FundMe contract with ETH funding and withdrawal logic
- Price conversion helper (`PriceConverter.sol`) used to check minimum USD contributions
- Local and integration tests under `test/` (unit and integration folders)
- Mock contracts for Chainlink price feeds (`MockV3Aggregator.sol`)
- Deployment and interaction scripts in `script/`

Requirements

- Linux, macOS or Windows with WSL
- Foundry (forge, cast, anvil). Install with:

Quick start (local development)

1. Start a local chain with `anvil` (recommended):

```bash
anvil
```

2. In another terminal, build the project:

```bash
forge build
```

3. Run the test suite (unit + integration):

```bash
forge test
```

Common commands

- Build: `forge build`
- Run tests: `forge test` (add `-vv` for verbose output)
- Format: `forge fmt`
- Run a single test file: `forge test --match-path test/unit/FundMe.t.sol`
- Run snapshot for gas reports: `forge snapshot`
- Start a local node: `anvil`
- Use `cast` for RPC calls: `cast <subcommand>`

Running scripts and deployment

The `script/` folder contains example scripts for deploying and interacting with contracts. Example:

1. Start `anvil` or connect to an RPC provider.

2. Deploy locally (broadcast the transaction):

```bash
forge script script/DeployFundMe.s.sol:DeployFundMe --broadcast --fork-url http://127.0.0.1:8545
```

3. Deploy to a public testnet (provide RPC url and a private key):

```bash
forge script script/DeployFundMe.s.sol:DeployFundMe --rpc-url <RPC_URL> --private-key <PRIVATE_KEY> --broadcast
```

Replace `<RPC_URL>` and `<PRIVATE_KEY>` with your values. Consider using environment variables or a secrets manager to avoid leaking keys.
