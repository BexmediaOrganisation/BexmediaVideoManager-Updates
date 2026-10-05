# Bexmedia Video Manager: Downloads

This is the **public release channel** for the Bexmedia Video Manager. It holds the downloadable builds, and the app checks this repo for updates.

## Download the latest version

**[Latest release →](https://github.com/BexmediaOrganisation/BexmediaVideoManager-Updates/releases/latest)**

- **Windows:** `Bexmedia Video Manager vX.Y.Z.exe`
- **macOS:** `Bexmedia Video Manager vX.Y.Z.dmg`. Open it and drag the app onto **Applications**.

## First launch: getting past the security prompt

The apps are **not code-signed**, so your computer warns you the first time. This is expected for an internal tool, and the app is safe. You only need to do this **once per version**.

### Windows
"Windows protected your PC" → **More info** → **Run anyway**.

### macOS
- **Older macOS** ("cannot be opened because the developer cannot be verified"): right-click (or Control-click) the app → **Open** → **Open**.
- **Recent macOS** ("Apple could not verify … is free of malware"): either open the app once (**Done**), then go to **System Settings → Privacy & Security** → **Open Anyway**; or clear the quarantine flag in **Terminal** (most reliable):
  ```sh
  xattr -c "/Applications/Bexmedia Video Manager.app"
  ```

> The source code lives in a separate private repository. This repo exists only to distribute builds and power the in-app update check. Releases are published here automatically.
