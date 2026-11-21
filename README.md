# Filo

**Fi-lo because qui-lo. A fast, lean file explorer for Windows.**

Filo is one small `.exe`, no need to install it and it needs no runtime. It opens a folder with half a million files in an instant, has undo for every file operation, a copy queue that knows your disks, batch rename, your own commands triggered by hotkeys and fast phone browsing that you can cancel. The last one alone may restore your love for Android.

<!-- screenshot: docs/filo.png -->

## Download

Get it here: https://github.com/riozebratubo/filo/releases/download/1.0.2/filo.exe.

---

## At a glance

|                                                              | **Filo** | Windows Explorer | The other lean and fast alternative |
| ------------------------------------------------------------ | :------: | :--------------: | :---------------------------------: |
| One small portable `.exe`                      | ✅ ~3 MB | ❌ part of Windows | ✅ |
| Huge folders opens with no lag                | ✅ | ❌ | ✅ |
| Folder sizes in the list, chosen per SSD / HDD     | ✅ | ❌ | ✅ |
| Type to filter with partial letters   | ✅ | ❌ | ✅ |
| Undo **and redo** of every file operation | ✅ | ⚠️ limited | ❌ |
| Batch rename: tokens, regex, case, live preview              | ✅ | ❌ | ✅ |
| Run your own programs on the selection by hotkey                | ✅ | ❌ | ❌ |
| Edit dates and attributes of files              | ✅ | ❌ | ❌ |
| Copies queued per physical disk with pause and reorder      | ✅ | ❌ | ❌ |
| Phones and cameras (MTP) working fast and you can cancel operations | ✅ | ❌ | ❌ |

---

## Why use Filo?

### Filo is really fast

- **Folders are read through the NT directory API** on a worker thread, Filo windows are responsive the whole time
- **Changes show up quickly** Each window watches its folder and applies new, removed and renamed items in place, not affecting your selection and scroll position
- **Folder sizes all the time (when we can)** in the background for the folder you're looking at. They stay up to date as things change and you can choose where it happens: SSDs, hard disks, network shares
- **One process for all the windows** A new window opens quickly when you need it

### Search just by typing

- **Just type** Typing in a folder filters it. Full matches come first, then partial ones, where the letters only have to appear in order. The matched letters are highlighted
- **Need better searching? Just `Ctrl+f`** You can now search subfolders and have more control

### File operations you can trust

- **Undo and redo everything.** Copy, move, rename, new, delete (restored from the Recycle Bin), batch rename and property edits. There's one journal for all windows, with no limit on undo steps.
- **A queue that knows your disks.** Jobs on the same physical disk (or the same server) take turns instead of thrashing it. Jobs on different disks run side by side. A waiting job can be cancelled, moved up or down, or started now.
- **One progress window for everything,** with pause and cancel. You can close the last window and let the jobs finish in the background.
- **A real conflict dialog:** replace, skip, keep both, or replace if newer, for one name or all of them. It shows sizes and dates, and folders are merged.
- Prefer Windows' own progress and conflict dialogs? One setting each.

### Tools Explorer never had

- **Batch rename** (F2 on several items, or `Ctrl+Shift+R`): `[N]` name, `[E]` extension, `[C]` counter (start, step, digits), `[YMD]` and `[hms]` modified date and time, `[P]` parent folder. Find and replace, plain or regex, and case changes. A live preview marks clashes in red, and the whole rename is one undo step.
- **Your own commands.** Run any program on the selection with a hotkey, from the context menu or from the toolbar. Placeholders: `{items}` `{item}` `{folder}` `{name}` `{stem}` `{ext}`. A command can run once for all items or once per item, and can be limited to files, folders or extensions.
- **Edit files properties** (`Alt+Enter`): created, modified and accessed dates; Read-only, Hidden, System, Archive and Not indexed (three-state across a selection); NTFS compression and EFS encryption; cloud files pinned or unpinned. It works on many items at once, optionally including everything inside the selected folders, and the edit is one undo step.
- **Zip built in.** Compress to `.zip`, extract here, extract to a folder, extract to.

### Stellar phones and cameras handling

Windows' handling of phones (MTP) is slow, hangs, and can't really be cancelled. Filo talks to phones, tablets, cameras and players **itself**:

