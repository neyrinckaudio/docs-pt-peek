# Session Browser

When you open one or more `.ptx` files in PT Peek windows (via Open With, double-click, File → Open, or drag to dock), you get the full session browser. This provides the same information as the Quick Look preview, plus interactive features for playing audio files and clips and importing to Pro Tools.

## Sections

### Session Setup

A grid showing session parameters, similar to the Pro Tools Session Setup window:

- Sample Rate, Bit Depth, Audio Format
- Session Start, Length
- Pan Depth, Interleaved, Timecode Rate

### Overview

This represents the top area of the timeline:

- A **timeline view** — each clip is drawn as a colored rectangle matching its Pro Tools color, with tracks stacked vertically. Lanes are zebra-striped for easier scanning, and faint vertical **gridlines** align with the ruler. Clips that are selected elsewhere in the browser are highlighted in the Overview so you can see at a glance where they sit in the session.
- A pinned **track-name column** beside the timeline lanes — names stay in place as you pan or zoom the timeline horizontally and follow their lanes vertically. The column sizes itself to the lane height.
- **Tempo**, **Meter** (with change indicators), and a **ruler** — all shown above the timeline. The ruler supports display modes **Min:Sec**, **Timecode**, **Bars|Beats**, **Feet+Frames**, and **Samples**, defaulting to the session's Main Counter format.

The Session Setup and Overview sections are **pinned at the top** of the window. Only the lower sections (Tracks, Audio Files, Clips, Plugins, Memory Locations) scroll, so the Overview and ruler stay visible while you work below.

#### Overview Zoom and Pan

The Overview can be zoomed and panned to inspect a specific region of the timeline:

- **Horizontal zoom** — ++cmd++ ++"]"++ / ++cmd++ ++"["++ (also ++cmd+right++ / ++cmd+left++ in the View menu)
- **Vertical zoom** — ++ctrl+opt+up++ / ++ctrl+opt+down++ (also ++cmd+up++ / ++cmd+down++ in the View menu)
- **Reset zoom** — ++cmd+0++
- **Inline triangle buttons** in the Overview section header (Pro Tools-style) do the same thing.
- **Pan** with a two-finger trackpad swipe or scroll wheel over the Overview; slim scroll bars appear at the edges when you're zoomed in.

Zoom recenters around the active selection (selected clips, selected tracks, or the rectangle area). With no selection, it recenters around the middle of the visible Overview. The ruler beneath the Overview follows the zoom and pan in lockstep.

#### Overview Height

The Overview opens at a consistent height — up to 12 tracks tall — regardless of the session's track count. Drag the bottom edge to resize it; resizing changes **how many tracks are visible** rather than stretching the tracks themselves. Vertical zoom steps through fixed track heights so lane sizes stay predictable. Small sessions never leave empty space below the tracks.

#### Selecting in the Overview

