#
# Copyright (c) 2018 Nordic Semiconductor
#
# SPDX-License-Identifier: LicenseRef-Nordic-5-Clause
#

cmake_minimum_required(VERSION 3.20.0)

find_package(Zephyr REQUIRED HINTS $ENV{ZEPHYR_BASE})
project(lte-ble-gateway)

# NORDIC SDK APP END
zephyr_include_directories(src)

# NORDIC SDK APP 
FILE(GLOB app_sources src/*.c)
target_sources(app PRIVATE
	${app_sources}
)

# CUSTOM LIB
FILE(GLOB app_libary src/lib/*.c)
target_sources(app PRIVATE
	${app_libary}
)
