# Project file for the "test" server for the UVC Gadget driver.  We're doing 
# this with CMake instead of the original Makefile because we need to be
# a bit more flexible with build so it will build right as an OpenEmbedded 
# recipe- as well as make it easier to handle being hand-built in manual
# or cross-compile contexts...
PROJECT(uvc-gadget)
CMAKE_MINIMUM_REQUIRED(VERSION 2.8)

# Define our flags...
#SET(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -W -Wall -g -I$(KERNEL_DIR)/include -I$(KERNEL_DIR)/arch/$(ARCH)/include")
SET(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -W -Wall -g")

# Define our application...
ADD_EXECUTABLE(uvc-gadget uvc-gadget.c)

# Define our install path so that CMake knows we need a "make install"
INSTALL(PROGRAMS uvc-gadget DESTINATION sbin)

