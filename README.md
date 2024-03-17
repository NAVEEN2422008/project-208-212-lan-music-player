# c208-c212 - LAN Music Player (FTP + Socket Server)

A client/server LAN music-sharing desktop app. The server runs a socket listener and an FTP server sharing a `shared_files` directory; the Tkinter client browses, uploads, downloads, and plays music files over FTP.

## Features
- Server auto-creates a `shared_files` directory, accepts socket connections per client, and runs an FTP server (user `lftpd`/`lftpd`) on port 21.
- Client GUI lists local `shared_files`, uploads songs via FTP (`STOR`), downloads to the user's Downloads folder (`RETR`).
- Play / Pause / Resume / Stop playback controls using pygame's mixer.

## Tech Stack
- Python 3
- `pyftpdlib` (server FTP)
- `pygame` / `playsound` (audio)
- Tkinter GUI, socket, ftplib

## Project Structure
```
c208-c212/
├── Server.py   # socket accept loop + pyftpdlib FTP server
└── Client.py   # Tkinter music window + FTP upload/download + player
```

## Installation
```
pip install pyftpdlib pygame playsound
```

## Usage
1. Run `python Server.py` to start the socket + FTP server.
2. Run `python Client.py` to open the music window.
3. Use the Upload/Download buttons and player controls; audio is served from the server's `shared_files` directory.