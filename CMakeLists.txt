# Compile SDL
# cmake -DCMAKE_INSTALL_PREFIX=C:\reirina\dev-llvm\SDLdeps -DBUILD_SHARED_LIBS=OFF -DCMAKE_BUILD_TYPE=Release ..
# cmake --build . --config Release --target install
# the --config must match -DCMAKE_BUILD_TYPE when compile with xcode and MSVC

# -DCMAKE_C_COMPILER=C:\reirina\llvm-mingw-20250812-ucrt-x86_64\bin\clang.exe -DCMAKE_CXX_COMPILER=C:\reirina\llvm-mingw-20250812-ucrt-x86_64\bin\clang++.exe

# cmake -DCMAKE_INSTALL_PREFIX=C:\reirina\dev-llvm\SDLdeps -DSDL_SHARED=OFF -DSDL_STATIC=ON ..
# cmake --build . --target install


# Compile Project using SDL3
# cmake -DCMAKE_BUILD_TYPE=Release ..
# cmake --build . --config Release


cmake_minimum_required(VERSION 4.1.0)

project(sdlapp)

list(APPEND CMAKE_PREFIX_PATH "${CMAKE_CURRENT_SOURCE_DIR}/../SDLdeps")

find_package(SDL3 REQUIRED)

add_executable(sdlapp main.cpp)
target_link_libraries(sdlapp SDL3::SDL3)

add_executable(arch arch.c)

add_executable(snake snake.c)
target_link_libraries(snake SDL3::SDL3)
