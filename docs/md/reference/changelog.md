# Changelog

All notable changes to Volume Control will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.0.0] - 2026-01-09

### Added
- **Initial release of Volume Control** - A cross-platform command-line utility for managing system audio volume
- **Cross-platform support** - Built and distributed for:
  - **Windows** (x64) - Native Windows executable with full audio session management
  - **Linux** - Built with PulseAudio support for comprehensive Linux audio control
  - **macOS** - Native macOS binary supporting Core Audio framework
- **Command-line interface** - Simple and intuitive CLI for volume operations
- **System audio control** - Ability to get, set, and modify system master volume
- **Audio session management** - Control individual application audio streams (where supported by the OS)
- **Mute/Unmute functionality** - Quick toggle for system audio mute state
- **Volume increment/decrement** - Relative volume adjustments for fine-tuning
- **Percentage-based control** - Volume values expressed as percentages (0-100%)
- **Lightweight design** - Minimal resource footprint and fast execution
- **No external dependencies** - Self-contained executables for each platform

### Technical Details
- **Language**: C++17
- **Build System**: CMake with Ninja generator
- **Windows API**: Direct integration with Windows Audio Session API (WASAPI)
- **Linux Integration**: PulseAudio API for Linux audio management
- **macOS Integration**: Core Audio framework for macOS audio control
- **CI/CD**: Automated builds and releases via GitHub Actions

### Features
- Get current system volume level
- Set system volume to specific percentage
- Increase/decrease volume by specified amount
- Mute/unmute system audio
- List active audio sessions (platform-dependent)
- Control individual application volumes (where supported)
- Query audio device information
- Cross-platform consistent command-line interface

### Platform-Specific Notes
- **Windows**: Full WASAPI integration with support for both legacy and modern audio endpoints
- **Linux**: Requires PulseAudio (default on most modern distributions)
- **macOS**: Core Audio integration with support for both built-in and external audio devices

---

## [Unreleased]

### Planned - Considerations
- GUI interface for desktop environments
- Audio device selection and switching
- Volume presets and profiles
- System tray integration (Windows/macOS)
- Audio visualization features
- Advanced audio routing capabilities