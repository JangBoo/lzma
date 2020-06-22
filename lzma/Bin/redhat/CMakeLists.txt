#=============================================================================
# ilzma cmake configuration
# Copyright (c) 2005-2011, Coveo Solutions Inc.
#=============================================================================
CMAKE_MINIMUM_REQUIRED(VERSION 2.8.3 FATAL_ERROR)
SET(CMAKE_VERBOSE_MAKEFILE off)

#### Project Definition
PROJECT(lzma)

ADD_DEFINITIONS("-Wall -c -O2 -D_7ZIP_ST -DDEBUG -D_DEBUG")

# Add files and include Paths
SET(HDR_FILES
    ../../C/LzmaDec.h
    ../../C/LzmaEnc.h
    ../../C/LzFind.h
    ../../C/Alloc.h
    ../../C/7z.h
    ../../C/7zBuf.h
    ../../C/7zCrc.h
    ../../C/Lzma2Dec.h
    ../../C/CpuArch.h
    ../../C/Bra.h
    ../../C/Bcj2.h)

SET(SRC_FILES
    ../../C/LzmaDec.c
    ../../C/LzmaEnc.c
    ../../C/LzFind.c
    ../../C/Alloc.c
    ../../C/7zIn.c
    ../../C/7zDec.c
    ../../C/7zBuf.c
    ../../C/7zCrc.c
    ../../C/7zCrcOpt.c
    ../../C/7zStream.c
    ../../C/Lzma2Dec.c
    ../../C/CpuArch.c
    ../../C/Bra.c
    ../../C/Bcj2.c
    ../../C/Bra86.c)

# Target Definition
ADD_LIBRARY(lzmaD SHARED
    ${SRC_FILES}
    ${HDR_FILES}
)

