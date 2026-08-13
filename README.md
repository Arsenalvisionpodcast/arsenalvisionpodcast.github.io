# arsenalvisionpodcast.github.io

Infrastructure pages for the ArsenalVision app (not a website).

- `/.well-known/assetlinks.json` — Android App Links verification for the
  Patreon OAuth callback. The main site is Squarespace, which cannot serve
  files under `/.well-known/`, so verification lives on this domain.
  Fingerprints, in order: the CURRENT Play App Signing key (upgraded
  26 Jul 2026), the PREVIOUS Play App Signing key (still ~76% of the
  install base — devices on pre-upgrade installs verify against it),
  the upload key, and the local debug key. If the signing key is ever
  upgraded again (possible from 26 Jul 2027), add the new SHA-256 here
  from Play Console → App signing.
- `/patreon-callback/` — OAuth redirect target. Verified Android devices
  never see it (the OS opens the app directly); everywhere else it
  forwards `code`+`state` to `avpapp://patreon-callback`, same as the
  original bounce page on arsenalvisionpodcast.com.

App repo: https://github.com/Arsenalvisionpodcast/ArsenalVisionApp
(see HANDOFF.md → "Patreon OAuth App Links").
