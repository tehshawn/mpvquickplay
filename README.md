# MKV QuickPlay

A lightweight macOS menu bar app for quick video preview using mpv. Select a video file in Finder and press **Control+Space** to instantly preview it.

## Features

- **Instant Preview**: Press `Control+Space` to preview the selected video in Finder
- **Quick Navigation**: Use `Up/Down` arrow keys to jump between videos in the same folder
- **Toggle Playback**: Press `Control+Space` again to close, or press `Escape`
- **Minimal UI**: Runs quietly in the menu bar with no Dock icon
- **Native Performance**: Uses mpv for fast, high-quality video playback

## Requirements

- macOS 13.0 (Ventura) or later
- **mpv** media player (required)

### Installing mpv

Install mpv using Homebrew:

```bash
brew install mpv
```

## Installation

### Option 1: Build from Source (Recommended)

Due to macOS security restrictions, the app must be built locally to work properly. Pre-built releases may not be able to detect hotkeys on your Mac.

**Requirements**: Xcode (free from App Store) and Command Line Tools

```bash
# Clone the repository
git clone https://github.com/tehshawn/mkvquickplay.git
cd mkvquickplay

# Build the app
cd macos
xcodebuild -project MKVQuickPlay.xcodeproj -scheme MKVQuickPlay -configuration Release build

# Copy to Applications
cp -R ~/Library/Developer/Xcode/DerivedData/MKVQuickPlay-*/Build/Products/Release/MKVQuickPlay.app /Applications/

# Launch
open /Applications/MKVQuickPlay.app
```

### Option 2: Download Release (May Not Work)

> **Note**: Pre-built releases may show "Hotkey Detection Failed" on macOS 26+ due to stricter security requirements for unsigned apps. If this happens, use Option 1 instead.

1. Download the latest `MKVQuickPlay.app.zip` from [Releases](../../releases)
2. Unzip and move `MKVQuickPlay.app` to `/Applications`
3. Launch the app
4. Grant **Accessibility** permission when prompted

## Usage

1. Launch **MKV QuickPlay** (it appears in your menu bar)
2. In **Finder**, select a video file (MKV, AVI, WebM, MP4, M4V, or MOV)
3. Press `Control+Space` to preview
4. Use `Up/Down` arrows to navigate to previous/next video
5. Press `Escape` or `Control+Space` to close

## Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| `Control+Space` | Open/close video preview |
| `Up Arrow` | Previous video in folder |
| `Down Arrow` | Next video in folder |
| `Escape` | Close preview |

## Permissions

MKV QuickPlay requires two permissions:

1. **Accessibility**: For detecting global hotkeys (Control+Space). Grant via:
   - System Settings > Privacy & Security > Accessibility

2. **Automation**: For querying Finder selection. Grant when prompted on first use.

## Supported Formats

- MKV (Matroska Video)
- AVI
- WebM
- MP4
- M4V
- MOV

## Troubleshooting

### "Hotkey Detection Failed" alert
This happens on macOS 26+ when running a pre-built (unsigned) app. **Solution**: Build from source using Option 1 above. When you build locally, macOS trusts the app.

### "mpv not found" alert
Install mpv using `brew install mpv`

### Hotkey not working (no alert)
1. Check that Accessibility permission is granted in System Settings > Privacy & Security > Accessibility
2. Try removing MKV QuickPlay from the Accessibility list, quit the app, relaunch, and grant permission again
3. Ensure Finder is the active application when pressing the hotkey

### No video plays
Make sure a supported video file is selected in Finder (not just highlighted in a preview pane)

## License

MIT License - feel free to use, modify, and distribute.

## Credits

- Uses [mpv](https://mpv.io/) for video playback
- Icon inspired by VLC media player
