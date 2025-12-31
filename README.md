# HLS-FFmpeg

[![Bash](https://img.shields.io/badge/Language-Bash-informational?style=flat&logo=gnu-bash&color=4EAA25)](https://www.gnu.org/software/bash/)
[![FFmpeg](https://img.shields.io/badge/FFmpeg-FFmpeg-informational?style=flat&logo=ffmpeg&color=orange)](https://ffmpeg.org/)
[![Golang](https://img.shields.io/badge/Language-Go-informational?style=flat&logo=go&color=00ADD8)](https://golang.org/)

This project allows you to download a video from Google Drive, generate HLS assets (video segments) at different bitrates and resolutions, extract audio, and create master playlists for adaptive streaming. It also includes a Golang-based file server for local/internal live streaming.

## Features

- Download video from Google Drive  
- Generate HLS video segments at multiple resolutions and bitrates  
- Extract audio and create an HLS audio playlist  
- Create a master playlist for adaptive streaming  
- Simple local/internal streaming via a Golang file server  

## Technologies Used

- **Bash** – scripting automation  
- **FFmpeg** – video/audio processing  
- **cURL** – file downloading  
- **Golang** – lightweight file server  

## Prerequisites

- **FFmpeg** installed and accessible in your PATH  

## How to Run

You can run the script in two ways:

### 1. Run with `run.sh`  

```bash
sh run.sh
```
### 2. Run manually

### 2. Run manually

```bash
chmod +x script.sh
sh script.sh
```

## Output

After execution, you will find:

#### Video directories with HLS segments at different bitrates/resolutions:

- `video_6000k/`
- `video_4500k/`
- `video_3000k/`
- `video_2000k/`
- `video_1100k/`

#### Master playlists:

- `master.m3u8` – for video with multiple resolutions
- `audio_.m3u8` – for audio HLS segments

#### Logs directory:

- `logs/audio_log.txt` & `logs/audio_err.txt`
- `logs/video_log.txt`
- `logs/download_log.txt`
- `logs/server_log.txt`


```treeview
├── Readme.md
├── audio
│   ├── video_000.mp3
│   ├── video_001.mp3
│   └── ...
├── audio_.m3u8
├── config.sh
├── file_server.go
├── input.mp4
├── logs
│   ├── audio_err.txt
│   ├── audio_log.txt
│   ├── download_log.txt
│   ├── server_log.txt
│   └── video_log.txt
├── master.m3u8
├── run.sh
├── script.sh
├── video_1100k
│   ├── video_000.ts
│   └── ...
├── video_1100k.m3u8
├── video_2000k
│   ├── video_000.ts
│   └── ...
├── video_2000k.m3u8
├── video_3000k
│   ├── video_000.ts
│   └── ...
├── video_3000k.m3u8
├── video_4500k
│   ├── video_000.ts
│   └── ...
├── video_4500k.m3u8
├── video_6000k
│   ├── video_000.ts
│   └── ...
└── video_6000k.m3u8
```


## How to Open the Master Playlist

1. Open your terminal, and you will see:

```bash
Please open http://localhost:8081/master.m3u8 in Safari or VLC.
```

2. Or manually open with VLC:

- `File > Open Network > URL`
- Or directly open master.m3u8

3. Audio playlist (audio_.m3u8) can be opened with Music app on macOS or VLC.
