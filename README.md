# TechStream
Lightweight LAN Media Streaming for Windows

TechStream is a **portable LAN media server** designed for simple, fast streaming of local media libraries without cloud services.

Stream your media to any device on your network.  
No cloud. No accounts. No tracking. Just local streaming.

---

## Download

Download the latest release from the GitHub Releases page:

https://github.com/ablestudio-dev/techstream/releases

Extract the ZIP file and run:

```
TechStream.exe
```

No installer required.

---

## Overview

TechStream streams local media folders or M3U playlists over LAN using a built-in HTTP server.

Version **3.x** introduces the **Persistent M3U Library system**, allowing multiple playlists to be hosted, browsed, and streamed through the upgraded built-in web interface while maintaining deterministic hash-based streaming for reliable resume behavior.

---

## Features

- Stream local video files over LAN
- Built-in HTTP server (Kestrel)
- Byte-range streaming (seeking works in VLC)
- Deterministic hash-based streaming (`/stream/{hash}`)
- Automatic M3U playlist generation
- Persistent M3U playlist library
- Playlist Manager for loading and organizing playlists
- Host multiple playlists simultaneously
- Resume-safe playlist switching
- Embedded browser video playback in the default web interface
- Upgraded built-in web interface
- Optional custom web interface
- Portable (no installer required)

---

## Quick Start

1. Extract the release ZIP file.
2. Run **TechStream.exe**.
3. Select a media folder or load an M3U playlist.
4. Click **Start Server**.
5. On another device, open **VLC**.
6. Go to **Media → Open Network Stream**.
7. Enter:

```
http://YOUR-LAN-IP:5050/playlist.m3u
```

Example:

```
http://192.168.1.42:5050/playlist.m3u
```

---

## Playlist Library

TechStream supports multiple playlist modes.

### Folder Mode
- Indexed files become the active playlist.
- Natural sorting is applied.

### M3U Mode
- Loaded playlists become canonical file lists.
- Playlist order is preserved exactly.

### Persistent Playlist Library
- Loaded playlists remain available in the library.
- Multiple playlists can be hosted simultaneously.

Available playlist routes:

```
/playlist.m3u
/playlist/{name}.m3u
/playlists
```

---

## Available Endpoints

```
/
Root landing page
```

```
/playlist.m3u
Returns the active playlist as an M3U file
```

```
/playlists
Returns a list of available playlists
```

```
/playlist/{name}.m3u
Returns a specific playlist
```

Examples:

```
http://YOUR-LAN-IP:5050/playlist/test1.m3u
http://YOUR-LAN-IP:5050/playlist/test2.m3u
```

```
/api/files
Returns the currently active file list (JSON)
```

```
/stream/{hash}
Streams a specific media file
(byte-range enabled for seeking and resume)
```

---

## Web Interface

TechStream includes a built-in web interface served from:

```
/web/index.html
```

Visiting the root server URL:

```
http://YOUR-LAN-IP:5050/
```

will load the default web interface, which allows:

- browsing playlists
- accessing server endpoints
- playing media directly in the browser

The `/web` directory can be modified to create a custom interface.

---

## Authentication (Optional)

TechStream supports basic HTTP authentication.

If enabled:

- Set a username and password in the application
- Enable **Require Authentication**
- Restart the server

Clients will be prompted for credentials when connecting.

---

## Requirements

- Windows 10 or Windows 11 (64-bit)
- Devices must be on the same LAN network

This build is **self-contained** and does not require .NET installation.

---

## Notes

- Always connect using your **LAN IP address**
- Do **not** use `127.0.0.1` from another device
- The server binds to `0.0.0.0` for LAN access
- Windows Firewall may prompt on first run
- SmartScreen warnings may appear because the application is not code-signed

---

## License

TechStream is distributed as compiled software.

See **LICENSE.txt** for details.

---

Built with focus on **simplicity, portability, LAN-first design, and zero cloud dependency.**
