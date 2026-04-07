# Quick Look Preview

PT Peek adds a Quick Look extension for Pro Tools session files (`.ptx`). Press ++space++ on any session file in Finder to see a preview without opening Pro Tools.

## What the Preview Shows

The Quick Look preview displays:

- **Session Setup** — sample rate, bit depth, session length, start time
- **Overview** — universe showing all tracks and clip positions, tempo and meter
- **Tracks** — list of all tracks with color, type, format, and plugin inserts
- **Plugins** — active and inactive plugins used in the session
- **Audio Files** — all audio files referenced by the session and the path
- **Clips** — all clips (colored) with their source audio files
- **Locations** — all memory location names along with a color

## Sections

Each section can be expanded or collapsed by clicking its header. PT Peek remembers which sections you had open, so the layout persists across previews.

## Licensed vs. Unlicensed

Without a license, the preview shows:

- **Session Setup** and **Overview** — full detail
- **Tracks, Plugins, Audio Files, Clips** — grayed out
- Section headers with counts are always visible

With a valid license, all sections show full detail.

## Workflow Tips

1. **Open only the sections you need** — expand just the section relevant to what you're looking for. PT Peek remembers your layout, so the next session you preview will show the same sections open, letting you zero in on the info you care about.

2. **Browse sessions in Finder** — use Finder's search to find `.ptx` files, then press ++space++ to open a Quick Look preview. Use the ++up++ and ++down++ arrow keys to move through your search results while the preview stays open, making it easy to scan through sessions and find the one you're looking for.

## Demo Session

If you don't have a license yet, you can try PT Peek with a built-in demo session that unlocks full functionality — no license or iLok account required.

### Downloading the Demo Session

1. Launch the PT Peek app
2. Go to **File → Download Demo Session…**
3. A `.zip` file will download. Double-click it to expand the full session folder.

### Previewing the Demo Session

1. Open the expanded session folder in Finder
2. Select the `.ptx` file
3. Press ++space++ to preview — all sections will display with full detail

### Important

!!! warning "Do not rename or modify the demo session"
    The demo session file name and contents must not be altered. PT Peek identifies the demo session by its original name and data — if either is changed, it will no longer be recognized and the unlicensed preview restrictions will apply.
