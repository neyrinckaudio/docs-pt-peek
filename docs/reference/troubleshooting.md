# Troubleshooting

Before trying the steps below, go to **Help → Troubleshooting** in the PT Peek app. This runs a diagnostic check and can detect common problems automatically.

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

1. **Check that iLok License Manager is installed** — PT Peek requires iLok License Manager to verify your license. If it is not installed, download it from [ilok.com](https://www.ilok.com) and install it.

2. **Make sure iLok License Manager is running** — open Activity Monitor and search for "iLok". The iLok License Manager service should be running. If not, launch iLok License Manager from your Applications folder.

3. **Verify your license is activated** — open iLok License Manager and confirm that your PT Peek license appears and is activated to your computer (not just deposited to your iLok account).

4. **Check the PT Peek helper** — open Activity Monitor and search for "PT Peek Helper". It should be running. If not:
    - Go to **System Settings → General → Login Items**
    - Ensure PT Peek is enabled
    - Quit and relaunch PT Peek

If the issue persists, visit [neyrinck.com/support](https://neyrinck.com/support) for further assistance.

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
3. Report the issue with the crash log at [neyrinck.com/support](https://neyrinck.com/support)

