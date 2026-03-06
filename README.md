# TwilightBoxart

A GUI tool that automatically downloads and manages box art for [TwilightMenu++](https://github.com/DS-Homebrew/TWiLightMenu) on Nintendo DS/DSi flashcarts.

## Features

- Auto-detects SD cards with TwilightMenu++ installed
- Downloads box art from multiple sources: GameTDB, LibRetro Thumbnails, SteamGridDB
- Supports NES, SNES, GB, GBC, GBA, NDS, Game Gear, Genesis, Master System ROMs
- Parallel downloads with 8 worker threads
- Auto-generates 32x32 custom icons for non-NDS ROMs
- Configurable output size and aspect ratio
- Drag & drop folder support

## Building

### Prerequisites

- C11 compiler (GCC, Clang, or MinGW)
- [raylib](https://www.raylib.com/) 5.0+
- [libcurl](https://curl.se/libcurl/)

### CMake (recommended, all platforms)

```bash
cmake -B build
cmake --build build
```

CMake will automatically download and build raylib if not found on your system. Only libcurl needs to be installed.

### macOS

```bash
brew install raylib curl
make
```

### Linux

```bash
# Install dependencies (Ubuntu/Debian)
sudo apt-get install -y libcurl4-openssl-dev libx11-dev libxrandr-dev \
    libxinerama-dev libxcursor-dev libxi-dev libgl-dev

# Option A: Install raylib from source
git clone https://github.com/raysan5/raylib.git --depth 1 -b 5.5
cd raylib && cmake -B build && cmake --build build && sudo cmake --install build

# Option B: Just use CMake (it will fetch raylib automatically)
cmake -B build && cmake --build build
```

### Windows (MSYS2/MinGW)

```bash
pacman -S mingw-w64-x86_64-{gcc,cmake,raylib,curl}
cmake -B build -G "MinGW Makefiles"
cmake --build build
```

## Usage

1. Insert your DS/DSi SD card
2. Launch TwilightBoxart
3. Select your SD card root (or let it auto-detect)
4. Optionally enter a [SteamGridDB API key](https://www.steamgriddb.com/) for extra coverage
5. Click **Start Download**
6. Wait for completion, then safely eject your SD card

## License

MIT License - see [LICENSE](LICENSE) for details.
