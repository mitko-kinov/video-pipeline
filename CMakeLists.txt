cmake_minimum_required(VERSION 3.15)

# Set the path to the vcpkg toolchain file
set(CMAKE_TOOLCHAIN_FILE "/home/mitkoPi/Projects/video-pipeline/vcpkg/scripts/buildsystems/vcpkg.cmake" CACHE STRING "Vcpkg toolchain file")

project(video-pipeline LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)

# Find the fmt library
set(CMAKE_PREFIX_PATH "~/Projects/vcpkg/installed/x64-linux")
find_package(fmt CONFIG REQUIRED)

# Add executable target
add_executable(video-pipeline src/main.cpp)

# Link against fmt
target_link_libraries(video-pipeline PRIVATE fmt::fmt)

