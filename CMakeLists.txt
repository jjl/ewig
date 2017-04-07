cmake_minimum_required(VERSION 2.6)
project(ewig)

set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED on)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall -Werror")
set(CMAKE_CXX_EXTENSIONS off)
set(CMAKE_EXPORT_COMPILE_COMMANDS on)

set(CURSES_NEED_NCURSES TRUE)
find_package(Curses REQUIRED)

include_directories(
  ${CURSES_INCLUDE_DIR}
  "${PROJECT_SOURCE_DIR}/src"
  "${PROJECT_SOURCE_DIR}/deps/immer")

add_executable(ewig
  src/main.cpp
  src/ewig/main.cpp)
target_link_libraries(ewig ${CURSES_LIBRARIES})