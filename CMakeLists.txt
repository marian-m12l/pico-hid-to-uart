cmake_minimum_required(VERSION 3.13)
# initialize the SDK based on PICO_SDK_PATH
# note: this must happen before project()
include(pico_sdk_import.cmake)
project(pico-hid-to-uart)
 
pico_sdk_init()

add_executable(pico-hid-to-uart)

target_include_directories(pico-hid-to-uart PRIVATE ${CMAKE_CURRENT_LIST_DIR})

target_sources(pico-hid-to-uart PRIVATE
        main.c
        hid_app.c
        )
        
target_link_libraries(pico-hid-to-uart PRIVATE pico_stdlib tinyusb_host tinyusb_board)
pico_add_extra_outputs(pico-hid-to-uart)