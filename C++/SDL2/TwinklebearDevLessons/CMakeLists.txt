cmake_minimum_required(VERSION 3.10)
project(TwinklebearDevLessons)

# Use the FindSDL2 modules
set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} "${TwinklebearDevLessons_SOURCE_DIR}/cmake")
# set output directory for binaries
set(BIN_DIR ${TwinklebearDevLessons_SOURCE_DIR}/bin)

# Set warning levels for clang gcc & msvc
# Set debug and optimization flags for build type
if (${CMAKE_CXX_COMPILER_ID} STREQUAL "GNU" OR ${CMAKE_CXX_COMPILER_ID} STREQUAL "Clang")
    set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall -Wextra -pedantic -std=c++11")
    set(CMAKE_CXX_FLAGS_DEBUG "${CMAKE_CXX_FLAGS} ${CMAKE_CXX_FLAGS_DEBUG} -g")
    set(CMAKE_CXX_FLAGS_RELEASE "${CMAKE_CXX_FLAGS} ${CMAKE_CXX_FLAGS_RELEASE} -O2")
elseif (${CMAKE_CXX_COMPLIER_ID} STREQUAL "MSVC")
    if (CMAKE_CXX_FLAGS MATCHES "/W[0-4]")
        string(REGEX REPLACE "/W[0-4]" "/W4" CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS}")
    else()
        set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} /W4")
    endif()
endif()

# Find SDL2 and put it in the include path
find_package(SDL2 REQUIRED)
include_directories(${SDL2_INCLUDE_DIR})

# add include directories
include_directories(include)

# Look in the subdirectories and find its CMakeLists.text to build the executable
add_subdirectory(Lesson0)
add_subdirectory(Lesson0PS)
add_subdirectory(Lesson1)
add_subdirectory(Lesson1PS)
add_subdirectory(Lesson2)
