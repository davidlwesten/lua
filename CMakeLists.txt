cmake_minimum_required(VERSION 3.1..3.15)
if(${CMAKE_VERSION} VERSION_LESS 3.12)
    cmake_policy(VERSION ${CMAKE_MAJOR_VERSION}.${CMAKE_MINOR_VERSION})
endif()

project(lua VERSION 5.3 LANGUAGES C)
add_library(lua STATIC)
target_sources(lua PRIVATE
    #header files
    lapi.h
    lauxlib.h
    lcode.h
    lctype.h
    ldebug.h
    ldo.h
    lfunc.h
    lgc.h
    llex.h
    lmem.h
    lobject.h
    lopcodes.h
    lparser.h
    lstate.h
    lstring.h
    ltable.h
    ltm.h
    lundump.h
    lua.h
    lvm.h
    lzio.h
    ltests.h

    # source files
    lapi.c
    lauxlib.c
    lbaselib.c
    lcode.c
    lcorolib.c
    lctype.c
    ldblib.c
    ldebug.c
    ldo.c
    ldump.c
    lfunc.c
    lgc.c
    linit.c
    liolib.c
    llex.c
    lmathlib.c
    lmem.c
    loadlib.c
    lobject.c
    lopcodes.c
    loslib.c
    lparser.c
    lstate.c
    lstring.c
    lstrlib.c
    ltable.c
    ltablib.c
    ltests.c
    ltm.c
    lundump.c
    lutf8lib.c
    lvm.c
    lzio.c
    ltests.c)

target_compile_definitions(lua
    PUBLIC
    lua_c)

target_include_directories(lua
    PUBLIC
    $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/..>
    $<INSTALL_INTERFACE:include>)
