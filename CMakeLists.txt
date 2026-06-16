file(GLOB_RECURSE FREERTOS_SOURCES
        "${CMAKE_CURRENT_SOURCE_DIR}/freertos-kernel/*.c"
        "${CMAKE_CURRENT_SOURCE_DIR}/freertos-kernel/include*.c"
        "${CMAKE_CURRENT_SOURCE_DIR}/freertos-kernel/template/*.c"
        "${CMAKE_CURRENT_SOURCE_DIR}/freertos-kernel/template/ARM_CM4F_3_priority_bits/*.c"
        "${CMAKE_CURRENT_SOURCE_DIR}/freertos-kernel/portable/GCC/ARM_CM4F/*.c"
        "${CMAKE_CURRENT_SOURCE_DIR}/freertos-kernel/portable/MemMang/*.c"
)

add_library(LPC54016-FreeRTOS
        STATIC ${FREERTOS_SOURCES}
)

target_include_directories(LPC54016-FreeRTOS PUBLIC
        ${CMAKE_CURRENT_SOURCE_DIR}/freertos-kernel/include
        ${CMAKE_CURRENT_SOURCE_DIR}/freertos-kernel/portable/GCC/ARM_CM4F
        ${CMAKE_CURRENT_SOURCE_DIR}/freertos-kernel/template
        ${CMAKE_CURRENT_SOURCE_DIR}/freertos-kernel/template/ARM_CM4F_3_priority_bits
)