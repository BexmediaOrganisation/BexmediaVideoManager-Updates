<!-- Generated from GUIDE-USER.md in the private BexmediaVideoManager repo by publish-user-guide.yml.
     Edit it there: changes made here are overwritten. -->

# Bexmedia Video Manager: user guide

Bexmedia's desktop app for the team's Vimeo library. It uploads new videos, swaps in new versions of existing ones without breaking their links, and shows you what clients have said.

Think of a Vimeo project folder as a shelf of framed pictures, and your exports as newer prints. The app slips each new print into its existing frame: same frame, same place on the wall, same visitor comments. It just updates the label. It only buys a new frame for a print that has never had one.

**Contents:** [Install](#1-install-the-app) · [Connect to Vimeo](#2-connect-it-to-vimeo-once) · [Upload](#3-upload-videos-and-new-versions) · [Dashboard](#4-the-dashboard) · [Everyday extras](#5-everyday-extras) · [Updates](#6-updates) · [Known limits](#known-limits) · [Troubleshooting](#troubleshooting)

## 1. Install the app

1. Open the **[latest release](https://github.com/BexmediaOrganisation/BexmediaVideoManager-Updates/releases/latest)** and, under **Assets**, download the file for your computer:
   - **Mac:** `Bexmedia Video Manager vX.Y.Z.dmg`
   - **Windows:** `Bexmedia Video Manager vX.Y.Z.exe`
2. **Mac:** open the `.dmg` and drag **Bexmedia Video Manager** onto **Applications**. Open it from Applications.
   **Windows:** the `.exe` *is* the app, so there's no installer. Put it somewhere permanent (for example your Documents folder, or pin it to the taskbar) and double-click it.
3. **The first time you open a new version, your computer warns you.** The app isn't code-signed. That's normal for an internal tool, and the app is safe:
   - **Mac:** "Apple could not verify…". Press **Done**, then go to **System Settings → Privacy & Security**, scroll down, and press **Open Anyway**. If that doesn't appear, open **Terminal** and run:
     ```sh
     xattr -c "/Applications/Bexmedia Video Manager.app"
     ```
   - **Windows:** "Windows protected your PC". Press **More info**, then **Run anyway**.

## 2. Connect it to Vimeo (once)

The app talks to Vimeo with a **token**: a personal key, like a password made just for this app. Everyone makes their own.

1. Sign in to Vimeo with **your own** team-member login, then go to **[developer.vimeo.com/apps](https://developer.vimeo.com/apps)**.
2. Open the **Bexmedia** app there. If you can't see one, ask Tom.
3. Choose **Generate access token**, then **Authenticated**, and tick these scopes:
   `public` `private` `edit` `upload` `video_files` `interact` `create`
   Add `delete` **only** if you've been asked to clear out old projects (see [History](#history-clearing-out-old-projects)).
4. **Copy the token straight away.** Vimeo shows it only once. It's a long string of 32 letters and numbers. The *Client identifier* and *Client secrets* on that page are **not** tokens.
5. Open Bexmedia Video Manager, press **Token** (top right), paste, and press **Save**. The header shows **CONNECTED**.

The token is stored only on your computer, in your own settings folder. If a scope is missing, the header says which one; make a new token with the right scopes and paste it in again.

**Token rules** (Vimeo's terms, and common sense):
- **Never share your token**, not even with a colleague in a hurry. They make their own. Never use someone else's.
- Never put it in an email, a chat, a screenshot or a document. The only place it goes is the app's **Token** box.
- Lost a computer, leaving Bexmedia, or think it leaked? **Delete it** at developer.vimeo.com → your app → *Authentication*.

## 3. Upload videos and new versions

Open the **Upload** tab.

> **Every file name must carry a version:** `_V1`, ` V2`, `-v03`, etc. (upper or lower case, after `_`, a space or `-`). Files without one are turned away. The version decides what's newer: `Hero_V3.mp4` replaces a video called `Hero_V2`.

1. **Project:** type the project name from the Bexmedia Project Creator, for example `#20260001 Client Name - Project Title`.
2. **Folder:** browse the team library and pick the client folder. The app creates the project folder inside it, or uses the existing one (it tells you if the name already exists).
3. **Videos:** choose one or many files (`.mp4`, `.mov`, `.m4v`, `.mxf`).
4. **Empty folder:** they upload straight in. **Folder with videos:** choose **Replace videos** or **Add new videos**.
5. **Review:** every row has a tick box. **Nothing changes on Vimeo until you press Apply.**
   - *Replace* pairs each file with a video by name. Exact matches are ticked for you. Close matches are suggested but left unticked for you to check, and **Change match…** lets you pick another video, or upload as new.
   - A replace needs a **higher version** than the video already has.
   - If the name itself would change (not just the version), ticking the row asks you to confirm. You can edit the title, but **it must always carry the file's version**.

**What a replace keeps:** the video's link, review page, comments and version history. Clients' links never break. After a replace the title becomes the new file name, so it shows the new version.

## 4. The Dashboard

The app opens on the **Dashboard**. **Refresh** reloads everything. **Who am I?** tells the app your name as Vimeo shows it, which powers *Just me* and *My uploads*.

- **Overview:** five cards, each a shortcut:
  - **New on my videos:** unseen comments on videos you uploaded.
  - **Last 24 hours:** uploads and new versions, team-wide.
  - **Active projects** and **All videos**.
  - **Clear out:** projects untouched for 2 years.

  Pink numbers mean something wants a look. Underneath: videos with new comments, and what changed in the last day. Click a card, or **open** on a row, to jump there.
- **Feedback at a glance:** a tree of projects with how many new comments each has. Twirl one open to see its videos. Comments are counted per version. *On current version* is the feedback to act on; *On earlier versions* was made before a newer version replaced it. **open** goes to the video's review page or the project folder on Vimeo. Scope it to the whole *Team*, *A project*, or *Just me*. Opening a review page marks that video as seen.
- **Projects:** the library as a tree (client folders, then projects) with video counts, new comments and last upload. Select some or all of a project's videos (*Select all*), then **Add new versions…**: choose files, and they're matched against only the videos you selected.
- **Recent activity:** what was uploaded or given a new version in the last 24 hours, 7 days or 30 days, and by whom.
- **All videos:** every video, sortable. Filter by uploader, search (video, folder or commenter), *My uploads*, *New comments only*.
- **History:** old projects by date, for clearing out (see below).

**Pink flags:** **● NEW** marks unseen comments; **● 24H** marks anything uploaded or changed in the last 24 hours. The window title shows your count of new comments, for example `(3) Bexmedia Video Manager`. "New" is tracked per person, per computer. The first time you open the app, existing comments count as already seen.

**Long names:** if a title is cut off, rest the pointer on it and a box shows the whole thing.

### History: clearing out old projects

> **Deleting is permanent.** Only do this if you've been asked to, and only with a token that has the extra `delete` scope. Without it the delete buttons are switched off, though anyone can browse the list.

Set *Last activity from / to* (or *Older than 1 / 2 / 3 yr*), select projects, then choose:
- **Delete old file versions:** each video keeps its current version, link and review page; older file versions go.
- **Delete superseded videos:** separate videos that share a name with a higher version in the same folder (for example `Hero V1` and `Hero V2` next to `Hero V3`) are deleted; the highest is kept.
- **Delete chosen videos:** you tick exactly which.
- **Delete everything:** every video in the selected projects. The empty folders stay.

You always see exactly what will go. Anything with unseen comments, or uploaded in the last 90 days, starts **unticked**. Nothing happens until you type the confirmation phrase (`DELETE` and the count). Every item is logged in `deletion logs/` in your settings folder.

## 5. Everyday extras

- **Copy review links** (on every view): copies each selected video's name and review link, ready to paste into an email to a client.
- **Download:** select videos, choose what to save (the video file in the qualities Vimeo has, the transcript `.txt`, the subtitles `.vtt`) and a folder. Each file shows its progress and an **Open location** button. Nothing already in the folder is overwritten.
- **Thumbnails:** rest the pointer on a video row to see its thumbnail.
- **Live alerts:** the app checks Vimeo every minute for new uploads and versions, and every five minutes for new comments. When something changes you get a pink line in the footer and a soft chime: for new comments on *your* videos, new uploads, and new versions. **Sound on / Sound off** in the header turns the chime on or off. Vimeo can't push alerts to a desktop app, which is why the app looks for them itself.
- **Dark or light:** the app opens in its dark theme. **Dark theme / Light theme** in the header, next to **Sound on / Sound off**, switches straight away without losing your place, and the app remembers your choice. It waits while an upload, download or deletion is running.

## 6. Updates

A few seconds after it opens, the app checks for a newer version. If there is one, it asks whether to open the download page. Install it the same way as the first time ([Install](#1-install-the-app); on a Mac choose *Replace* when you drag it onto Applications; on Windows replace the old `.exe`). Expect the security warning again: it appears once per version.

The **Updates** button in the header checks on demand and always tells you the result. Your version number is at the top of the window (`VIDEO MANAGER V0.2.0`). All versions, and what changed in each, are on the **[releases page](https://github.com/BexmediaOrganisation/BexmediaVideoManager-Updates/releases)**.

## Known limits

- **Comments left on a Vimeo review page** (`vimeo.com/reviews/…`) **don't reach the app.** Vimeo doesn't make them available to apps. Comments on the normal video page do show. A comment without a name shows as **Guest**.
- **Comments are counted per version**, so a video's own page on Vimeo can show a bigger total than the app's *On current version*: Vimeo's review page only shows comments on the current version.
- **The security warning on first launch** comes back with each new version, because the app isn't code-signed.
- **The studio account:** uploads made through the shared `Bexmedia` Vimeo login show `Bexmedia` as the uploader, whoever did them.

## Troubleshooting

| What you see | What to do |
|---|---|
| "Apple could not verify…" / "Windows protected your PC" | Expected. See [Install](#1-install-the-app), step 3. |
| "Could not connect", or a **401** | The token is missing or wrong. Press **Token**, paste a fresh one, **Save**. |
| Header says **TOKEN MISSING** *scope* | Make a new token with all the scopes in [Connect](#2-connect-it-to-vimeo-once) and paste it in. |
| The **folder** buttons are greyed out | Your token lacks `create`. Make a new token with it. |
| A file is rejected on the Upload tab | Its name has no version. Rename it to end in `_V1`, ` V2`, etc. |
| A replace says it needs a higher version | The video already has that version or a newer one. Check you picked the right file. |
| New uploads don't land in the folder (403) | Your token lacks `interact`. Make a new token with it. |
| The app never offers an update | Press **Updates** to check. If it can't reach GitHub, check your internet. |
| Anything else | Ask Tom. Include a screenshot of the window (never of your token). |
