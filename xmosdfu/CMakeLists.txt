cmake_minimum_required(VERSION 3.20)

project(XMOS_DUF VERSION 0.1.0 LANGUAGES CXX)

set(PROJECT_NAME xmosdfu)

include_directories(
    ${CMAKE_CURRENT_BINARY_DIR}
    ${CMAKE_CURRENT_SOURCE_DIR}/libusb/Linux64
    ${CMAKE_CURRENT_SOURCE_DIR}/libusb/Linux32
    )

set(EXECUTABLE_OUTPUT_PATH ${PROJECT_BINARY_DIR}/bin)
set(SRCLIST 
    xmosdfu.cpp
)

if(UNIX AND NOT APPLE)
    find_path(LIBSERIALPORT_INCLUDE_DIR NAMES libusb.h)
    find_library(LIBUSB_LIBRARY NAMES usb-1.0)
endif()

add_executable(${PROJECT_NAME} ${SRCLIST})

target_link_libraries(${PROJECT_NAME}
    ${LIBUSB_LIBRARY}
)