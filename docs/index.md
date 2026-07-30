# PT Peek User Guide

**PT Peek** is a macOS app that gives you instant visibility into your Pro Tools sessions — tracks, audio files, clips, plugins, and more. Preview and browse Pro Tools session files (`.ptx`) directly from the Finder — without opening Pro Tools. Reveal online files in Finder, see offline paths, and if Pro Tools is open, you can quickly import basic track data, files, and clips.

## What PT Peek Does

- **Quick Look Preview** — press Space on any `.ptx` file in Finder to see session details instantly
- **Session Browser Windows** — open `.ptx` files to explore tracks, clips, audio files, plugins, and much more
- **Audio Playback** — play back audio files and clips, interleaved and multi-mono, through your system's default audio output
- **Import to Pro Tools** — import basic track data, clips, and audio files directly into a running Pro Tools session
- **Export Session Report** — save a multi-page PDF of the full session for archiving or sharing
- **Session Database** (Pro) — catalog the sessions on your drives so they can be searched without opening them
- **Multi-Session Search** (Pro) — find sessions across your whole library by session, track, clip, audio file, or plug-in name

## What's New in 1.4 Beta { #whats-new-in-14 }

PT Peek 1.4 adds PT Peek Pro — instead of looking at one session at a time, you can now search across every session on your drives:

- **[Session Database](features/session-database.md)** (Pro) — add drives and folders as **Watch Locations** and PT Peek catalogs the Pro Tools sessions inside them in the background, then keeps the catalog current as you save, move, and delete sessions. The new window (**Window → Show/Hide Session Database**, ++cmd+shift+d++) shows exactly what's indexed, what's offline, and what macOS is blocking, with a live console and a one-click problem report.
- **[Multi-Session Search](features/multi-session-search.md)** (Pro) — search your whole session library by **session, track, clip, audio file, or plug-in name** (**Window → Show/Hide Multi-Session Search**, ++cmd+shift+s++). Results are instant — no session files are opened and Pro Tools never launches.
- **See what matched** — expand a result to list only the tracks, clips, audio files, or plug-ins that matched, without opening the session.
- **Session preview beside the results** — selecting a result shows the full session next to the list, with the matched track, clip, or audio file revealed in place — where you can play it back, just like a session browser window. Double-click (or press ++enter++) to open it in a window of its own.
- **Narrow the search** — limit a search to a volume or folder with the **Locations** chips, add **criteria rows** for sample rate, bit depth, track count, track type, frame rate, modified date, and more, and include or exclude Pro Tools **Session File Backups**.

## What's New in 1.2

PT Peek 1.2 sharpens the Overview and makes large-track-count sessions easier to work with — a new side-by-side layout, track names shown on the timeline, and a cleaner, more predictable Overview:

- **Split View** — new layout option with the Overview and the session data side by side so you can better view sessions with a lot of tracks. Toggle the layout with the new toolbar button or with the new menu item **View → Switch to Split/Single Column** (++cmd+opt+l++).
- **Overview Track Names** — now the Overview shows track names at the left. The track name font adjusts to the lane height: none, mini, regular. 
- **Overview Refresh** — added faint vertical grid lines aligned to the ruler and zebra-striped lanes for easier scanning.
- **Overview Auto-Scroll** — selecting a track (or one of its clips) in the Tracks section scrolls the Overview to bring that track into view.
- **Overview Resize Height** — previously, adjusting the Overview height would alter the track height. Now, it only changes how many tracks are visible. Use the vertical zoom to adjust track height.
- **Quick Look Overview** — zoom and height persist between previews.

## What's New in 1.1

PT Peek 1.1 makes the Overview the center of navigation, and adds search, filtering, and per-file persistence:

- **Zoomable / pannable Overview** — horizontal and vertical zoom with Pro Tools-style shortcuts, scroll bars, and inline triangle buttons
- **Adjustable Overview height** — drag the bottom edge of the Overview to grow or shrink it
- **Overview rectangle selection** — drag in the Overview to filter Tracks, Audio Files, and Clips to just what's inside
- **Pinned Session Setup and Overview** — they stay visible at the top while the lower sections scroll
- **Toolbar search and scope picker** (++cmd+f++) — filter Tracks, Audio Files, and Clips by name; matching sections auto-expand and show "N of M"
- **Resizable Name columns** in Tracks, Audio Files, and Clips
- **Overview playback indicator** — a vertical line tracks inline playback through the Overview
- **Waveform double-click** to start playback on audio file and clip rows
- **Option-click a section header** to open or close all sections (Tracks, Audio Files, Clips, Plugins, Memory Locations) at once
- **Option-click a track disclosure** to expand or collapse every track in the Tracks section at once
- **Filter-aware import** — imports only the clips currently visible after filtering
- **Per-file persistence** — each `.ptx` window remembers its size, zoom, rectangle, open sections, and column widths
- **Quick Look gets the same Overview controls** — zoom buttons, height drag, rectangle filtering

A **What's New** dialog appears the first time you launch 1.1 with a short summary of these changes.

## Requirements

- macOS 12.0 (Monterey) or later
- Pro Tools 10 or later .ptx files
- Pro Tools 2025.6 or later (for Import to Pro Tools features)
- iLok account (for license activation)

## Quick Start

1. [Install PT Peek](getting-started/installation.md)
2. [Launch the app](getting-started/first-launch.md) to register the Quick Look extension
3. Select any `.ptx` file in Finder, press ++space++ to preview it
4. To open a full session browser window, do any of the following:
    - Right-click the file → **Open With → PT Peek**
    - In PT Peek, use **File → Open…**
    - Drag one or more `.ptx` files onto the PT Peek icon in the Dock
