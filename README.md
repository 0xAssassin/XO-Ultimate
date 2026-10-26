<p align="center">
  <img src="docs/assets/logo.jpeg" width="120" alt="XO Ultimate logo">
</p>

<h1 align="center">XO Ultimate</h1>
<p align="center"><strong>Think. Play. Win.</strong></p>
<p align="center">A neon tic-tac-toe game with AI challenges, local multiplayer, custom boards, music, and an offline Android app.</p>
<p align="center">
  <a href="https://github.com/0xAssassin/XO-Ultimate/releases/download/v1/XO-Ultimate.apk">Download Android APK</a> ·
  <a href="https://github.com/0xAssassin/XO-Ultimate/releases">Releases</a> ·
  <a href="https://github.com/0xAssassin/XO-Ultimate/issues">Report a bug</a>
</p>

## About

XO Ultimate takes classic tic-tac-toe beyond the 3 × 3 board. Challenge the computer or play with a friend on the same device. Choose your winning line and board size, then start the match.

The website keeps a compact portrait layout on phones, PCs, and laptops. The Android app bundles the game locally for offline play.

## Features

- **VS Computer:** Easy, Medium, and Hard difficulties. Easy is selected by default.
- **Local multiplayer:** Two players take turns on the same device.
- **Four win rules:** Connect 3, 4, 5, or 6 marks horizontally, vertically, or diagonally.
- **Board previews:** Swipe or use side arrows, tap a card to select, and press Start Game.
- **Neon interface:** Custom XO artwork, highlighted moves, winning lines, and result dialogs.
- **Audio:** Background music, tap/move effects, and separate win, loss, and draw sounds.
- **Controls:** Volume, music, sound effects, vibration, new rounds, and score reset.
- **Saved preferences:** Audio settings are stored locally when browser storage is available.
- **Offline game:** Images and sounds are embedded in the HTML. Downloading the APK requires internet access.
- **No ads:** No advertising SDK is included.

## Win rules and boards

| Win condition | Available boards |
| --- | --- |
| 3 in a row | 3 × 3 |
| 4 in a row | 4 × 4 or 5 × 5 |
| 5 in a row | 9 × 9 or 11 × 11 |
| 6 in a row | 11 × 11 |

Hard difficulty uses exhaustive minimax on the classic 3 × 3 board. Larger boards use a tactical evaluator; they are not guaranteed to be unbeatable.

## Play in a browser

1. Download or clone this repository.
2. Open `index.html` in a modern browser with JavaScript enabled.
3. Choose VS Computer or Local Multiplayer.
4. Select a win rule, continue to board selection, choose a board, and press Start Game.

The web game needs no package installation, build step, server, or API key. Browser audio starts after interaction. If sound is silent, tap the **♪** button in the header or **Enable & Test Sound** in Settings. Check device media volume and site audio permissions if necessary.

## Install on Android

1. Download [XO-Ultimate.apk](https://github.com/0xAssassin/XO-Ultimate/releases/download/v1/XO-Ultimate.apk).
2. Open the downloaded file on your Android phone.
3. If Android asks, allow installation from the browser or file manager used to open it.
4. Install and launch **XO Ultimate**.

**Minimum version:** Android 8.0 / API 26. The app uses the device's Android WebView; an updated WebView is recommended. The only declared app permission is vibration.

An APK is an Android application. PCs and laptops can play the browser version or download the APK to transfer to an Android device.

## Website and APK versions

The `v1` APK is the first Android build. The root `index.html` includes subsequent website fixes for mobile audio and background APK downloads. The public Android source under `android/` matches the initial APK's bundled game; it does not automatically update when the website changes.

To ship website changes inside a new APK, update `android/assets/index.html`, increment the Android version, and rebuild using the original private signing key. See [Android build instructions](android/README.md).

## Repository layout

```text
index.html               Browser game, with embedded artwork and audio
android/                 Native Android wrapper and original v1 game asset
  src/                   Java Activity
  res/                   App icon and Android theme
  assets/index.html      Game bundled in Android v1
  AndroidManifest.xml    Package metadata and permissions
  build.sh               Android build script
  README.md              Build and signing instructions
docs/assets/logo.jpeg    README artwork
CHANGELOG.md             Website and Android version history
RELEASE_NOTES.md         Release description for Android v1
CONTRIBUTING.md          Contribution and bug-report guidelines
GITHUB_SETUP.md          Repository upload checklist
```

## Downloads

The website's download button uses the GitHub release asset:

```text
https://github.com/0xAssassin/XO-Ultimate/releases/download/v1/XO-Ultimate.apk
```

When publishing a new APK, upload it as a release asset and update `githubReleaseUrl` in the `apk-download-config` block of `index.html`. Keep the private signing backup out of the repository and release assets.

## Privacy

The supplied game source does not include analytics or advertising integrations. Audio preferences stay in local browser/WebView storage. GitHub handles requests to download the APK.

## Contributing

Bug reports and suggestions are welcome. Read [CONTRIBUTING.md](CONTRIBUTING.md) before opening an issue or pull request.

## License

No license has been selected for this repository. A license file can be added separately by the repository owner.

---

Maintained by [0xAssassin](https://github.com/0xAssassin).
