# Import to Pro Tools

PT Peek can import tracks, audio files, and clips directly into a running Pro Tools session.

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

- A new track in Pro Tools with the same name, type, and format
- All audio files used by the track's clips are imported to the clip list
- Clips are created with the correct source offset and length
- Clips are spotted at their original timeline positions

### Audio Files

Importing audio files adds them to the Pro Tools clip list. No tracks are created.

### Clips

Importing clips:

1. Imports the associated audio files to the clip list
2. Creates sub-clips with the correct offset and length in the source file

No tracks are created and clips are not placed on the timeline.

## Stereo and Multi-Mono

PT Peek handles stereo tracks with multi-mono source files correctly:

- Each mono file is imported separately
- Clips reference the mono files with the correct channel routing (Left/Right)
- The track is created with the appropriate stereo format

## Error Handling

If an import fails, the dialog shows the error message from Pro Tools. Common issues:

- **"Cannot connect"** — Pro Tools is not running or not responding
- **"Version not supported"** — Pro Tools is older than 2025.6
- **"No session open"** — open or create a session in Pro Tools
- **"Sample rate mismatch"** — change the Pro Tools session sample rate to match
