CMAKE_MINIMUM_REQUIRED(VERSION 2.8.3 FATAL_ERROR)
SET(CMAKE_VERBOSE_MAKEFILE off)

#### Project Definition
PROJECT(lzma)

# Add files and include Paths

file(GLOB HDR_FILES
        ${PROJECT_SOURCE_DIR}/lzma/C/*.h)

file(GLOB SRC_FILES
        ${PROJECT_SOURCE_DIR}/lzma/C/*.c)


# Target Definition
ADD_LIBRARY(lzma SHARED
    ${SRC_FILES}
    ${HDR_FILES}
)


# Install library
install(TARGETS lzma DESTINATION lib)

# Install library headers
install(FILES ${HDR_FILES} DESTINATION include)