cmake_minimum_required(VERSION 3.11)

set(CMAKE_CXX_STANDARD 11)
file(GLOB ZLIB_SRC "src/extlibs/zlib/*.c")
file(GLOB LZMA_SRC "src/extlibs/lzma/unix/*.c")
file(GLOB BZIP2_SRC "src/extlibs/zlib/*.c")
file(GLOB_RECURSE SRC "src/*.cpp")

add_library(zip STATIC ${SRC} ${ZLIB_SRC} ${LZMA_SRC} ${BZIP2_SRC})
target_compile_options(zip PRIVATE "-fPIC" "-Wno-enum-conversion" "-O3")
