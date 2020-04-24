set (Boost_USE_STATIC_LIBS ON)
set (Boost_USE_MULTITHREADED ON)

set (BOOST_COMPONENTS system 
                      filesystem
                      program_options)

FIND_PACKAGE(Boost COMPONENTS ${BOOST_COMPONENTS} REQUIRED)

set(ZLIB_INCLUDE_DIR "${CMAKE_CURRENT_SOURCE_DIR}/zlib")
set(ZLIB_LIBRARY "${CMAKE_CURRENT_SOURCE_DIR}/zlib/build/Debug/zlibstaticd.lib")
set(LIBTOMCRYPT_INCLUDE_DIR "${CMAKE_CURRENT_SOURCE_DIR}/libtomcrypt/build/include")
set(LIBTOMCRYPT_LIBRARY "${CMAKE_CURRENT_SOURCE_DIR}/libtomcrypt/build/lib/tomcrypt.lib")
set(LIBB64_INCLUDE_DIR "${CMAKE_CURRENT_SOURCE_DIR}/libb64/include")
set(LIBZRIF_INCLUDE_DIR "${CMAKE_CURRENT_SOURCE_DIR}/libzrif/include")
set(PSVPFSPARSER_INCLUDE_DIR "${CMAKE_CURRENT_SOURCE_DIR}/psvpfsparser")
add_subdirectory(zlib)
add_subdirectory(libtomcrypt)
add_subdirectory(libb64)
add_subdirectory(libzrif)
add_subdirectory(psvpfsparser/cmake)
