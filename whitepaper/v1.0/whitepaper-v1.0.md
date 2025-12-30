# TenCoin (TEC) — Whitepaper v1.0

**A UTXO-Based Blockchain with Native Timelock & Conditional Transactions**

**Version:** 1.0  
**Network Supply Model:** Deflationary Halving Schedule  
**Consensus:** Proof-of-Work  
**Block Time:** 5 Minutes  
**Halving Interval:** Every 100,000 Blocks

---

## 1. Executive Summary

TenCoin (TEC) is a decentralized blockchain built on a UTXO model, extended with native timelock outputs and conditional dual-state UTXOs. It enables autonomous, predictable, and programmable transfers without relying on external smart-contract layers.

TenCoin is designed for:

- Transparent and verifiable monetary issuance  
- Deferred payments and time-based custody  
- Escrow-like conditional transfers  
- Secure long-term storage through time-vault wallets  

---

## 2. Network Parameters

| Parameter               | Value                                |
|-------------------------|--------------------------------------|
| Consensus Mechanism      | Proof-of-Work                        |
| Block Time               | 5 minutes                             |
| Initial Block Reward     | 50 TEC                                |
| Halving Interval         | Every 100,000 blocks                  |
| Smallest Unit            | Teno (8 decimals)                     |
| Transaction Model        | UTXO-based script validation          |
| Fee Model                | Standard miner fee per transaction    |

The emission schedule follows a deterministic halving curve, providing predictable monetary policy for the network.

---

## 3. Transaction Model & Script Architecture

TenCoin extends the classical UTXO model:

- Each transaction output defines spending conditions  
- Conditions are expressed through output-level scripts  
- Full nodes deterministically validate all transactions  

### Supported Capabilities:

- Timelock Outputs (Timer Transactions)  
- Conditional Dual-State UTXOs with Verification Code  

These features are embedded in the blockchain state, ensuring autonomous execution and immutable auditability.

---

## 4. Timelock Transactions

A timelock UTXO defines a future unlock time:

- Timestamp or block-height stored in the output script  
- Output is non-spendable until the condition is met  
- Full nodes enforce the restriction at validation  

**Use Cases:**

- Deferred transfers  
- Scheduled asset releases  
- Long-term custody wallets  

---

## 5. Conditional Dual-State UTXOs

Certain outputs define two spending paths:

| State | Condition                                        | Actor            |
|-------|-------------------------------------------------|----------------|
| A     | Receiver provides correct verification code before maturity | Receiver        |
| B     | Sender recovers funds after maturity if not redeemed | Original Sender |

**Benefits:**

- Escrow-like guarantees  
- Reversible and conditional transfers  
- Fully deterministic, no off-chain execution required  

**Example Transaction:**

Output: 100 TEC
Condition: hash("secret-code") = stored value
State A: Receiver redeems with correct code before block #200,000
State B: Sender can reclaim after block #200,000 if unspent

---

## 6. Time-Vault Wallets

TenCoin supports time-vault addresses:

- Anyone can deposit funds  
- Funds are locked until a future timestamp  
- Creator or third-party cannot bypass the lock  

**Illustrative Use Case:**

- Custodial wallet for a child at birth  
- Unlocks at adulthood  
- Deposits possible anytime, funds remain locked until maturity  

---

## 7. Economic & Security Principles

- Deterministic issuance via halving schedule  
- Full-node validation ensures consensus enforcement  
- PoW secures the network  
- All transaction logic embedded in scripts, guaranteeing predictable behavior  

---

## 8. Network & Infrastructure

- Transaction Model: UTXO with advanced script conditions  
- Node Architecture: Cross-platform and resource-efficient  
- Interface: JSON-RPC for wallet & tooling integration  
- Network Roles: Full nodes enforce rules and validate state  

---

## 9. Use-Case Domains

- Deferred payroll & scheduled payments  
- Savings vaults and locked reserves  
- Conditional remittances and escrow  
- Inheritance & multi-year trusts  
- Programmable time-based asset distribution  

All operate natively via UTXO scripts without external execution layers.
