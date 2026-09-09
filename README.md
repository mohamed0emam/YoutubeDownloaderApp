# 🚀 Pro Playlist Downloader v3.0

![Version](https://img.shields.io/badge/Version-3.0.0-blue.svg?style=for-the-badge&logo=youtube)
![Platform](https://img.shields.io/badge/Platform-Windows_10_%7C_11_(64--bit)-lightgrey.svg?style=for-the-badge&logo=windows)
![Framework](https://img.shields.io/badge/.NET-10.0_WPF-512BD4.svg?style=for-the-badge&logo=dotnet)
![License](https://img.shields.io/badge/License-EULA_Proprietary-orange.svg?style=for-the-badge)

**Pro Playlist Downloader** is an enterprise-grade, standalone Windows desktop application engineered to download full YouTube playlists or individual media files with exceptional speed, rock-solid resilience, and intelligent stream management.

Powered by a **Modern Fluent UI (Windows 11 inspired)**, self-healing stream extraction algorithms, and scoped Win32 process isolation, version **3.0** delivers a completely frictionless and crash-free media downloading experience.

---

## 🌟 What's New & Key Features in v3.0

### 1. 🎨 Modern Fluent Design & Ergonomics (Windows 11 Inspired)
- **Refined Theme System:** Premium deep-slate dark theme (`#0F172A` / `#1E293B`) and ultra-clean light theme featuring modern typography (*Segoe UI Variable*).
- **Interactive Status Pill Badges:** Replaced generic text with translucent, color-coded pill badges reflecting live states (`Preparing...`, `Downloading...`, `Converting...`, `Completed`, `Failed`).
- **Smart Input Card:** 1-click **"Paste from Clipboard"** button right inside the URL input bar for instant link entry, plus an instant **"Clear"** button.
- **Interactive Empty State:** Visually rich welcome state with media illustrations and feature highlights when no URL is active.
- **Color-Shifting Progress Indicators:** Fluid progress bars that dynamically shift accent colors based on download, extraction, or completion status.

### 2. 🔄 Real-Time "Converting..." & FFmpeg Post-Processing Tracking
- **Live Output Stream Listener:** Directly hooks into the underlying download engine's live STDOUT to detect audio extraction (`[ExtractAudio]`), media merging (`[Merger]`), and video conversion (`[ffmpeg]`) in real-time.
- **Continuous 4-Phase Visual Pipeline:** Transparent status transitions:
  $$\text{Preparing...} \longrightarrow \text{Downloading... (0\% - 100\%)} \longrightarrow \text{Converting... (100\%)} \longrightarrow \text{Completed (100\%) }$$
  No more wondering whether the application is stuck during audio extraction or format remuxing!

### 3. 🌐 Self-Healing Download Engine & YouTube HTTP 403 Resolution
- **Startup Auto-Update:** Non-blocking background health check (`yt-dlp -U`) upon startup to ensure stream decipher algorithms are always aligned with the latest YouTube player changes.
- **Automated 403 Self-Healing:** Intelligently identifies YouTube stream cipher/throttling blocks (HTTP 403 Forbidden), triggers an in-memory engine upgrade, and retries the stream seamlessly.
- **High-Resilience Stream Flags:** Built-in integration for `ForceIPv4`, `NoCheckCertificates`, and geo-bypass parameters across all download pipelines.

### 4. 🔒 Enterprise Child Process Tree Isolation (`ProcessManager`)
- **Scoped Win32 Snapshot Tracking:** Employs low-level Win32 `CreateToolhelp32Snapshot` process management to precisely track child process IDs (PIDs).
- **Safe Targeted Cancellation:** Clicking **"Cancel"** instantly terminates the application's spawned `yt-dlp` and `ffmpeg` processes (`entireProcessTree: true`) without touching external background tools or other instances on your PC.

### 5. 📊 Accurate Video & Audio Size Estimation
- **Direct Format Manifest Extraction:** Interrogates streaming manifests to compute accurate file sizes across all video resolutions (1080p, 720p, 480p, 360p) and 320k audio streams.
- **Isolated Multi-Tier Fallback:** Eliminates annoying `"N/A"` file size placeholders with real-time estimation algorithms.

### 6. 🔍 Transparent Error Diagnostics (`CustomMessageBox`)
- **Detailed Technical Diagnostics:** Diagnoses exceptions with an expandable inspection panel detailing error types, stack traces, and engine output logs.
- **1-Click "Copy Error" Button:** Instantly copies formatted diagnostic data to the Windows Clipboard for quick reporting and assistance.

### 7. 🛡️ Silent, Non-Intrusive Workflow
- **Zero Annoying Completion Modals:** Removed intrusive modal popups upon download completion. Progress and status update smoothly on list items without interrupting your work.
- **Gentle System Tray Notifications:** Non-blocking Windows balloon tip notifications alert you when downloads finish while the app is minimized to the system tray.

### 8. ⚡ Multi-Threaded Batch & Quality Control
- **High-Speed Multi-Threading:** Downloads up to **3 items simultaneously** for maximum bandwidth utilization without CPU overload.
- **Advanced Subtitle Extraction:** Automatically discovers and saves subtitles (original or auto-generated) as cleanly formatted `.srt` files alongside media.
- **Smart Duplicate Detection:** Automatically skips already downloaded files (marked in clean green status) to avoid re-downloading existing media.

---

### 🖥️ Application Preview

<p align="center">
  <img width="950" alt="Pro Playlist Downloader v3.0 Interface" src="https://github.com/user-attachments/assets/67eb22e2-c992-4ebb-a569-067e883f999a" />
</p>

---

## 📥 Download & Installation

### Option 1: Official Windows Installer (Recommended)
1. Download **`Pro_Playlist_Downloader_v3.0_Setup.exe`** from the **[Releases](https://github.com/mohamed0emam/YoutubeDownloaderApp/releases/latest)** section.
2. Run the installer (all required components and runtime dependencies are bundled).
3. Launch **Pro Playlist Downloader** from your Desktop or Start Menu!

### Option 2: Portable Package
1. Download **`YoutubeDownloaderApp-v3.0.zip`**.
2. Extract the archive to your preferred folder.
3. Run **`YoutubeDownloaderApp.exe`** (requires Windows 10/11 64-bit).

---

## 💡 How to Use

1. **Paste URL:** Paste any YouTube playlist or video link into the input bar (or click the 📋 **Paste** button).
2. **Fetch:** Click **Fetch** to instantly load video titles, thumbnails, durations, and sizes.
3. **Customize Quality:** Select your desired format:
   - *Highest Video Quality (up to 1080p)*
   - *720p / 480p / 360p MP4*
   - *Pristine MP3 Audio Only (320kbps)*
   - *Subtitles (.SRT)*
4. **Choose Destination:** Select your preferred save directory.
5. **Download:** Click **Download Selected** and monitor real-time download and conversion progress!

---

## 📝 License & Terms

This software is provided as a proprietary desktop tool. All rights reserved. By installing and using this software, you agree to the End-User License Agreement (EULA) bundled within the installer.

---

<p align="center">
  <b>Developed with passion and precision by Eng. Mohamed Emam</b><br>
  <sub>Official Repository: <a href="https://github.com/mohamed0emam/YoutubeDownloaderApp">https://github.com/mohamed0emam/YoutubeDownloaderApp</a></sub>
</p>