- A **Devices** section in the tree, and a tile for each storage.
- Listings are cached and kept fresh by the device's own events. Thumbnails come from the device.
- **Every copy can be stopped.** A cancelled or failed copy doesn't leave a half-written file behind.
- Drag items out to any program, or copy and paste them, just like files on disk.
- Search a device's folders as fast as your own disks: the walk happens once and is kept in memory.

### Made to fit you

- **A settings window that covers everything:** fonts, text size, row height, accent and background colours, zebra rows, date and size formats, tree sections (Pinned, Recent, This PC, Devices, Places, Storage), the search bar's position, where new windows open, and more. It has its own search, and changes apply immediately.
- **Every action can be rebound,** with a main and an alternative key for each. Clashes are shown, and you can reset one key or all of them.
- **Windows remember their places.** Each numbered window comes back where you left it, with its tree width and columns, on the right monitor. The last session can reopen too.
- Light, dark or follow Windows, with the system accent colour.

### Portable and plain by design

- Settings, keys and commands are readable JSON in `%APPDATA%\Filo`. Edit them by hand while Filo runs, and it picks the changes up.
- Put a `settings.json` next to `filo.exe` and Filo becomes **portable**. Everything stays in that folder.

---

## New windows

Filo opens **new windows, not tabs**, and has **no split pane and no preview pane**. One folder per window, every window equal, all in one process. If you want two folders side by side, open two windows (`Ctrl+N`).

---

## Keys (defaults)

| Action | Keys |
| --- | --- |
| Go to a folder / find an action | `Ctrl+P` / `Ctrl+Shift+P` |
| Back / forward / up | `Alt+Left` / `Alt+Right` / `Alt+Up`, `Backspace` |
| Type a path | `Ctrl+L`, `Alt+D` |
| Search this folder | type, or `Ctrl+F`, `F3` |
| New window / close window | `Ctrl+N` / `Ctrl+W` |
| New folder | `Ctrl+Shift+N` |
| Rename / batch rename | `F2` / `Ctrl+Shift+R` |
| Edit properties | `Alt+Enter` |
| Cut / copy / paste / copy path | `Ctrl+X` / `Ctrl+C` / `Ctrl+V` / `Ctrl+Shift+C` |
| Delete / delete for good | `Delete` / `Shift+Delete` |
| Undo / redo | `Ctrl+Z` / `Ctrl+Y`, `Ctrl+Shift+Z` |
| Views: details / list / icons | `Ctrl+Shift+1` / `2` / `3` |
| Bigger / smaller thumbnails | `Ctrl+=` / `Ctrl+-` |
| Show or hide hidden items | `Ctrl+H` |
| Refresh | `F5` |
| Settings | `Ctrl+,` |

All of them can be changed under **Settings → Keys**.

---

## Getting started

1. Download `filo.exe` from [Releases](../../releases).
2. Run it. There's nothing to install.

**Requirements:** Windows 10 or 11, 64-bit.

---

## Built with

Filo is written in C++ on top of the Windows API, with its own written framework UI. Zip support uses [miniz](https://github.com/richgel999/miniz) (MIT). The full list of third-party code and licences is on the **About** page in Settings.

### Freeware

Filo is **free** for personal use. There are no ads, no trial period, no sign-up and no telemetry. Filo never connects to the internet on its own, even for update checks; it only touches the network folders you open. Don't take my word for it: watch it with your firewall or any network monitor, or use AI tools on Filo binaries to check any of those claims yourself.

**At work**
- Filo may be commercially licensed in the future to use at work. For now, the only allowed use is personal.

**You may**
- use Filo on as many computers of your own as you like;
- decompile Filo to analyze it;
- copy it and share the unmodified `filo.exe` with anyone, as long as you don't charge for it.

**You may not**
- sell Filo, or bundle it with something you sell, without permission;
- modify or repackage `filo.exe` or hand it out under another name;
- remove or change the About page or its third-party licence notices.

**No warranty. This is important.** Filo is provided "as is", without warranty of any kind. It copies, moves and deletes files, so keep backups of anything that matters. The author is not liable for lost data or any other damage that comes from using it.

Third-party code built into Filo keeps its own licence. The full list is on **Settings → About**.

Copyright © 2026 riozebratubo. All rights reserved.

<!-- TODO: licence -->
