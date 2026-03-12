# IX File Manager

**A powerful, privacy-respecting, GPL-3.0 Android file manager combining the best features of the FOSS ecosystem.**

[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)
[![CI](https://github.com/Sumon-Kayal/ix-file-manager/actions/workflows/ci.yml/badge.svg)](https://github.com/Sumon-Kayal/ix-file-manager/actions)
[![Min SDK](https://img.shields.io/badge/min%20SDK-21%20(Android%205.0)-green)](https://developer.android.com/about/versions/lollipop)

---

## Features

### v1.0 (Current)
- **Archive support** — Create and extract ZIP, TAR, TAR.GZ, TAR.BZ2, TAR.XZ; read 7Z
- **Root access** — Full root file system browsing and operations via libsu
- **Material Design 3** — Clean, modern UI with dynamic color support
- **Storage volumes** — Internal storage, SD card, root partition
- **Bookmarks** — Persistent folder bookmarks
- **Recents** — Recently accessed files

### Planned (v1.x — v2.0)
- Dual-panel mode (Ghost Commander-style)
- Cloud remotes via rclone (FTP, SFTP, SMB, WebDAV, S3, Google Drive…)
- File encryption (Secure File Manager-inspired)
- Bash shell terminal panel
- Document/media browser tabs
- Archive password protection

---

## Built From

IX File Manager stands on the shoulders of these excellent GPL-3.0 projects:

| Project | Contribution |
|---|---|
| [Material Files](https://github.com/zhanghai/MaterialFiles) | Architecture base, Material Design 3 |
| [Amaze File Manager](https://github.com/TeamAmaze/AmazeFileManager) | Archive operations, root concepts |
| [Ghost Commander](https://sourceforge.net/projects/ghostcommander/) | Dual-panel UX, bash shell |
| [RCX / rclone](https://github.com/x0b/rcx) | Cloud remote architecture |
| [Secure File Manager](https://github.com/Secure-File-Manager/Secure-File-Manager) | Encryption approach |
| [Fossify File Manager](https://github.com/FossifyOrg/File-Manager) | Media browser patterns |

---

## Tech Stack

- **Language**: Kotlin
- **UI**: Material Design 3, ViewBinding
- **Architecture**: MVVM + Repository
- **Async**: Coroutines + Flow
- **Root**: [libsu](https://github.com/topjohnwu/libsu) by topjohnwu
- **Archives**: [Apache Commons Compress](https://commons.apache.org/proper/commons-compress/)
- **Database**: Room (bookmarks, recents)
- **Navigation**: Jetpack Navigation Component
- **Min SDK**: 21 (Android 5.0)
- **Target SDK**: 34 (Android 14)

---

## Project Structure

```
app/src/main/java/com/ixfilemanager/
├── core/
│   ├── archive/        # ArchiveManager, ArchiveService
│   ├── root/           # RootManager (libsu wrapper)
│   └── fs/             # File system utilities
├── data/
│   ├── model/          # FileItem, ArchiveEntry
│   └── repository/     # FileRepository, AppDatabase
├── ui/
│   ├── main/           # MainActivity, MainViewModel
│   ├── panels/         # FileBrowserFragment, ArchiveViewerFragment
│   └── dialogs/        # Archive, rename, properties dialogs
└── util/               # Extensions, formatters
```

---

## Building

### Requirements
- Android Studio Hedgehog or later
- JDK 17
- Android SDK 34

### In Termux (Android)
```bash
# Clone
git clone https://github.com/YOUR_USERNAME/ix-file-manager
cd ix-file-manager

# Build debug APK
./gradlew assembleDebug

# APK output
ls app/build/outputs/apk/debug/
```

### Install on device
```bash
adb install app/build/outputs/apk/debug/app-debug.apk
```

---

## Contributing

1. Fork this repo
2. Create a feature branch: `git checkout -b feature/dual-panel`
3. Commit changes: `git commit -m "feat: add dual-panel layout"`
4. Push: `git push origin feature/dual-panel`
5. Open a Pull Request

Please follow [Conventional Commits](https://www.conventionalcommits.org/).

---

## License

```
IX File Manager — Copyright (C) 2024 IX File Manager Contributors
This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.
```

See [LICENSE](LICENSE) for the full text.
