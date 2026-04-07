# Troubleshooting

## Quick Look Preview Not Showing

**Symptom:** Pressing ++space++ on a `.ptx` file shows the default icon instead of the PT Peek preview.

**Solutions:**

1. **Launch PT Peek once** — macOS registers the Quick Look extension on first launch
2. **Check System Settings** — go to **Privacy & Security → Extensions → Quick Look** and ensure PT Peek is enabled
3. **Reset Quick Look** — open Terminal and run:
   ```bash
   qlmanage -r
   ```
4. **Re-register the app** — open Terminal and run:
   ```bash
   /System/Library/Frameworks/CoreServices.framework/Versions/Current/Frameworks/LaunchServices.framework/Versions/Current/Support/lsregister -f -R -trusted /Applications/PT\ Peek.app
   ```

## License Not Detected

**Symptom:** The app shows "License not found" even though you have a valid license.

**Solutions:**

1. **Check the helper** — open Activity Monitor and search for "PT Peek Helper". It should be running. If not:
    - Go to **System Settings → General → Login Items**
    - Ensure PT Peek is enabled
    - Quit and relaunch PT Peek
2. **Reset background task management** — if the helper won't start:
   ```bash
   sudo sfltool resetbtm
   ```
   Then quit and relaunch PT Peek.
3. **Check Keychain** — run from Terminal:
   ```bash
   "/Applications/PT Peek.app/Contents/MacOS/PT Peek" --check-keychain
   ```
   This shows whether the secret key and token are present.
4. **Clear and restart** — if all else fails:
   ```bash
   "/Applications/PT Peek.app/Contents/MacOS/PT Peek" --clear-keychain
   "/Applications/PT Peek.app/Contents/MacOS/PT Peek" --unregister-helper
   ```
   Then relaunch PT Peek.

## Import to Pro Tools Fails

**"Cannot connect to Pro Tools"**

- Make sure Pro Tools is running
- Pro Tools must be version 2025.6 or later

**"No session open"**

- Open or create a session in Pro Tools before importing

**"Sample rate mismatch"**

- The Pro Tools session sample rate must match the `.ptx` file
- Change the Pro Tools session sample rate, or open a session that matches

**"Version not supported"**

- Import requires Pro Tools 2025.6 or later
- Update Pro Tools to the latest version

## Audio Playback Issues

**No sound**

- Check the output device picker in the session browser header
- Make sure the selected device is not muted
- Verify the audio files are accessible on disk (not offline)

**Wrong channels / panning**

- PT Peek routes mono files directly to output channels
- For multi-mono, ensure files have the correct channel suffixes (`.L`, `.R`, etc.)

## App Crashes or Freezes

If PT Peek becomes unresponsive:

1. Force quit: ++cmd+option+esc++ → select PT Peek → Force Quit
2. Check Console.app for crash logs under PT Peek
3. Report the issue with the crash log

## Debug Commands

These can be run from Terminal for advanced troubleshooting:

```bash
APP="/Applications/PT Peek.app/Contents/MacOS/PT Peek"

# Check license token status
"$APP" --check-keychain

# Delete token file (keeps secret key)
"$APP" --delete-token

# Delete both secret key and token
"$APP" --clear-keychain

# Unregister the background helper
"$APP" --unregister-helper
```
