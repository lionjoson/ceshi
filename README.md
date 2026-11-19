# float updates

Signed software updates for float. This branch hosts release artifacts only.

## Downloads

- [float 0.6.5 for macOS / Apple Silicon](https://raw.githubusercontent.com/1379074387-hue/ceshi/float-updates/macos/float-0.6.5-macos-arm64.zip) — macOS 15 or newer.
- Windows: no Windows build is published yet. Do not use the Mac archive on Windows.

Mac users can check for updates inside **Settings → Updates**. Automatic checks can be switched off; installation is confirmed by the user. Users on 0.6.4 or earlier need to install this update-enabled version once.

## Platform-specific update feeds

- `releases.json`: platform catalog. Consumers select their own OS and architecture. `available: false` means there is no released build; it is never a fallback to another OS's installer.
- `macos/appcast.xml`: signed Sparkle feed for macOS. Update archives are Ed25519-signed; the public key is embedded in the app.
- `macos/latest.json`: metadata compatible with the older manual update checker.
- A Windows release will get its own installer, version, architecture requirements and update mechanism. Sparkle is used only by the Mac app.

Audio, subtitles and dictionary queries are not sent to this repository. Requests for update information or downloads use GitHub's hosting. The private signing key is stored in the publisher's local Keychain and is never part of this repository or the app.

## Release integrity

The Mac update feed and installer archive are signed. Modifying a signed file requires rebuilding and signing a new release. Model and dictionary downloads remain independent from app updates.

Licenses and acknowledgements for NotchSub, WhisperKit, Whisper, Sparkle and dictionary data are bundled inside the app's About & Privacy page.
