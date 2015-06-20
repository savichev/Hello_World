cmake_minimum_required(VERSION 2.8.4)
project(Hello_World)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

find_package (PkgConfig REQUIRED)
pkg_check_modules (GTK2 REQUIRED gtk+-2.0)

include_directories (${GTK2_INCLUDE_DIRS})
link_directories (${GTK2_LIBRARY_DIRS})

set(SOURCE_FILES main.cpp)
add_executable(Hello_World ${SOURCE_FILES})

add_definitions (${GTK2_CFLAGS_OTHER})
target_link_libraries (Hello_World ${GTK2_LIBRARIES})
