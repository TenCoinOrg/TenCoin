# TenCoin


# TenCoin (TEC)

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Network Status](https://img.shields.io/badge/Network-Mainnet-green.svg)]()

**TenCoin** is a decentralized, peer-to-peer cryptocurrency designed for secure, autonomous, and time-locked transactions. Inspired by Bitcoin, TenCoin introduces advanced features such as **timer transactions**, **verify-code transactions**, and an automated **completed_fee reward system** for miners.

---

## Table of Contents
- [Introduction](#introduction)
- [Key Features](#key-features)
- [Technical Details](#technical-details)
- [Getting Started](#getting-started)
- [Example Usage](#example-usage)
- [Contributing](#contributing)
- [License](#license)

---

## Introduction
TenCoin (TEC) aims to provide a fully autonomous blockchain experience where transactions with time locks and verification codes can be executed automatically by the network without user intervention. It supports standard wallets and is designed for scalability and performance.

- **Ticker:** TEC  
- **Smallest Unit:** Teno (8 decimals, like satoshi)  
- **Total Supply:** 10,000,000 TEC  

---

## Key Features
- **UTXO-based transaction model** for transparency and security.  
- **Timer transactions**: schedule transfers to be automatically executed at a future time.  
- **Verify-code transactions**: allow conditional unlocking with a secret code.  
- **Completed_fee system**: miners earn rewards for completing timer or verify-code transactions.  
- **Multisig & advanced scripts**: supports timelock, multisignature, and custom script conditions.  
- **P2P network** with dedicated ports:
  - Mainnet: `10110` (P2P), `10111` (RPC)  
  - Testnet: `10112`  
- **JSON RPC API**: compatible with standard wallets like Trust Wallet.  
- **Cross-platform nodes**: lightweight nodes can run autonomously, even on limited hardware.

---

## Technical Details
- **Consensus:** PoW initially, upgradeable to PoS in the future.  
- **Halving:** every 100,000 blocks, initial block reward 50 TEC.  
- **Transaction Fees:**  
  - `fee`: paid to miner including transaction in block  
  - `completed_fee`: reserved at creation, paid when transaction is redeemed or refunded  
- **Timer behavior:** nodes execute transactions automatically at `set_time`.  
- **Refund behavior:** handled deterministically; `completed_fee` always paid.  
- **Verify-code transactions:** `verify_code_input` must match `verify_code_hash` stored in transaction metadata.  

---

## Getting Started

### Prerequisites
- Rust >= 1.88.0  
- Cargo >= 1.88.0  
- Compatible OS: Linux, Windows, macOS  

### Installation
```bash
git clone https://github.com/TenCoin-crypto/TenCoin.git
cd TenCoin
cargo build --release

