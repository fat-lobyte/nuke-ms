# CMakeLists.txt file for the nuke-ms project

# we need at lest cmake 2.6
cmake_minimum_required(VERSION 2.6)

# we are compiling nuke-ms, and it's C++-Code
project(nuke-ms)

enable_testing()


# We need boost for all executeables
set(Boost_USE_MULTITHREADED ON)
find_package( Boost 1.39.0 REQUIRED thread system)

# Add Boost header and library directories
include_directories(${Boost_INCLUDE_DIRS})
link_directories(${Boost_LIBRARY_DIRS})


# Add source directory, place resulting files in build directory
add_subdirectory(src)

# Add include directory
add_subdirectory(include)

# Add tests, but exclude from all target
add_subdirectory(test EXCLUDE_FROM_ALL)

# Add doc directory, but exclude from all target
add_subdirectory(doc EXCLUDE_FROM_ALL)
