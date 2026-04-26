# Audio Playback

PT Peek can play audio files and clips directly from the session browser.

## Inline Playback

Each audio file and clip row has a small waveform display with a play button. Click the play button to start playback. Click again to pause. The waveform shows a red playhead that tracks the current position.

- Click anywhere on the waveform to seek to that position
- Only one item plays at a time — starting a new item stops the previous one
- Waveform displays are cached after the first play, so subsequent views are instant

## Multi-Mono Playback

PT Peek automatically detects multi-mono file sets (e.g., `Drums.L.wav` + `Drums.R.wav`) and plays them together as a set. If your audio device has more than two channels, extra channels are routed to the device in SMPTE order.

Multi-mono channel detection supports these Pro Tools suffixes:

| Suffix | Channel |
|--------|---------|
| `.L` | Left |
| `.R` | Right |
| `.C` | Center |
| `.LFE` | Low Frequency Effects |
| `.Ls` | Left Surround |
| `.Rs` | Right Surround |
| `.Lss`, `.Rss` | Left/Right Side Surround |
| `.Ltf`, `.Rtf` | Left/Right Top Front (Atmos) |
| `.Ltr`, `.Rtr` | Left/Right Top Rear (Atmos) |

## Audio Engine

PT Peek uses macOS Core Audio for playback. This provides:

- **Direct channel routing** — each mono file routes to the corresponding output channel
- **Device-aware mixing** — automatically adapts to the system default output's channel count
- **Low latency** — files play directly from disk

## Output Device

PT Peek plays through your **system default audio output**. To change where playback is routed, change your default output device in **System Settings → Sound** (or by ++option++-clicking the volume icon in the menu bar).
