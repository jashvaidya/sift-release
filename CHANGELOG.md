# Changelog

All notable changes to Sift will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [0.1.9] - 2026-01-26

### Fixed
- 🎬 **CRITICAL**: Fixed export getting stuck at 20%
  - Export now uses non-blocking FFmpeg output reading with stall detection
  - Added timeout protection to prevent infinite hangs
- ✅ Fixed export showing "failed" even when successful
  - Now properly checks output file existence instead of relying on process return code
- 🛑 Fixed backend not shutting down when app closes
  - Clean process termination on application exit

### Improved
- 🧪 Added comprehensive test suite (278 tests)
  - 177 backend unit tests
  - 101 frontend tests (stores, components, API client)
- 🔒 Added pre-commit hooks to run tests before commits
- 📝 Added unified test runner script (`run-all-tests.ps1`)

---

## [0.1.8] - 2026-01-26

### Fixed
- 🛑 Backend process now properly terminates when the app is closed
  - Previously the backend would keep running in the background

---

## [0.1.7] - 2026-01-26

### Fixed
- 🎬 **CRITICAL**: Fixed FFmpeg not being found on systems without FFmpeg installed
  - Backend now correctly looks for FFmpeg in `resources/` folder (same level as exe)
  - This was causing "Invalid video file" errors for users without system FFmpeg
  - Previous fix only checked parent directory which was incorrect

---

## [0.1.6] - 2026-01-26

### Added
- 🔔 Update indicator in header - version badge now shows a pulsing green LED when an update is available
  - Click the version badge to re-open the update notification if you dismissed it
  - No need to restart the app to see the update option again

### Improved
- 🔄 Update state is now managed at the app level for better UX

---

## [0.1.5] - 2026-01-26

### Fixed
- 🔒 Disabled Content Security Policy entirely to resolve Tauri IPC communication issues
  - CSP was blocking internal Tauri plugin communication even with explicit allows
  - This is safe for desktop apps that don't load external content

---

## [0.1.4] - 2026-01-26

### Fixed
- 🔌 Fixed Content Security Policy blocking Tauri IPC protocol
  - Added `ipc:` and `http://ipc.localhost` to CSP connect-src directive
  - This fixes "Failed to fetch" errors that appeared after v0.1.3

### Improved
- 📦 Backend now uses centralized version file (`version.py`) for easier maintenance
- 🔄 All version references now properly synchronized across frontend and backend

---

## [0.1.3] - 2026-01-26

### Fixed
- 🏷️ Version badge in header now shows actual app version instead of hardcoded "v0.1.0"
  - Version is now dynamically read from Tauri at runtime

---

## [0.1.2] - 2026-01-26

### Fixed
- 🔄 Fixed auto-update failing with "Error opening file for writing: sift-backend.exe"
  - Backend process is now properly terminated before installer runs
  - Added NSIS PREINSTALL hook to kill running processes during update

---

## [0.1.1] - 2026-01-26

### Fixed
- 🐛 Fixed "Invalid video file: FileNotFoundError" error when uploading videos
  - FFmpeg was not being found in the correct location after installation
  - Backend now correctly locates FFmpeg in the Tauri resources folder
- 📝 Added FFmpeg/FFprobe path logging at startup for easier debugging

---

## [0.1.0] - 2026-01-26

### 🎉 Initial Release

**Sift** is now available! Find the gold in your gameplay footage.

#### Features
- 🤖 AI-powered moment detection using voice activity analysis
- 📹 Support for MP4, MKV, MOV, AVI, and WebM video formats
- ✂️ Frame-accurate clip trimming with preview
- 🎬 Individual and batch clip export
- 🔄 Automatic update system
- 🎨 Modern, dark-themed UI

#### Notes
- Windows 10/11 (64-bit) only for this release
- macOS and Linux support planned for future versions

---

<!-- Template for future releases:

## [X.X.X] - YYYY-MM-DD

### Added
- New feature description

### Changed
- Change description

### Fixed
- Bug fix description

### Removed
- Removed feature description

-->
