# CMakeList.txt : Top-level CMake project file, do global configuration
# and include sub-projects here.
#
cmake_minimum_required (VERSION 3.10)

# Enable Hot Reload for MSVC compilers if supported.
if (POLICY CMP0141)
  cmake_policy(SET CMP0141 NEW)
  set(CMAKE_MSVC_DEBUG_INFORMATION_FORMAT "$<IF:$<AND:$<C_COMPILER_ID:MSVC>,$<CXX_COMPILER_ID:MSVC>>,$<$<CONFIG:Debug,RelWithDebInfo>:EditAndContinue>,$<$<CONFIG:Debug,RelWithDebInfo>:ProgramDatabase>>")
endif()

project ("Volume Control")

set(SRC "Volume Control/Volume Control.cpp")
set(ARGPARSER "Volume Control/ArgumentParser.cpp")

# Platform-specific source files
if (WIN32)
  set(PLATFORM_SRC "Volume Control/VolumeController_Windows.cpp")
  set(RESOURCE_FILE "Volume Control/Resource.rc")
elseif (APPLE)
  set(PLATFORM_SRC "Volume Control/VolumeController_macOS.cpp")
elseif (UNIX)
  set(PLATFORM_SRC "Volume Control/VolumeController_Linux.cpp")
else()
  message(FATAL_ERROR "Unsupported platform")
endif()

# Build executable with platform-specific files
if (WIN32)
  add_executable(volume
    ${SRC}
    ${ARGPARSER}
    ${PLATFORM_SRC}
    ${RESOURCE_FILE}
  )
else()
  add_executable(volume
    ${SRC}
    ${ARGPARSER}
    ${PLATFORM_SRC}
  )
endif()

target_compile_features(volume PRIVATE cxx_std_20)

# Platform-specific linking
if (WIN32)
  target_link_libraries(volume PRIVATE ole32)
elseif (APPLE)
  target_link_libraries(volume PRIVATE "-framework CoreAudio" "-framework CoreFoundation")
elseif (UNIX)
  find_package(PkgConfig REQUIRED)
  pkg_check_modules(PULSEAUDIO REQUIRED libpulse)
  target_link_libraries(volume PRIVATE ${PULSEAUDIO_LIBRARIES})
  target_include_directories(volume PRIVATE ${PULSEAUDIO_INCLUDE_DIRS})
endif()