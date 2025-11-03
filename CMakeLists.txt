cmake_minimum_required(VERSION 3.16)
project(OpenHopmon)

# set the output directory for built objects.
# This makes sure that the dynamic library goes into the build directory automatically.
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/$<CONFIGURATION>")
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/$<CONFIGURATION>")

add_subdirectory(third_party/SDL EXCLUDE_FROM_ALL)

add_executable(OpenHopmon src/main.cpp)

# Link to the actual SDL3 library.
target_link_libraries(OpenHopmon PRIVATE SDL3::SDL3)
