cmake_minimum_required(VERSION 3.21)

include(${CMAKE_CURRENT_SOURCE_DIR}/../../cmake/prelude.cmake)
project(simpleble_examples)
include(${CMAKE_CURRENT_SOURCE_DIR}/../../cmake/epilogue.cmake)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_EXTENSIONS OFF)

option(SIMPLEBLE_LOCAL "Use local SimpleBLE" ON)

if (SIMPLEBLE_LOCAL)
    add_subdirectory(${CMAKE_CURRENT_LIST_DIR}/../../simpleble ${CMAKE_BINARY_DIR}/simpleble)
else()
    cmake_policy(SET CMP0144 OLD)
    find_package(simpleble CONFIG REQUIRED)
endif()

# C++

add_subdirectory(cpp/scan)
add_subdirectory(cpp/connect)
add_subdirectory(cpp/write)



