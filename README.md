# arsenalvisionpodcast.github.io

Infrastructure pages for the ArsenalVision app (not a website).

- `/.well-known/assetlinks.json` — Android App Links verification for the
  Patreon OAuth callback. The main site is Squarespace, which cannot serve
  files under `/.well-known/`, so verification lives on this domain.
  Fingerprints: the upload key and the local debug key are present;
  **the Google Play App Signing certificate fingerprint must also be
  listed** (Play Console → Test and release → Setup → App signing →
  App signing key certificate → SHA-256) or Play-installed builds won't
  verify.
- `/patreon-callback/` — OAuth redirect target. Verified Android devices
  never see it (the OS opens the app directly); everywhere else it
  forwards `code`+`state` to `avpapp://patreon-callback`, same as the
  original bounce page on arsenalvisionpodcast.com.

App repo: https://github.com/Arsenalvisionpodcast/ArsenalVisionApp
(see HANDOFF.md → "Patreon OAuth App Links").
