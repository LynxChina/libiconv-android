cmake_minimum_required(VERSION 3.4.1)

set(CMAKE_VERBOSE_MAKEFILE on)

set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -Wno-multichar -D_ANDROID  -DBUILDING_LIBICONV -DBUILDING_LIBCHARSET -DIN_LIBRARY")
#set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${PROJECT_SOURCE_DIR}/so/${ANDROID_ABI})
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

add_definitions(-DLIBDIR="c")

add_library(
    iconv

    SHARED

    src/main/jni/libiconv/lib/iconv.c
    src/main/jni/libiconv/libcharset/lib/localcharset.c
    src/main/jni/libiconv/lib/relocatable.c
)

include_directories(
    src/main/jni/libiconv/include/
    src/main/jni/libiconv/libcharset/include/
)

target_link_libraries(
    iconv

)