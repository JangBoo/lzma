cmake_minimum_required(VERSION 2.8.3 FATAL_ERROR)

project(lzma)

ADD_DEFINITIONS("-Wall -c -O2 -D_7ZIP_ST")


file(GLOB HDR_FILES
        ${PROJECT_SOURCE_DIR}/lzma/C/*.h)

file(GLOB SRC_FILES
        ${PROJECT_SOURCE_DIR}/lzma/C/*.c)

add_library(lzma STATIC 
    ${SRC_FILES}
    ${HDR_FILES}
)

install(
    TARGETS lzma
    RUNTIME DESTINATION bin
    LIBRARY DESTINATION lib
    ARCHIVE DESTINATION lib
)

install(
    FILES ${HDR_FILES}
    DESTINATION include
)