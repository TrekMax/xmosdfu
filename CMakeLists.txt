cmake_minimum_required(VERSION 3.18)

if (WIN_PLATFORM)
    message(STATUS "----------- WIN_PLATFORM ---------")
    
    # 从环境变量获取交叉编译工具链路径
    set(GCC_PATH "/usr/bin")

    # 设置C和C++编译器
    set(CMAKE_C_COMPILER "/usr/bin/x86_64-w64-mingw32-gcc")
    set(CMAKE_CXX_COMPILER "/usr/bin/x86_64-w64-mingw32-g++")

    # 设置目标系统
    # set(CMAKE_SYSTEM_NAME WIN32)

    # 指定交叉编译环境的根路径（如果有）

    set(CMAKE_FIND_ROOT_PATH /usr/x86_64-w64-mingw32/)

    # 避免在系统路径中查找程序、库、头文件等
    set(CMAKE_FIND_ROOT_PATH_MODE_PROGRAM NEVER)
    set(CMAKE_FIND_ROOT_PATH_MODE_LIBRARY ONLY)
    set(CMAKE_FIND_ROOT_PATH_MODE_INCLUDE ONLY)

    add_definitions(-DWIN32)
    set(WIN32 1)
endif()

enable_language(CXX C)
set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED On)
set(CMAKE_CXX_EXTENSIONS Off)
set(CMAKE_BUILD_TYPE "Release" CACHE STRING "Only Release mode is allowed" FORCE)


project(xmosdfu)

add_subdirectory(lib/libusb)

add_executable(xmosdfu ${CMAKE_CURRENT_LIST_DIR}/src/xmosdfu.cpp)

target_include_directories(xmosdfu PRIVATE ./lib/libusb/libusb/libusb)
target_link_libraries(xmosdfu PRIVATE usb-1.0)


