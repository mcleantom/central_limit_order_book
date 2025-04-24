cmake_minimum_required(VERSION 3.16)
project(OrderBook LANGUAGES CXX)

# Set C++ standard
set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Gather source files
file(GLOB_RECURSE LIB_SOURCES CONFIGURE_DEPENDS
    "${CMAKE_SOURCE_DIR}/src/*.cpp"
    "${CMAKE_SOURCE_DIR}/src/*.h"
    "${CMAKE_SOURCE_DIR}/src/*.hpp"
)

# Create the library (change STATIC to SHARED if needed)
add_executable(OrderBook ${LIB_SOURCES})

# Optionally set include directories
target_include_directories(OrderBook PRIVATE
    ${CMAKE_SOURCE_DIR}/src
)

