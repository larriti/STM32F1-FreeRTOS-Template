# CMake minimum version
cmake_minimum_required (VERSION 3.1)

# Project Infomation
project (STM32F10x_StdPeriph_Driverlib)

# Reset output path
set(EXECUTABLE_OUTPUT_PATH ${CMAKE_BINARY_DIR}/bin)
set(LIBRARY_OUTPUT_PATH ${CMAKE_BINARY_DIR}/lib)

# Set include path
include_directories( CMSIS/Include )
include_directories( CMSIS/Device/Include )
include_directories( STM32F10x_StdPeriph_Driver/inc )

# The need build source path and build all files
aux_source_directory (STM32F10x_StdPeriph_Driver/src DIR_STM32F10x_StdPeriph_Driver_SRCS)

# CC AR
set(CMAKE_C_COMPILER "arm-none-eabi-gcc")
set(CMAKE_C_AR "arm-none-eabi-ar")

# CFLAGS
set(CMAKE_C_FLAGS "-g -mthumb -fno-builtin -mcpu=cortex-m3 -Wall -std=gnu99 -ffunction-sections -fdata-sections -fomit-frame-pointer -mabi=aapcs -fno-unroll-loops -ffast-math -ftree-vectorize" CACHE INTERNAL "c compiler flags")
set (CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -DSTM32F10X_HD -DUSE_STDPERIPH_DRIVER")

# Generate the target to static linker library
add_library (STM32F10x_StdPeriph_Driver ${DIR_STM32F10x_StdPeriph_Driver_SRCS})

# Make clean-all
add_custom_target (clean-all COMMAND rm -rf ${CMAKE_BINARY_DIR}/*)
