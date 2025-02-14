cmake_minimum_required(VERSION 3.5)

project(compositor_app)

set(CMAKE_CXX_STANDARD 23)

include(FindPkgConfig)
pkg_check_modules(MIRAL miral REQUIRED)
pkg_check_modules(XKBCOMMON xkbcommon REQUIRED)

add_executable(compositor_app main.cpp)

target_include_directories(compositor_app  PUBLIC SYSTEM ${MIRAL_INCLUDE_DIRS})
target_link_libraries(compositor_app ${MIRAL_LDFLAGS})
target_link_libraries(compositor_app ${XKBCOMMON_LIBRARIES})
