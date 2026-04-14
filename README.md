# 🚀 Pro Playlist Downloader

![Version](https://img.shields.io/badge/Version-2.0.0-blue.svg)
![Platform](https://img.shields.io/badge/Platform-Windows-lightgrey.svg)
![Architecture](https://img.shields.io/badge/Architecture-MVVM-success.svg)

**Pro Playlist Downloader** is a highly optimized, standalone Windows desktop application designed to download full YouTube playlists or single videos with ultimate speed, stability, and smart quality control.

Built using C# and WPF (MVVM Architecture), this tool acts as a powerful GUI wrapper around `yt-dlp` and `FFmpeg`, offering dynamic size calculations, smart subtitle extraction, and military-grade error handling.

---

## ✨ Key Features (المميزات الرئيسية)

### 1. ⚡ Smart & Concurrent Downloading
- **Batch Processing:** Fetch entire playlists or single URLs with one click.
- **Concurrent Downloads:** Downloads up to **3 videos simultaneously** using `SemaphoreSlim` to maximize bandwidth without overloading the system.
- **Auto-Dependency Setup:** The app automatically downloads and configures `yt-dlp.exe` and `ffmpeg.exe` in the background if they are missing. No manual setup required!

### 2. 💾 Dynamic Size Calculator
- Real-time estimation of the total download size for all selected videos.
- Dynamically recalculates sizes when the user changes the quality (e.g., from 1080p to Audio Only) by fetching active stream manifests via `YoutubeExplode`.
- Auto-formats size displays (MB to GB) for a clean UI.

### 3. 🎬 Advanced Quality & Subtitle Control
- **Smart Quality Selector:** Choose between Highest Quality, 1080p, 720p, 480p, 360p, or high-quality Audio Only. The engine forces FFmpeg to merge outputs into a clean `.mp4` format.
- **Subtitle Extraction:** Automatically fetches original and auto-generated captions, saving them as cleanly formatted `.srt` files alongside the video (without embedding them forcefully).

### 4. 🛡️ Intelligent Error Handling & Stability
- **Anti-Crash Architecture:** Uses Windows Native API (`kernel32.dll -> SetErrorMode`) to suppress annoying Windows crash dialogs when killing background processes.
- **Safe Cancellation:** A highly robust cancellation token system (`CancellationTokenSource`) that instantly kills orphaned `yt-dlp` and `ffmpeg` processes upon user cancellation, preventing memory leaks and UI freezes.
- **Smart Duplicate Detection:** Automatically detects if a file "already exists" and marks it as completed (Green) instead of throwing an error.
- **Browser DPAPI / Cookie Lock Detection:** Intelligently detects if your browser's security (Cookies/DPAPI) is blocking the download and provides human-readable UI instructions to fix it.
- **DRM Protection Detection:** Politely informs the user if the requested video is DRM-protected or region-blocked.

---
### 🖥️ Preview
<img width="1920" height="1005" alt="Screenshot (122)" src="https://github.com/user-attachments/assets/67eb22e2-c992-4ebb-a569-067e883f999a" />

## 🛠️ Under the Hood (Technical Stack)

- **Framework:** .NET / C# WPF (Windows Presentation Foundation)
- **Architecture:** MVVM (Model-View-ViewModel) using `ObservableObject`.
- **Core Libraries:** - `YoutubeDLSharp` (For executing yt-dlp commands & progress tracking).
  - `YoutubeExplode` (For fast manifest fetching and size estimations).
- **Background Processing:** Extensively uses `Task`, `async/await`, and `SemaphoreSlim` to keep the UI 100% responsive during heavy operations.

---

## 📥 Getting Started

1. Download the latest `Setup.exe` from the **[Releases](#)** tab.
2. Install the application (No prerequisites needed).
3. Paste a YouTube link, select your desired qualities and subtitles, and hit Download!

---

## 📝 License
This software is provided as a closed-source tool. All rights reserved to the developer. By using this software, you agree to the End-User License Agreement (EULA) provided during installation.

---
**Developed with passion and precision by Eng. Mohamed Emam**
