cmake_minimum_required(VERSION 3.10)
project(musical-project VERSION 1.0.0 LANGUAGES CXX)

# Set C++ standard
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Set build type
if(NOT CMAKE_BUILD_TYPE)
    set(CMAKE_BUILD_TYPE Release)
endif()

# Add source files
set(SOURCES
    src/main.cpp
)

# Create executable
add_executable(musical-project ${SOURCES})

# Include directories
target_include_directories(musical-project PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/include)

# Compiler flags
if(MSVC)
    target_compile_options(musical-project PRIVATE /W4)
else()
    target_compile_options(musical-project PRIVATE -Wall -Wextra -Wpedantic)
endif()
