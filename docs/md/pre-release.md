# Pre-Release Information

## Upcoming Release: v1.1.0 (Planned)

### Status
**Currently in Development** - Target release: Q1 2026

### Planned Features
- **Enhanced Audio Device Management**
  - List available audio devices
  - Switch between audio output devices
  - Device-specific volume control

- **Advanced Volume Controls**
  - Volume presets and profiles
  - Application-specific volume management
  - Fine-grained volume control (1% increments)

- **User Experience Improvements**
  - Interactive mode for real-time volume adjustment
  - Colored output for better visibility
  - Progress bars for volume changes
  - Verbose and quiet modes

- **Platform-Specific Enhancements**
  - **Windows**: Enhanced WASAPI integration with session management
  - **Linux**: PipeWire support alongside PulseAudio
  - **macOS**: Improved Core Audio integration with Bluetooth device support

### Testing & Feedback
This release is currently in development and testing phase. Early adopters and testers are welcome to try the development builds and provide feedback.

### Development Builds
Development builds are available through:
- **GitHub Actions**: Automated builds from the `develop` branch
- **Artifacts**: Downloadable from workflow runs
- **Docker**: Containerized builds for testing environments

### Known Issues
- Audio device switching may require elevated privileges on some systems
- Some Bluetooth audio devices may have limited functionality
- Application-specific volume control varies by platform capabilities

### Testing Priority Areas
We're particularly looking for feedback on:
1. Multi-device audio environments
2. Bluetooth audio device compatibility
3. Performance with large numbers of audio sessions
4. Cross-platform consistency of behavior

### How to Test Development Builds
```bash
# Clone the repository
git clone https://github.com/Lateralus138/Volume-Control.git
cd Volume-Control

# Switch to develop branch
git checkout develop

# Build from source (requires CMake and platform-specific dependencies)
mkdir build && cd build
cmake .. -G "Ninja" -DCMAKE_BUILD_TYPE=Release
cmake --build .

# Test the new features
./volume --help
./volume devices list
./volume preset create "gaming" 75
```

### Contributing
We welcome contributions! See our [Contributing Guidelines](../../CONTRIBUTING.md) for details on:
- Code submission process
- Testing requirements
- Documentation standards
- Issue reporting guidelines

### Release Timeline
- **Alpha**: Current - Core feature development
- **Beta**: Late January 2026 - Feature-complete, public testing
- **RC**: Early February 2026 - Release candidate, bug fixes only
- **Release**: Mid-February 2026 - Stable v1.1.0 release

## Changelog

See [Changelog](./docs/md/reference/changelog.md)

---

## Current Stable Release

While v1.1.0 is in development, the current stable release is **v1.0.0**, available for download from the [Releases](https://github.com/Lateralus138/Volume-Control/releases) page.

### Upgrade Path
- Upgrading from v1.0.0 to v1.1.0 will be seamless
- Configuration files and settings will be preserved
- Backward compatibility will be maintained for existing command-line interfaces

## Feedback Channels

### For Development Testing
- **GitHub Issues**: Report bugs and feature requests
- **GitHub Discussions**: General discussion and feedback
- **Discord**: Real-time chat with developers (coming soon)

### Security Concerns
For security-related issues, please email: security@lateralus138.com

## Roadmap Beyond v1.1.0

### v1.2.0 (Planned Q2 2026)
- GUI interface for desktop environments
- System tray integration
- Audio visualization features

### v1.3.0 (Planned Q3 2026)
- Advanced audio routing capabilities
- Network audio streaming support
- Plugin system for extensibility

---

**Note**: Pre-release information is subject to change. Features and timelines may be adjusted based on development progress, testing feedback, and community needs.