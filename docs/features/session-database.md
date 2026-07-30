# Session Database

!!! info "PT Peek Pro"
    The Session Database and [Multi-Session Search](multi-session-search.md) are PT Peek Pro features.

PT Peek Pro keeps a **session database** — a catalog of the Pro Tools sessions stored on your drives. Once a folder is being watched, PT Peek scans it for `.ptx` files, reads each session's metadata (session name, sample rate, bit depth, tracks, clips, audio files, plug-ins), and stores it locally so you can search across every session at once in [Multi-Session Search](multi-session-search.md) — without opening the files.

The **Session Database** window is where you tell PT Peek *which* drives and folders to catalog, and where you see what it has found.

Open it with **Window → Show/Hide Session Database** (++cmd+shift+d++). The same command hides it again when it's frontmost. The window remembers its size and position, and reopens at launch if it was open when you quit.

## Watch Locations

PT Peek never scans your whole system on its own. You add **watch locations** — a folder, or an entire volume — and only those are cataloged.

The window is split into two panes:

- **This Mac** (left) — every volume PT Peek knows about: your internal drive, connected external drives, and any drive you've previously added that is currently offline.
- **Watch Locations on "*volume*"** (right) — the folders being watched on the selected volume, each with its indexing status.

### Adding a watch location

1. Select a volume in the left sidebar.
2. Click **+** at the bottom of the right pane.
3. Choose a folder to watch — or select the volume itself to watch the whole drive.

Because you pick the folder yourself, macOS grants PT Peek access to it without a separate permission dialog. Scanning starts immediately in the background.

### Removing a watch location

Select it and click **−**, or right-click the row and choose **Remove Watch Location…**. PT Peek stops watching that location and drops its sessions from search — unless another watch location still covers them. **Nothing on disk is touched.**

To force a fresh scan of a location, right-click it and choose **Rescan Now**.

### Offline volumes

A drive that isn't connected stays in the list, marked **Offline**, and its sessions remain searchable — you can still find a session on a disconnected archive drive and see where it lives. To forget a drive entirely, select it and click **−** under the sidebar (or right-click it and choose **Remove Offline Volume…**). That removes the drive, its watch locations, and its indexed sessions.

## Status and Counts

Each watch location shows a status icon and a session count:

| Icon | State | Meaning |
|------|-------|---------|
| Green check | Indexed | Read successfully and up to date |
| Spinner | Scanning | A scan is in progress — the count reads *indexed / found* |
| Orange triangle | Partially accessible | PT Peek can read the folder, but macOS is blocking some items inside it. Click it for details and a list of the blocked items |
| Red lock | Blocked by privacy | macOS is blocking the location. Click **Grant Access…** |
| Gray drive | Offline | The volume isn't connected. Last known counts are shown |

The footer under the list summarizes the selected volume — for example, "3 watch locations • 412 sessions indexed".

### Session File Backups

Pro Tools writes auto-backups into a **Session File Backups** folder next to the session. PT Peek indexes those too, but counts them separately — a second line under the main count reads, for example, "1,204 backups". Real sessions are always indexed first, so useful results appear before the backups are worked through. Backups are hidden from search results unless you turn on **Include Session File Backups** in [Multi-Session Search](multi-session-search.md).

## Full Disk Access

Folders you add yourself are readable without any extra permission. But macOS protects some locations (Desktop, Downloads, other apps' data) and blocks them even inside a folder you chose — that's what the **Partially accessible** state means.

To index sessions anywhere on your system, grant PT Peek **Full Disk Access**:

1. Click **Open Settings…** in the window's header (or **Open Privacy Settings…** in a status popover).
2. In **System Settings → Privacy & Security → Full Disk Access**, turn on PT Peek.
3. Return to PT Peek and click **Recheck** in the status popover.

macOS gives no notification when you grant access, so the **Recheck** step is what makes PT Peek notice.

## Keeping Up to Date

Once a location is watched, PT Peek keeps it current on its own:

- **Live changes** — saving, adding, moving, or deleting a `.ptx` file inside a watch location updates the database automatically, within a few seconds.
- **Unchanged files are skipped** — a file is only re-read when its size or modification date changes, so rescans of a large drive are cheap.
- **Reconnecting a drive** — plugging a watched drive back in catches up on whatever changed while it was disconnected, rather than rescanning everything.
- **Background work** — scanning runs at low priority so it stays out of the way of Pro Tools and the rest of your system.

## Console

Click **Show Console** in the bottom bar to open a live log of what the indexer is doing: scans starting and finishing, file changes detected, drives mounting and unmounting. It has an **Auto-scroll** toggle plus **Copy** and **Clear** buttons. Click **Hide Console** to put it away.

## Report a Problem

If indexing behaves unexpectedly, click **Report A Problem…** in the bottom bar. This opens a bug report with a diagnostic attached: a snapshot of every drive and folder being watched, its access and index status, file counts, any blocked items, and the recent event log — so the behavior can be diagnosed without a lot of back-and-forth.
