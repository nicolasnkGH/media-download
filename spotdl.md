# Guide to Using spotdl on Linux

## What is spotdl?

**spotdl** (Spotify Downloader) is a command-line tool that lets you download music from Spotify to your local machine. It finds the best audio sources (usually from YouTube) corresponding to Spotify tracks and downloads them with metadata and album art.

---

## Installing spotdl on Linux

### Method 1: Using pipx (Recommended)

1. **Install pipx (if not installed):**

```bash
sudo apt update
sudo apt install python3-pip python3-venv
python3 -m pip install --user pipx
python3 -m pipx ensurepath
exec "$SHELL"  # Restart shell to update PATH
```

2. **Install spotdl with pipx:**

```bash
pipx install spotdl
```

3. **Verify the installation:**

```bash
spotdl --version
```

### Method 2: Using pip inside a virtual environment

1. **Create a virtual environment:**

```bash
python3 -m venv ~/spotdl-venv
```

2. **Activate the virtual environment:**

```bash
source ~/spotdl-venv/bin/activate
```

3. **Install spotdl:**

```bash
pip install spotdl
```

4. **Use spotdl within this environment:**

```bash
spotdl --version
```

**Note: Remember to activate the virtual environment (source ~/spotdl-venv/bin/activate) every time you want to use spotdl with this method.**

### How to Use spotdl

**Download a single song by Spotify URL or name:**
```bash
spotdl "https://open.spotify.com/track/TRACK_ID"
```
or
```bash
spotdl "Song Name Here"
```

**Download a full Spotify playlist:**
```bash
spotdl "https://open.spotify.com/playlist/PLAYLIST_ID"
```
**Download a Spotify album:**
```bash
spotdl "https://open.spotify.com/album/ALBUM_ID"
```

**Specify output directory:**
```bash
spotdl --output /path/to/save "Song or URL"
```
**Note: Replace TRACK_ID, PLAYLIST_ID, ALBUM_ID, and /path/to/save with actual values.**

### Additional Features

- Downloads metadata (artist, album, cover art)
- Supports multiple audio formats: `mp3`, `flac`, `ogg`, `m4a`, `wav`, `opus`
- Supports downloading lyrics
- Supports multiple audio sources: YouTube, YouTube Music, SoundCloud, Bandcamp, Piped


### Prerequisites

**Install ffmpeg (required for audio processing):**
```bash
sudo apt install ffmpeg
```

### Important Notes

- spotdl uses Spotify links to find music but downloads from sources like YouTube.
- Respect copyright laws and Spotify's terms of service.
- Use spotdl responsibly.

### References

- [Official spotdl GitHub Repository](https://github.com/spotDL/spotify-downloader)
- [spotdl Documentation](https://spotdl.github.io/)


### Disclaimer

This guide is provided for educational purposes only.  
Downloading copyrighted content without proper authorization may violate Spotify's Terms of Service or applicable copyright laws.  
Use spotdl responsibly and ensure you have the right to download the content you access.  
The author of this guide does not condone or promote piracy in any form.
