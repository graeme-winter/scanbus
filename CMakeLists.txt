cmake_minimum_required(VERSION 3.13)

set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 17)

include(pico_sdk_import.cmake)

project(scanbus C CXX ASM)

pico_sdk_init()

add_executable(scanbus scanbus.c)

pico_set_program_name(scanbus "scanbus")
pico_set_program_version(scanbus "0.1")

pico_enable_stdio_uart(scanbus 1)
pico_enable_stdio_usb(scanbus 1)

target_link_libraries(scanbus pico_stdlib hardware_i2c)

pico_add_extra_outputs(scanbus)

