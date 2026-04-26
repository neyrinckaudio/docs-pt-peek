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

- A **universe view** similar to the Pro Tools universe — each clip is drawn as a colored rectangle matching its Pro Tools color, with tracks stacked vertically. Clips that are selected elsewhere in the browser are highlighted in the universe so you can see at a glance where they sit in the session.
- A **ruler** above the universe with selectable display modes: **Min:Sec**, **Timecode**, **Bars|Beats**, **Feet+Frames**, and **Samples**. The ruler defaults to the session's Main Counter format.
- **Tempo** and **Meter** (including change indicators)

### Tracks

A detailed list of every track in the session:

- **Color swatch** — matches the Pro Tools track color
- **Name** — track name
- **Type** — Audio, Aux, Master Fader, VCA, MIDI, Instrument
- **Format** — Mono, Stereo, LCR, Quad, 5.0, 5.1, 7.1, etc.
- **Inserts** — plugin insert slots (A through J), hover for details
- **Comments** — track comments

Click a track to select it. Expand a track to see its clips.

#### Folder Tracks

Folder tracks are shown with their full hierarchy and are always expanded — nested tracks are visible at all times. PT Peek labels folders as **routing folders** or **basic folders** so you can distinguish their function at a glance.

### Audio Files

All audio files referenced by the session:

- **Name** — file name
- **Format** — Mono, Stereo, LCR, 5.1, 7.1, and more (multi-mono files are grouped automatically)
- **Path** — file path on disk
- **Waveform** — inline waveform with play button (click to play)

### Clips

All clips in the session with their source audio files. Clips from multi-mono tracks are grouped together.

### Plugins

Lists all plugins used in the session, separated into Active and Inactive groups.

### Memory Locations

Lists all locations with name and color.

## Toolbar

Each session browser window has a title-bar toolbar with:

- **Open with Pro Tools** — opens the `.ptx` file directly in Pro Tools
- **Refresh** (++cmd+r++) — re-reads the session file from disk

## Reveal in Finder

Right-click any audio file or clip row to **Reveal in Finder**. This works for files that are online (accessible on disk) and shows their location in a Finder window.

## Selection

PT Peek supports Finder-style multi-selection:

- **Click** — select one item
- ++cmd++ **+ Click** — toggle an item in the selection
- ++shift++ **+ Click** — extend selection to include range
- **Arrow keys** — navigate up/down within a section

Selection is scoped to one section at a time. Clicking in a different section clears the previous selection.
