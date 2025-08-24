# Compile SDL
# cmake -DCMAKE_INSTALL_PREFIX=C:\reirina\dev-llvm\SDLdeps -DBUILD_SHARED_LIBS=OFF -DCMAKE_BUILD_TYPE=Release ..
# cmake --build . --config Release --target install
# the --config must match -DCMAKE_BUILD_TYPE when compile with xcode and MSVC

# Compile Project using SDL3
# cmake -DCMAKE_BUILD_TYPE=Release ..
# cmake --build . --config Release


cmake_minimum_required(VERSION 4.1.0)

project(sdlapp)

# set(OGRE_DIR "${CMAKE_CURRENT_SOURCE_DIR}/../deps/CMake/OGRE")
# set(OGRE_MEDIA_DIR "${CMAKE_CURRENT_SOURCE_DIR}/../ogre/Media")
# list(APPEND CMAKE_PREFIX_PATH "${CMAKE_CURRENT_SOURCE_DIR}/../deps")
# list(APPEND CMAKE_MODULE_PATH "${CMAKE_CURRENT_SOURCE_DIR}/../../deps/CMake")
list(APPEND CMAKE_PREFIX_PATH "${CMAKE_CURRENT_SOURCE_DIR}/../SDLdeps")
# list(APPEND CMAKE_MODULE_PATH "${CMAKE_CURRENT_SOURCE_DIR}/../../SDLdeps/lib/cmake")

find_package(SDL3 REQUIRED)
# find_package(OGRE REQUIRED COMPONENTS Bites CONFIG)

add_executable(sdlapp main.cpp)

target_link_libraries(sdlapp SDL3::SDL3)
# target_link_libraries(wlan kernel32 user32 gdi32 wlanapi)

add_executable(arch arch.c)
