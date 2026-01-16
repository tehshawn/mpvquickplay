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

### Option 1: Download Release

1. Download the latest `MKVQuickPlay.app.zip` from [Releases](../../releases)
2. Unzip and move `MKVQuickPlay.app` to `/Applications`
3. Launch the app
4. Grant **Accessibility** permission when prompted (required for hotkey detection)

### Option 2: Build from Source

```bash
git clone https://github.com/YOUR_USERNAME/MKVQuickPlay.git
cd MKVQuickPlay
xcodebuild -project MKVQuickPlay.xcodeproj -scheme MKVQuickPlay -configuration Release build
```

The built app will be in `~/Library/Developer/Xcode/DerivedData/MKVQuickPlay-*/Build/Products/Release/`

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

### "mpv not found" alert
Install mpv using `brew install mpv`

### Hotkey not working
1. Check that Accessibility permission is granted
2. Ensure Finder is the active application when pressing the hotkey

### No video plays
Make sure a supported video file is selected in Finder (not just highlighted in a preview pane)

## License

MIT License - feel free to use, modify, and distribute.

## Credits

- Uses [mpv](https://mpv.io/) for video playback
- Icon inspired by VLC media player