- **Click a clip** in the Overview to select it (matches the row's behavior in the Clips section). ++cmd++-click toggles, ++shift++-click extends from the anchor.
- **Drag a rectangle** in the Overview to define an **Overview rectangle** — see [Filter by Overview Rectangle](#filter-by-overview-rectangle) below.
- When tracks are selected in the Tracks section, a light frame is drawn around their lanes in the Overview.
- **Auto-scroll to selection** — selecting a track (or one of its clips) in the Tracks section automatically scrolls the Overview to bring that track's lane into view.
- While a clip is playing inline, a thin accent-colored vertical line marks the playback position in the Overview.

### Tracks

A detailed list of every track in the session:

- **Color swatch** — matches the Pro Tools track color
- **Name** — track name (drag the column divider to resize)
- **Type** — Audio, Aux, Master Fader, VCA, MIDI, Instrument
- **Format** — Mono, Stereo, LCR, Quad, 5.0, 5.1, 7.1, etc.
- **Inserts** — plugin insert slots (A through J), hover for details
- **Comments** — track comments

Click a track to select it. Expand a track to see its clips.

#### Folder Tracks

Folder tracks are shown with their full hierarchy and are always expanded — nested tracks are visible at all times. PT Peek labels folders as **routing folders** or **basic folders** so you can distinguish their function at a glance.

### Audio Files

All audio files referenced by the session:

- **Name** — file name (drag the column divider to resize)
- **Format** — Mono, Stereo, LCR, 5.1, 7.1, and more (multi-mono files are grouped automatically)
- **Path** — file path on disk
- **Waveform** — inline waveform with play button (click to play)

Non-playable or unhandled audio file types (for example, certain video container formats) are labeled **Not Available** instead of showing a waveform.

### Clips

All clips in the session with their source audio files. Clips from multi-mono tracks are grouped together. The Name column is resizable.

### Plugins

Lists all plugins used in the session, separated into Active and Inactive groups.

### Memory Locations

Lists all locations with name and color, plus a **Start** column showing the marker's position. The Start column is rendered in whichever format the Overview ruler is currently showing (Min:Sec, Timecode, Bars|Beats, Feet+Frames, or Samples) — change the ruler format and the column updates in lockstep. Non-marker locations (selections and other types) leave the column blank.

## Toolbar

Each session browser window has a title-bar toolbar with:

- **Open with Pro Tools** — opens the `.ptx` file directly in Pro Tools
- **Refresh** (++cmd+r++) — re-reads the session file from disk
- **Split View toggle** — see [Split View](#split-view) below
- **Search field** — see [Search and Filter](#search-and-filter) below
- **Scope picker** — limits the search to a single section

## Split View

Split View shows the Overview and the session lists side by side instead of stacked. Toggle it any of these ways:

- **View → Switch to Split/Single Column** (++cmd+opt+l++)
- The **Split View button** in the window's toolbar
- The **button in the Quick Look preview's header** (for the Quick Look version)

A draggable divider between the two panes lets you pick how much room each side gets. Each window remembers its own layout choice, and the setting persists per file.

## Search and Filter

A search field in the toolbar filters the **Tracks**, **Audio Files**, and **Clips** sections by name. Press ++cmd+f++ to focus the field.

- The scope picker next to the field limits the search to a single section (**All** / **Tracks** / **Audio Files** / **Clips**).
- While filtering, each section title reads **"(N of M)"** to show how many items match out of the total.
- Any section that has matches auto-expands so the results are visible without manually disclosing it.
- When a clip name matches, the track that contains it also surfaces, along with its parent folders, so the folder tree stays coherent.
- Click a row to hand keyboard focus back to that section — arrow keys then move the selection instead of editing the search text.

## Filter by Overview Rectangle

Drag a rectangle inside the Overview to narrow the Tracks, Audio Files, and Clips sections to just what falls inside the rectangle:

- Drag to define the rectangle. Tracks outside its vertical span hide; clips outside its horizontal span hide.
- When a track is expanded, its inner clip sub-list also follows the rectangle.
- Arrow-key navigation walks only the rows that are actually visible (including inner clips).
- Search filtering still applies on top of the rectangle.
- **Click** (without dragging) in the Overview — or choose **Edit → Clear Overview Selection** — to clear the rectangle.

The Quick Look preview also supports this — drag inside its Overview to filter, click to clear.

!!! tip "Filter-aware import"
    When you import tracks to Pro Tools with a rectangle and/or search active, only the clips that are currently visible are imported. What you see is what you get. See [Import to Pro Tools](import.md).

## Per-File Persistence

Each `.ptx` file's window remembers:

- Window size and position
- Overview zoom (horizontal and vertical) and height
- Overview rectangle
- Which sections are expanded or collapsed
- Name-column widths

These settings are restored the next time you open the same file, across app launches.

## Reveal in Finder

Right-click any audio file or clip row to **Reveal in Finder**. This works for files that are online (accessible on disk) and shows their location in a Finder window.

## Selection

PT Peek supports Finder-style multi-selection:

- **Click** — select one item
- ++cmd++ **+ Click** — toggle an item in the selection
- ++shift++ **+ Click** — extend selection to include range
- **Arrow keys** — navigate up/down within a section

Selection is scoped to one section at a time. Clicking in a different section clears the previous selection.
