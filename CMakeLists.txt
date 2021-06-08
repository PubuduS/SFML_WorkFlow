# Sets up the minimum version of cmake
cmake_minimum_required(VERSION 3.16)

# Project Name
project(main)

# Set the C++ standard to be used
# -std=c++11 is a GCC only flag. So don't use that.
set (CMAKE_CXX_STANDARD 11)

# Set source files
set (SOURCE_FILES main.cpp)

# Look for SFML and add it
# set (CMAKE_MODULE_PATH "${CMAKE_CURRENT_LIST_DIR}/SFML/cmake-modules/")
find_package (SFML REQUIRED system window graphics network audio)

# We add the executable of the program
add_executable (main ${SOURCE_FILES})
target_link_libraries(main PUBLIC sfml-system sfml-window sfml-graphics)

install(TARGETS main)