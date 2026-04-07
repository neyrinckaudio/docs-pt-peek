# First Launch

After installing PT Peek, launch it once to register the Quick Look extension with macOS.

## What Happens on First Launch

1. **Quick Look extension registers** — macOS discovers the PT Peek Quick Look extension and enables it for `.ptx` files
2. **License is verified** — PT Peek checks your license status
3. **Welcome screen appears** — shows key features and how to get started

On macOS 13 (Ventura) and later, you may see a notification that "PT Peek added items that can run in the background." This is normal — PT Peek needs a background service for license verification. Make sure it is enabled in **System Settings → General → Login Items & Extensions**.

On macOS 12 (Monterey), you can find it in **System Preferences → Users & Groups → Login Items**.

## Activate Your License

!!! tip "Try before you buy"
    You can download a demo session from **File → Download Demo Session…** to explore PT Peek with full functionality before activating a license.

If you haven't already activated your PT Peek license, you can do it now:

1. Go to **Help → Activate License…**
2. Enter your iLok Login ID and click **Sign in with iLok**
3. Sign in with your iLok credentials in the activation window
4. Follow the prompts to activate the license to your computer

See [License Activation](../features/activation.md) for more details.

!!! tip "You only need to launch PT Peek once"
    After the first launch, the Quick Look extension works in Finder even when PT Peek is not running. Your license is verified automatically.

## Verifying Quick Look

After launching PT Peek:

1. Open Finder and navigate to a folder containing `.ptx` files
2. Select a `.ptx` file
3. Press ++space++ to preview
4. You should see the session's setup information, tracks, and more

If the preview doesn't appear, see [Troubleshooting](../reference/troubleshooting.md).

## Opening Sessions

There are several ways to open `.ptx` files with PT Peek:

- **Quick Look** — select the file in Finder and press ++space++
- **Open With** — right-click the file(s) → Open With → PT Peek
- **Drag and drop** — drag one or more `.ptx` files onto the PT Peek icon in the Dock
- **File menu** — use File → Open… in PT Peek
