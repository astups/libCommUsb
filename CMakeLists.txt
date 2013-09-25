cmake_minimum_required(VERSION 2.6)
project(libCommUsb C)

set(CMAKE_C_FLAGS "-Wall")

find_package(PkgConfig REQUIRED)

pkg_check_modules(libusb REQUIRED libusb-1.0)
if(NOT libusb_FOUND)
	message(FATAL "Libusb is not found.")
endif(NOT libusb_FOUND)

add_executable(test_julien test_julien.c)
target_link_libraries(test_julien ${libusb_LIBRARIES})
