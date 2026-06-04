cmake_minimum_required(VERSION 3.10)

PROJECT(relayd C)
ADD_DEFINITIONS(-Os -Wall -Werror --std=gnu99 -g3)

ADD_EXECUTABLE(relayd
	src/relayd/main.c src/relayd/dhcp.c src/relayd/route.c
	src/libubox/uloop.c)

SET(CMAKE_INSTALL_PREFIX /usr)

INSTALL(TARGETS relayd
	RUNTIME DESTINATION sbin
)
