PROJECT("cJSON" C)

CMAKE_MINIMUM_REQUIRED(VERSION 2.8)

SET(WARN_SWITCHES "-pipe -Wall -Werror -Wshadow -Wextra -Winit-self -Wstrict-overflow=5 -Wunused-result -Wcast-qual -Wcast-align -Wpointer-arith -Wformat=2 -Wwrite-strings -Wmissing-prototypes -pedantic")

SET(CMAKE_C_FLAGS "${WARN_SWITCHES} -fno-common" CACHE STRING "" FORCE)
SET(CMAKE_C_FLAGS_RELEASE "-O2 -fno-asynchronous-unwind-tables -fomit-frame-pointer" CACHE STRING "" FORCE)
SET(CMAKE_C_FLAGS_DEBUG "-O0 -ggdb" CACHE STRING "" FORCE)

IF(NOT CMAKE_BUILD_TYPE )
    SET(CMAKE_BUILD_TYPE RELEASE CACHE STRING "" FORCE)
ENDIF()


ADD_LIBRARY(cJSON STATIC cJSON.c)

