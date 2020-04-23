project(zlib)

add_library(zlib INTERFACE)

target_include_directories(zlib INTERFACE "${CMAKE_CURRENT_SOURCE_DIR}")
if (WIN32)
    target_link_libraries(zlib INTERFACE 
        "${CMAKE_CURRENT_SOURCE_DIR}/build/Debug/zlibstaticd.lib")
elseif (APPLE)
    target_link_libraries(zlib INTERFACE 
        "${CMAKE_CURRENT_SOURCE_DIR}/build/Debug/libmacz.a")
elseif (UNIX)
    target_link_libraries(zlib INTERFACE
        "${CMAKE_CURRENT_SOURCE_DIR}/build/Debug/libz.a")
endif()
