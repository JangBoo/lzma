cmake_minimum_required(VERSION 2.8.3 FATAL_ERROR)

project(lzma)

file(GLOB HDR_FILES
       
    ${PROJECT_SOURCE_DIR}/lzma/C/LzmaDec.h
    ${PROJECT_SOURCE_DIR}/lzma/C/LzmaEnc.h
    ${PROJECT_SOURCE_DIR}/lzma/C/LzFind.h
    ${PROJECT_SOURCE_DIR}/lzma/C/Alloc.h
    ${PROJECT_SOURCE_DIR}/lzma/C/7z.h
    ${PROJECT_SOURCE_DIR}/lzma/C/7zBuf.h
    ${PROJECT_SOURCE_DIR}/lzma/C/7zCrc.h
    ${PROJECT_SOURCE_DIR}/lzma/C/Lzma2Dec.h
    ${PROJECT_SOURCE_DIR}/lzma/C/CpuArch.h
    ${PROJECT_SOURCE_DIR}/lzma/C/Bra.h
    ${PROJECT_SOURCE_DIR}/lzma/C/Bcj2.h

)

file(GLOB SRC_FILES
       
   ${PROJECT_SOURCE_DIR}/lzma/C/LzmaDec.c
    ${PROJECT_SOURCE_DIR}/lzma/C/LzmaEnc.c
    ${PROJECT_SOURCE_DIR}/lzma/C/LzFind.c
    ${PROJECT_SOURCE_DIR}/lzma/C/Alloc.c
    ${PROJECT_SOURCE_DIR}/lzma/C/7zIn.c
    ${PROJECT_SOURCE_DIR}/lzma/C/7zDec.c
    ${PROJECT_SOURCE_DIR}/lzma/C/7zBuf.c
    ${PROJECT_SOURCE_DIR}/lzma/C/7zCrc.c
    ${PROJECT_SOURCE_DIR}/lzma/C/7zCrcOpt.c
    ${PROJECT_SOURCE_DIR}/lzma/C/7zStream.c
    ${PROJECT_SOURCE_DIR}/lzma/C/Lzma2Dec.c
    ${PROJECT_SOURCE_DIR}/lzma/C/CpuArch.c
    ${PROJECT_SOURCE_DIR}/lzma/C/Bra.c
    ${PROJECT_SOURCE_DIR}/lzma/C/Bcj2.c
    ${PROJECT_SOURCE_DIR}/lzma/C/Bra86.c)

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