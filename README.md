# TechStream v1.0.0 Lightweight LAN Media Streaming for Windows

OVERVIEW

TechStream is a lightweight Windows desktop application that streams
local media folders over LAN using HTTP with automatic M3U playlist
generation.

Stream your local media library to other devices on your network. No
cloud. No accounts. No tracking. Just local streaming.

------------------------------------------------------------------------

FEATURES

-   Stream local video files over LAN
-   Built-in HTTP server (Kestrel)
-   Byte-range support (seeking works in VLC)
-   In-browser playback via /stream/{id}
-   Auto-generated /playlist.m3u
-   Optional custom web interface
-   Portable (no installer required)

------------------------------------------------------------------------

REQUIREMENTS

-   Windows 10 or Windows 11 (64-bit)
-   Same LAN network as the client device

(No additional runtime installation required. This build is
self-contained.)

------------------------------------------------------------------------

QUICK START

1.  Extract the ZIP file.

2.  Run TechStream.exe.

3.  Select a folder containing video files or load an M3U playlist.

4.  Click Start Server.

5.  On another device, open VLC.

6.  Go to Media → Open Network Stream.

7.  Enter:

    http://YOUR-LAN-IP:5050/playlist.m3u

Example:

	http://192.168.1.42:5050/playlist.m3u

------------------------------------------------------------------------

OPTIONAL AUTHENTICATION

TechStream supports basic HTTP authentication.

If authentication is enabled:

-   Set a username and password in the application.
-   Check “Require Authentication”.
-   Restart the server if needed.

When connecting from VLC or a browser, you will be prompted to enter the
configured username and password.

If authentication is disabled, no credentials are required.

------------------------------------------------------------------------

SERVER BEHAVIOR

Root URL:

/

TechStream includes a default landing page located at:

/web/index.html

When visiting:

	http://YOUR-LAN-IP:5050/

The bundled landing page will be served.

If you replace or modify:

/web/index.html

Your custom page will be served instead.

This allows users to build their own custom web interface.

------------------------------------------------------------------------

AVAILABLE ENDPOINTS

/
Root page (default landing page or custom web interface)

/api/files
Returns the indexed media list in JSON format

/stream/{id}
Streams a specific media file (byte-range enabled, supports seeking and
browser playback)

/playlist.m3u
Generates a dynamic M3U playlist for use in VLC and compatible players

------------------------------------------------------------------------

IMPORTANT NOTES

-   Use your PC’s LAN IP address (not 127.0.0.1).
-   The server binds to 0.0.0.0 for LAN access.
-   You may need to allow the app through Windows Firewall.
-   Windows SmartScreen may show a warning because the app is not
    code-signed. Click “More Info” → “Run Anyway”.

------------------------------------------------------------------------

DISCLAIMER

TechStream is intended for streaming media you legally own or 
have the legal right to use within your local network. 

Users are solely responsible for ensuring their use of 
the Software complies with applicable laws.

Do not expose the server publicly unless you understand the risks and
legal implications.

------------------------------------------------------------------------

All Rights Reserved – See LICENSE.txt

------------------------------------------------------------------------

Built with focus on simplicity, portability, and zero cloud dependency.

