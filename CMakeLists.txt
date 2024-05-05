cmake_minimum_required(VERSION 3.13)

include(pico_sdk_import.cmake)

project(auto_mouse C CXX ASM)

# initialize the Raspberry Pi Pico SDK
pico_sdk_init()

add_executable(auto_mouse)

target_sources(auto_mouse PUBLIC
    ${CMAKE_CURRENT_LIST_DIR}/main.c
    ${CMAKE_CURRENT_LIST_DIR}/usb_descriptors.c
)

# Make sure TinyUSB can find tusb_config.h
target_include_directories(auto_mouse PUBLIC
        ${CMAKE_CURRENT_LIST_DIR})

# In addition to pico_stdlib required for common PicoSDK functionality, add dependency on tinyusb_device
# for TinyUSB device support and tinyusb_board for the additional board support library used by the example
target_link_libraries(auto_mouse PUBLIC
    pico_stdlib
    pico_rand
    tinyusb_device
    tinyusb_board
)

pico_add_extra_outputs(auto_mouse)
