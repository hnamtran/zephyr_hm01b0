# SPDX-License-Identifier: Apache-2.0

cmake_minimum_required(VERSION 3.20.0)
find_package(Zephyr REQUIRED HINTS $ENV{ZEPHYR_BASE})
project(picocamera)

set(PICO_SDK_PATH "/home/zephyrvm/zephyrproject/modules/hal/rpi_pico")

target_sources(app 
    PRIVATE 
    src/main.c 
    src/hm01b0.c
    ${PICO_SDK_PATH}/src/rp2_common/hardware_i2c/i2c.c
    )

include_directories(
    ${CMAKE_CURRENT_LIST_DIR}/src/include   
    ${PICO_SDK_PATH}/src/rp2_common/hardware_i2c/include
    ${PICO_SDK_PATH}/src/common/pico_time/include
    ${PICO_SDK_PATH}/src/boards/include
)
