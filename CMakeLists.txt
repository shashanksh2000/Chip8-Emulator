cmake_minimum_required(VERSION 3.14)
project(chip8)

set(CMAKE_CXX_STANDARD 11)

#SET(SDL2_SEARCH_PATHS "C:/SDL2")

#find_package(SDL2 REQUIRED)

set(SDL2_INCLUDE_DIR "C:/SDL2/include")
set(SDL2_LIBRARY_DIR "C:/SDL2/lib")
include_directories(${SDL2_INCLUDE_DIR})

add_executable(
	chip8
	Source/Chip8.cpp
	Source/Main.cpp
	Source/Platform.cpp)

target_compile_options(chip8 PRIVATE -Wall)

#target_link_libraries(chip8 PRIVATE SDL2::SDL2)

target_link_libraries(chip8 -lmingw32 ${SDL2_LIBRARY_DIR}/libSDL2main.a ${SDL2_LIBRARY_DIR}/libSDL2.dll.a -mwindows)