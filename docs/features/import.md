# Import to Pro Tools

PT Peek can import basic track, file, and clip data into an open Pro Tools session (Pro Tools 2025.6 or later).

1. **Tracks** - Track (type, name, and color), audio files, and clips spotted to the track.
2. **Audio Files** - Optionally copied. Optionally sample rate converted.
3. **Clips** - Individual clips, not organized as region groups.

## Requirements

- **Pro Tools 2025.6 or later** must be running
- A session must be open in Pro Tools
- The session sample rate must match the `.ptx` file's sample rate
- Audio files must be accessible on disk (online)

## How to Import

### From the Menu

1. Select one or more items (tracks, audio files, or clips)
2. Use **File → Import to Pro Tools…** or press ++cmd+shift+i++

### From the Context Menu

1. Select one or more items
2. Right-click → **Import to Pro Tools…**

### From the Track Row

Right-click any track to import it and its clips.

## Import Dialog

Before importing, PT Peek shows a dialog that verifies:

1. **Connection** — can PT Peek connect to Pro Tools?
2. **Version** — is Pro Tools 2025.6 or later?
3. **Session** — is a session open? Shows the session name.
4. **Sample Rate** — does the Pro Tools session match the file's sample rate?

If all checks pass, you see a list of items to import with a **Cancel** / **Import** button.

## What Gets Imported

### Tracks

Importing a track creates:

- A new track in Pro Tools with the same name, type, color, and format
- All audio files used by the track's clips are imported to the clip list
- Clips are created with the correct source offset and length
- Clips are spotted at their original timeline positions
- Clips are not combined into groups

### Audio Files

Importing audio files adds them to the Pro Tools clip list. No tracks are created. Files are copied to the destination session's Audio Files directory. If the destination sample rate is different from the source, sample rate conversion will be applied.

### Clips

Importing clips:

1. Imports the associated audio files to the clip list
2. Creates sub-clips with the correct offset and length in the source file

No tracks are created and clips are not placed on the timeline.

## Interleaved and Multi-Mono

PT Peek handles multichannel tracks and files for interleaved and multi-mono cases:

- Tracks are created with the appropriate stem format
- Source audio files can be interleaved or multi-mono
- Audio files that are copied will match the destination session's session setup: interleaved or multi-mono
- 

## Error Handling

If an import fails, the dialog shows the error message from Pro Tools. Common issues:

- **"Cannot connect"** — Pro Tools is not running or not responding
- **"Version not supported"** — Pro Tools is older than 2025.6
- **"No session open"** — open or create a session in Pro Tools
- **"Sample rate mismatch"** — change the Pro Tools session sample rate to match
