# Release Information

## Current Release: v1.0.0

### Release Date
January 9, 2026

### Overview
This is the initial stable release of Volume Control, providing a comprehensive cross-platform command-line utility for managing system audio volume across Windows, Linux, and macOS operating systems.

### Downloads
- **Windows**: `volume-windows.exe` - Native Windows x64 executable
- **Linux**: `volume-linux` - Linux binary with PulseAudio support
- **macOS**: `volume-macos` - macOS binary with Core Audio support

### System Requirements
- **Windows**: Windows 10 or later (x64)
- **Linux**: Any modern distribution with PulseAudio installed
- **macOS**: macOS 10.14 (Mojave) or later

### Installation
1. Download the appropriate binary for your operating system
2. Place the executable in your preferred location
3. Add to system PATH (optional, for global access)
4. Run `volume --help` to see available commands

### Quick Start
```bash
# Show current volume (default behavior when no arguments)
volume

# Show help
volume --help

# Set volume to 50%
volume 50

# Increase volume by 10%
volume +10

# Decrease volume by 10%
volume -10

# Set to maximum volume (100%)
volume --max

# Set to minimum volume (0%)
volume --min

# Mute audio
volume --mute

# Unmute audio
volume --unmute

# Example combinations
volume 75 --mute    # Set to 75% and mute
volume +20 --unmute  # Increase by 20% and unmute
```

### Key Features
- Cross-platform compatibility
- Lightweight and fast execution
- No external dependencies required
- Intuitive command-line interface
- Comprehensive audio control capabilities

### Security & Verification
All binaries are cryptographically signed and verified. SHA256 hashes are provided for integrity verification in the main README.

## Changelog

See [Changelog](./docs/md/reference/changelog.md)

---

## Previous Releases

No previous releases available - this is the initial release.

## Support

For issues, feature requests, or questions:
- [GitHub Issues](https://github.com/Lateralus138/Volume-Control/issues)
- [GitHub Discussions](https://github.com/Lateralus138/Volume-Control/discussions)

## License

This project is licensed under the GNU General Public License v3.0. See [LICENSE](../../LICENSE) for details.