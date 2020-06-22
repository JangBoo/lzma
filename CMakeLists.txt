#=============================================================================
# lzma cmake configuration
# Copyright (c) 2005-2014, Coveo Solutions Inc.
#=============================================================================
CMAKE_MINIMUM_REQUIRED(VERSION 2.8.3 FATAL_ERROR)
SET(CMAKE_VERBOSE_MAKEFILE off)

#### Project Definition
PROJECT(lzma)
ADD_DEFINITIONS("-Wall -c -O2 -D_7ZIP_ST")

# Add files and include Paths
SET(HDR_FILES
    ../lzma/C/LzmaDec.h
    ../lzma/C/LzmaEnc.h
    ../lzma/C/LzFind.h
    ../lzma/C/Alloc.h
    ../lzma/C/7z.h
    ../lzma/C/7zBuf.h
    ../lzma/C/7zCrc.h
    ../lzma/C/Lzma2Dec.h
    ../lzma/C/CpuArch.h
    ../lzma/C/Bra.h
    ../lzma/C/Bcj2.h)
SET(SRC_FILES
    ../lzma/C/LzmaDec.c
    ../lzma/C/LzmaEnc.c
    ../lzma/C/LzFind.c
    ../lzma/C/Alloc.c
    ../lzma/C/7zIn.c
    ../lzma/C/7zDec.c
    ../lzma/C/7zBuf.c
    ../lzma/C/7zCrc.c
    ../lzma/C/7zCrcOpt.c
    ../lzma/C/7zStream.c
    ../lzma/C/Lzma2Dec.c
    ../lzma/C/CpuArch.c
    ../lzma/C/Bra.c
    ../lzma/C/Bcj2.c
    ../lzma/C/Bra86.c)

# Target Definition
ADD_LIBRARY(lzma SHARED
    ${SRC_FILES}
    ${HDR_FILES}
)