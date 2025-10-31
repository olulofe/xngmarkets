# xNG Markets

## Repository Layout

```
xngmarkets
  ├─ contracts                      # Contracts and deployment scripts (HTS, HSCS)
  ├─ app                            # Nextjs Dapp hosted on Vercel
  └─ oracle-cron                    # Cron job to fetch off-chain stock price and update price Oracle Contracts on Hedera (Every 3 mins)
  └─ whitepaper                     # xNG Market Whitepaper
```

## Track

Onchain Finance & Real-World Assets (RWA)

## Pitch Deck

[https://drive.google.com/file/d/1Txpz_6C2cqii5KgG2SLf4GviYi6H2XJ9/view](https://drive.google.com/file/d/1p8O-3u5S4UbTnim_ewRlGgOWXUVtHbdH/view)

## Hedera Certification Link

https://drive.google.com/file/d/1PgTy6o4DdmVxgs3CDG8km5NMD8xEfxCZ/view

## Hedera Services Used

1. **Hedera Token Service (HTS)**
Used to tokenize NGX blue-chip stocks with KYC and Freeze keys for compliance.
2. **Hedera Smart Contract Service (HSCS)**
Deployed core contracts, including the OracleHub, CLOB, BorrowSupplyV1, and Settlement Adapter for logic execution.
3. **Hedera Consensus Service (HCS)**
Publishes price data and oracle updates, ensuring transparent off-chain data feeds and auditability.
4. **Hedera Mirror Node**
Used by the frontend to stream live updates for trades, portfolio data, and oracle price bands.

## Hedera Transaction Types

- TokenMintTransaction
- TransferTransaction
- ContractExecuteTransaction
- TokenCreateTransaction
- ContractCallQuery

## Deployed Contracts (Hedera Testnet)

| Contract                | Explorer Link                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| :---------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 12 HTS Tokenized Assets | [xNGX-MTNN](https://hashscan.io/testnet/token/0.0.6807185), [xNGX-UBA](https://hashscan.io/testnet/token/0.0.6807187), [xNGX-GTCO](https://hashscan.io/testnet/token/0.0.6807188), [xNGX-ZENITHBANK](https://hashscan.io/testnet/token/0.0.6807189), [xNGX-ARADEL](https://hashscan.io/testnet/token/0.0.6807190), [xNGX-TOTALNG](https://hashscan.io/testnet/token/0.0.6807191), [xNGX-AIICO](https://hashscan.io/testnet/token/0.0.6807192), [xNGX-CORNERST](https://hashscan.io/testnet/token/0.0.6807193), [xNGX-OKOMUOIL](https://hashscan.io/testnet/token/0.0.6807194), [xNGX-PRESCO](https://hashscan.io/testnet/token/0.0.6807195), [xNGX-NESTLE](https://hashscan.io/testnet/token/0.0.6807196), [xNGX-DANGSUGAR](https://hashscan.io/testnet/token/0.0.6807197) |
| OracleHub.sol           | [0.0.6809934](https://hashscan.io/testnet/contract/0.0.6809934)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| Clob.sol                | [0.0.6955617](https://hashscan.io/testnet/contract/0.0.6955617)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| DirectSettleAdapter.sol | [0.0.6955987](https://hashscan.io/testnet/contract/0.0.6955987)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| BorrowSupply.sol        | [0.0.6837722](https://hashscan.io/testnet/contract/0.0.6837722)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| MockUSDC.sol            | [0.0.6808751](https://hashscan.io/testnet/contract/0.0.6808751)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
## Architecture Diagram

<img width="1600" height="961" alt="image" src="https://github.com/user-attachments/assets/f8ef86f5-a30e-47e2-8dd3-dd88a6acfea5" />


## Setup

### Requirements
* Node JavaScript runtime environment >= v18 installed
* Linux or Mac OS
* solc, solidity compiler 0.8.0 minimum

### Installation

* Clone repository
* cd `app`
* Copy `.env.example` to `.env` (See below)
* Run `npm install`
* Run `npm run dev`

```env
NEXT_PUBLIC_PROJECT_ID = 
NEXT_PUBLIC_EXPLORER = 
NEXT_PUBLIC_CHAIN_ID = 
NEXT_PUBLIC_RPC_URL = 

NEXT_PUBLIC_ORACLE_HUB_CONTRACT = 
NEXT_PUBLIC_USDC_XNG_CONTRACT = 
NEXT_PUBLIC_DIRECT_SETTLE_ADAPTER_CONTRACT = 
NEXT_PUBLIC_CLOB_CONTRACT = 
NEXT_PUBLIC_BORROW_SUPPLY_CONTRACT = 

mongodbURI =
OPERATOR_ID = 
OPERATOR_KEY = 
```

### Steps

* Get MOCK USDC from https://hedera-usdc-faucet.vercel.app/
* Visit https://xng.markets
* Place a Buy limit order for any tokenized stock
* Provide Liquidity for Lending
* Place a Sell limit order (If your buy limit order was fulfilled)
* Use your tokenized stock to get USDC backed loan
