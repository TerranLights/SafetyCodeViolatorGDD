# Save_System
This keeps the game feeling safe and polished across platforms.

## Overview
A robust, cross-platform save system that works seamlessly on both **Steam (Windows/Linux)** and **Android**.

## Save Types

### 1. Profile / Career Save
- Player rank, total stats (victims, score, reputation)
- Unlocked locations, hazards, and cosmetics
- Overall progress and achievements
- Saved in `player_profile.json` (or encrypted binary on Steam)

### 2. Active Shift Save
- Current contract state
- All placed hazards and their modifications
- Worker positions, statuses, and routines
- Plausible Deniability meter + time elapsed
- Quick-save support (manual + auto every 30–45 seconds)

### 3. Highlight Reels & Clips
- Metadata for best moments (not full video to save space)
- Thumbnails and short replay data for quick viewing

## Technical Implementation

- **Primary Format**: JSON (human readable, easy to mod)
- **Godot Method**: `FileAccess` + `JSON` class for local saves
- **Steam Integration**: Steam Cloud + Steam Remote Storage for PC version
- **Android**: Standard app data directory (`user://` in Godot)

## Save Structure Exampleo

saves/
├── profile.json
├── contracts/
│   ├── contract_office_01.json
│   └── contract_factory_03.json
├── highlights/
│   └── reel_2025-06-23.json
└── backups/          ← auto backups on major failures


## Features

- **Auto-save** during Setup and Simulation phases
- **Cloud Sync** on Steam (with conflict resolution)
- **Multiple Profiles** support (for fun "different Violator styles")
- **Export / Import** functionality (good for modding & sharing)
- **Corruption Recovery** — keeps last 3 successful saves

## Android-Specific Notes
- Smaller save sizes (compress JSON where possible)
- Automatic backup to device storage
- Resume from last active shift when reopening the app
