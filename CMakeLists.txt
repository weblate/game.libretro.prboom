cmake_minimum_required(VERSION 3.1)
project(game.libretro.prboom)

list(APPEND CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR})

find_package(Kodi REQUIRED)
find_library(PRBOOM_LIB NAMES prboom_libretro${CMAKE_SHARED_LIBRARY_SUFFIX} PATH_SUFFIXES libretro)

set(PRBOOM_CUSTOM_BINARY ${PRBOOM_LIB}
    ${PROJECT_NAME}${CMAKE_SHARED_LIBRARY_SUFFIX})

build_addon(${PROJECT_NAME} PRBOOM "")

include(CPack)
