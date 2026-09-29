# pepvault-ota

Over-the-air update bundles for the [PepVault](https://pepvault.app) iOS app.

This repository holds no source code. Each release is a compiled web bundle (the app's JavaScript, CSS and assets, the same kind of code pepvault.app serves), published by PepVault's build pipeline.

- `ota-<version>` releases hold one bundle each (`bundle-<version>.zip`).
- `channel-<native version>` releases hold `manifest.json`, which tells the app on that native version which bundle to use.

The app only installs a bundle whose manifest carries a valid signature from PepVault's signing key and whose SHA-256 matches the file. If a new bundle doesn't start cleanly, the app rolls back on its own. Don't edit releases by hand.
