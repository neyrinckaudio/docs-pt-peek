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
- **Device-aware mixing** — automatically adapts to the selected output device's channel count
- **Low latency** — files play directly from disk

## Output Device Selection

Use the device picker in the session browser header to select an output device. Available devices include:

- Built-in speakers/headphones
- USB audio interfaces
- Bluetooth audio devices
- Virtual audio devices (e.g., Pro Tools Audio Bridge)

The device list updates automatically when devices are connected or disconnected.
