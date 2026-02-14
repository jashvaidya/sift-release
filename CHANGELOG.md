# Changelog

All notable changes to Sift will be documented in this file.

## [0.1.12] - 2026-02-14

### Added
- **Gaming rarity color system** — clips are now color-coded by quality tier: Common (white), Uncommon (green), Rare (blue), Legendary (purple), Exotic (gold with glow)
- **Quality tier filtering** — filter clips by minimum quality tier with visual feedback
- **Volume control** — adjustable volume slider with mute toggle (M key), persisted across sessions
- **0.25x playback speed** — added ultra-slow-motion playback option
- **Keyboard shortcuts** — Ctrl+A (select all), Ctrl+E (export), Ctrl+, (settings)
- **Remember playback position** — video resumes where you left off
- **Window state persistence** — remembers window size and position between sessions
- **Startup diagnostics** — checks FFmpeg availability on launch
- **Duplicate video detection** — prevents importing the same video twice
- **Auto-save checkpointing** — periodically saves work to prevent data loss
- **Confirmation dialogs** — destructive actions now require confirmation
- **Clear cache option** — added to Settings panel
- **Selection indicator** — orange arrow above selected clip on timeline
- **Manual clip color** — manual clips shown in rose/pink (distinct from rarity colors)

### Improved
- **Responsive layout** — adapts to different window sizes with fluid content area
- **Compact sidebar** — fixed 320px width with tighter spacing for video cards
- **Dev workflow** — better process cleanup, faster dev builds

### Fixed
- Duplicate video upload now shows proper error instead of CORS error
- Orphaned backend processes on port 8000 are cleaned up on dev start
- PowerShell `$PID` variable conflict in dev script
- Removed excessive toast notifications (undo, redo, favorite, clip created)

### Removed
- Fullscreen mode (unnecessary for clip review workflow)
