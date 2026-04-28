# Export Session Report

PT Peek can export a complete, printable session report as a multi-page PDF. This is useful for archiving, sharing session details with collaborators, or printing a reference document.

## How to Export

1. Open a `.ptx` file in a session browser window
2. Go to **File → Export Session Report…** (++cmd+p++)
3. Choose a save location and filename — PT Peek defaults to `<session> Report.pdf`
4. Click **Save**

The PDF is generated in the background and opens automatically in your default PDF viewer.

## What's in the Report

The report is a vector PDF that includes every section of the session, regardless of which sections are currently expanded or collapsed in the browser:

- **Session Setup** — sample rate, bit depth, audio format, start, length, pan depth, interleaved, timecode rate
- **Tracks** — name, type, format, comments, with color swatches and folder hierarchy preserved
- **Audio Files** — name, format, and full path (multi-mono files shown as `Drums.(L R).wav`)
- **Clips** — names and source files
- **Plugins** — separated into Active and Inactive groups
- **Memory Locations** — name, color, type, and reference

Each page after the first has a running header (**PT Peek Session Report**) and a page-number footer.
