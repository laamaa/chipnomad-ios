# ChipNomad iOS

iOS port of [ChipNomad Tracker](https://github.com/Megus/chipnomad-tracker), a multi-platform tracker with LSDJ-like interface for creating chiptune music.

## About

ChipNomad is a tracker designed for creating chiptune music with an interface inspired by LSDJ and M8 Tracker. This iOS port brings the tracker to iPhone devices. The port is still in its early stages and may or may not work on your device...

For more information about ChipNomad Tracker:
- [ChipNomad Manual](https://chipnomad.org/manual)
- [ChipNomad Discord](https://discord.gg/PJarAn2QCW)

## Prerequisites

- macOS with Xcode installed
- iOS development environment set up
- Git

## Getting Started

### 1. Clone the Repository

```bash
git clone <repository-url>
cd chipnomad
```

### 2. Initialize and Update Git Submodules

This project uses three git submodules for external dependencies:
- **SDL** - Graphics, audio, and input handling
- **chipnomad-tracker** - Core tracker engine
- **freetype2-ios** - Font rendering library

To download all submodules, run:

```bash
git submodule update --init --recursive
```

This command will:
- Initialize the submodules defined in `.gitmodules`
- Clone the submodule repositories into the `ext/` directory
- Recursively initialize any nested submodules

### 3. Open the Project

Open the Xcode project:

```bash
open chipnomad.xcodeproj
```

Or double-click `chipnomad.xcodeproj` in Finder.

### 4. Build and Run

1. Select your target device or simulator in Xcode
2. Press `Cmd+R` to build and run the project

## Project Structure

```
chipnomad/
├── chipnomad/           # iOS app source code and resources
├── chipnomad.xcodeproj/ # Xcode project file
└── ext/                 # External dependencies (git submodules)
    ├── SDL/             # SDL library
    ├── chipnomad-tracker/  # Core tracker engine
    └── freetype2-ios/   # FreeType font library
```

## Updating Submodules

To update all submodules to their latest commits:

```bash
git submodule update --remote --recursive
```

To update a specific submodule:

```bash
cd ext/chipnomad-tracker
git pull origin main
cd ../..
git add ext/chipnomad-tracker
git commit -m "Update chipnomad-tracker submodule"
```

## Troubleshooting

### Submodule Directories Are Empty

If the `ext/` directory exists but the subdirectories are empty, run:

```bash
git submodule update --init --recursive
```

### Submodule Update Issues

If you encounter issues updating submodules, try:

```bash
git submodule sync --recursive
git submodule update --init --recursive
```

## License

Please refer to the individual submodule repositories for their respective licenses.

## Acknowledgements

ChipNomad Tracker is created by Megus and wouldn't be possible without:
- [LSDJ](https://www.littlesounddj.com/lsd/index.php) by Johan Kotlinski
- [M8 Tracker](https://dirtywave.com) by Trash80
- [Ayumi AY chip emulator](https://github.com/true-grue/ayumi) by Peter Sovietov
