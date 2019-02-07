cmake_minimum_required(VERSION 3.5)
project(ttybus C)

set(CMAKE_C_STANDARD 11)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY "../out/")

include_directories(.)

add_executable(tty_bus tty_bus.c configure.h)
add_executable(tty_plug tty_plug.c configure.h)
add_executable(tty_fake tty_fake.c configure.h)
add_executable(tty_attach tty_attach.c configure.h)
add_executable(dpipe dpipe.c configure.h)


add_custom_target(BUILD_ALL)
add_dependencies(BUILD_ALL tty_attach tty_fake tty_plug tty_bus dpipe)
