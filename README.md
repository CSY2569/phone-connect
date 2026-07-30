# Phone Connect

A [Noctalia](https://docs.noctalia.dev) v5 plugin for controlling paired phones via **KDE Connect**.

## Features

- **Device status** — battery level, charging state, network type (5G/LTE/…), pairing status
- **Quick actions** — ring, ping, send clipboard, share text/files/URLs, SMS, SFTP file browser
- **Media control** — play/pause/skip/seek, album art, now-playing info (MPRIS)
- **Customization** — per-device image, display name alias, panel placement (attached / floating / below-widget)
- **Language** — English & Simplified Chinese, switchable in settings

## Requirements

- `kdeconnect` (`kdeconnectd` + `kdeconnect-cli`)
- `gdbus` (from glib2)
- `sshfs` (for phone file browsing)
- KDE Connect app on your phone (Android / iOS)

## Install

```bash
# Clone the repo as a local plugin source
mkdir -p ~/noctalia-plugins
git clone https://github.com/<your-org>/phone-connect ~/noctalia-plugins/phone-connect

# Register the path source in Noctalia
noctalia msg plugins source add phone-connect path ~/noctalia-plugins

# Reload and enable
noctalia msg config-reload
noctalia msg plugins enable icefish/phone-connect
```

Then add the bar widget and control-center tile from Settings.

## Settings

| Setting | Description |
|---------|-------------|
| State Update Interval | Seconds between device refreshes |
| Show Charging Fill | Highlight the bar widget when charging |
| Show Clipboard Action | Quick clipboard-send button in panel |
| Device Image | Custom image for the selected device |
| Device Alias | Custom display name (default: Your-Phone) |
| Language | English / 简体中文 |
| Panel Placement | Attached to bar / Floating center / Below widget |
| Max Recent Images | Number of recent images (future) |
| Show Ongoing Media | Show media info section (future) |

## License

MIT
