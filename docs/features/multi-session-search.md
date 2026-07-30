# Multi-Session Search

!!! info "PT Peek Pro"
    Multi-Session Search and the [Session Database](session-database.md) are PT Peek Pro features.

Multi-Session Search answers questions that span your whole session library: *Which sessions use that vocal take? Where did I use Auto-Tune? Which 96 kHz sessions have a track named "Gtr Solo"?* It searches the [Session Database](session-database.md), so results come back instantly — no session files are opened and Pro Tools never has to launch.

Open it with **Window → Show/Hide Multi-Session Search** (++cmd+shift+s++). The same command hides it again when it's frontmost. The window remembers its size, position, and your last search, and reopens at launch if it was open when you quit.

!!! note "Add watch locations first"
    Search only covers what's in the database. If results come back empty, open the [Session Database](session-database.md) window and add the folders or drives that hold your sessions.

## The Window

The window is a search bar across the top, with results on the left and a **preview** of the selected session on the right. Drag the divider between them to set how much room each side gets; the position is remembered.

### Search bar

- **Type menu** — what you're searching for: **Session Name**, **Track Name**, **Clip Name**, **File Name**, or **Plug-In Name**. A session matches when *any* of its items of that type match, so "Track Name contains vox" finds every session containing a track named "Vox Comp", "vox dbl", and so on.
- **Search field** — type a word or the start of one. Results update as you type.
- **Include Session File Backups** — off by default, so Pro Tools auto-backups stay out of your results. Turn it on when you're hunting for an older version of a session.

### Locations

The **Search:** line below the search bar limits the search to part of your library:

- **This Mac** is always present and searches everything in the database.
- Use the **Locations** pull-down to add a chip for a **volume** (any drive PT Peek has indexed, online or offline) or a **folder** (**Folder…** opens a picker).
- Click a chip to search that location. Only one is active at a time.
- To remove a chip, right-click it and choose **Remove**, or use **Locations → Remove**.

Your chips persist between launches, so the drives and folders you search often stay one click away.

### Criteria rows

For anything more specific, click the **+** at the right of the **Search:** line to add a criteria row. Each row is *field · operator · value*, and results must match **all** of the rows plus whatever is in the search field. Use the **+** and **−** on a row to add or remove rows.

| Field | Operators | Example |
|-------|-----------|---------|
| Session name | contains / is / is not | contains `mix` |
| Track name | contains / is / is not | is `Kick In` |
| Track type | is / is not | is `VCA` |
| Plug-in name | contains / is / is not | contains `Auto-Tune` |
| Clip name | contains / is / is not | contains `take 3` |
| Audio file name | contains / is / is not | contains `Vox_01` |
| Sample rate | is / is at least / is at most | is `96000` |
| Bit depth | is / is at least / is at most | is at least `24` |
| Track count | is / is at least / is at most | is at least `50` |
| Frame rate | contains / is / is not | is `23.976` |
| Modified within | *n* days | within `30` days |
| Volume | online / offline | online |

Track, clip, plug-in, and audio-file criteria match at the session level — a session qualifies if *any* of its tracks (or clips, plug-ins, files) matches.

## Results

Results are listed by **Session Name** and **Path**, with a count at the bottom of the list. Sessions on a disconnected drive still appear, dimmed.

When you search by Track, Clip, Audio File, or Plug-In name, each session row has a disclosure triangle. Expanding it lists **only the items that matched** — so you can see which tracks or clips triggered the hit without opening the session.

| Action | Result |
|--------|--------|
| Click a row | Select it — the preview on the right jumps to that session and highlights the matched item |
| Double-click a row, or press ++enter++ | Open the session in a full PT Peek window |
| ++right++ | Expand the session (show matched items) |
| ++left++ | Collapse, or jump from a matched item back to its session |
| ++up++ / ++down++ | Move through sessions and their matched items |
| Right-click | **Open in PT Peek** or **Reveal in Finder** |

## Preview Pane

Selecting a result shows that session in the right-hand pane — the same view as a [session browser](session-browser.md) window, with the Overview, Session Setup, Tracks, Audio Files, Clips, Plugins, and Memory Locations. Selecting a matched track, clip, or audio file in the results reveals and highlights it in the preview, so you can see where it sits in the session before deciding to open it.

**Playback happens here.** The results list itself doesn't play audio — to hear a match, select it, then play it from its waveform in the preview pane, exactly as you would in a session browser window. See [Audio Playback](audio-playback.md).

Sessions on an offline drive show their name and path, but can't be expanded, previewed, or played — reconnect the drive to work with them.
