# Supported Formats

## Session Files

| Extension | Format | Support |
|-----------|--------|---------|
| `.ptx` | Pro Tools Session (v10+) | Full preview and browsing |

!!! note
    PT Peek reads `.ptx` files only. Older `.ptf` and `.pts` formats are not supported. Template files (`.ptt`) are not supported.

## Audio Formats

Pro Tools sessions use the following audio formats:

| Format | Extensions | Multi-Mono |
|--------|-----------|------------|
| WAV | `.wav` | Yes |
| AIFF | `.aif`, `.aiff` | Yes |

## Multi-Mono Detection

PT Peek automatically groups multi-mono WAV files into stereo or surround sets based on filename suffixes:

**Stereo:** `.L` + `.R`

**Surround formats:**

- **LCR:** `.L` + `.R` + `.C`
- **5.1:** `.L` + `.R` + `.C` + `.LFE` + `.Ls` + `.Rs`
- **7.1:** `.L` + `.R` + `.C` + `.LFE` + `.Ls` + `.Rs` + `.Lss` + `.Rss`

**Atmos height channels:** `.Ltf`, `.Rtf`, `.Ltr`, `.Rtr`, `.Ltm`, `.Rtm`, `.Lts`, `.Rts`

## Track Types

PT Peek displays all Pro Tools track types:

| Type | Icon | Import Support |
|------|------|---------------|
| Audio | Track | Yes |
| Aux Input | Track | Yes |
| Master Fader | Track | Yes |
| VCA | Track | Yes |
| MIDI | Track | Limited |
| Instrument | Track | Yes |

## Import Requirements

For importing to Pro Tools:

- Pro Tools **2025.6** or later
- Session must be open
- Sample rates must match between the `.ptx` file and the Pro Tools session
- Audio files must be accessible on disk
