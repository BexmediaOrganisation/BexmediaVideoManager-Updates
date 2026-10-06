<!-- The install section is generated from GUIDE-USER.md in the private BexmediaVideoManager repo
     by publish-install-steps.yml. Edit it there: changes made here are overwritten. -->

# Bexmedia Video Manager — Downloads

Public release channel for Bexmedia Video Manager. Holds downloadable builds; the app checks this repo for updates.

**[Latest release →](https://github.com/BexmediaOrganisation/BexmediaVideoManager-Updates/releases/latest)**

## 1. Install the app

**Mac:**

1. Open the **[latest release](https://github.com/BexmediaOrganisation/BexmediaVideoManager-Updates/releases/latest)** and, under **Assets**, download `Bexmedia Video Manager vX.Y.Z.dmg`.
2. Open the `.dmg` and drag **Bexmedia Video Manager** onto **Applications**. Open it from Applications.
3. **The first time you open a new version, your computer warns you.** The app isn't code-signed. That's normal for an internal tool, and the app is safe: you'll see "Apple could not verify…". Press **Done**, then go to **System Settings → Privacy & Security**, scroll down, and press **Open Anyway**. If that doesn't appear, open **Terminal** and run:
   ```sh
   xattr -c "/Applications/Bexmedia Video Manager.app"
   ```

**Windows:**

1. Open the **[latest release](https://github.com/BexmediaOrganisation/BexmediaVideoManager-Updates/releases/latest)** and, under **Assets**, download `Bexmedia Video Manager vX.Y.Z.exe`.
2. The `.exe` *is* the app, so there's no installer. Put it somewhere permanent (for example your Documents folder, or pin it to the taskbar) and double-click it.
3. **The first time you open a new version, your computer warns you.** The app isn't code-signed. That's normal for an internal tool, and the app is safe: you'll see "Windows protected your PC". Press **More info**, then **Run anyway**.
