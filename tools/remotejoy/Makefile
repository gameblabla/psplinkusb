TARGET = remotejoy
OBJS = main.o kmode.o exports.o imports.o

# Use the kernel's small inbuilt libc
USE_KERNEL_LIBC = 1
# Use only kernel libraries
USE_KERNEL_LIBS = 1

INCDIR = 
CFLAGS = -Os -G0 -fsee -fomit-frame-pointer  -Wall -std=gnu99 -I../../usbhostfs -I../../psplink
ASFLAGS = $(CFLAGS)
CXXFLAGS = $(CFLAGS) -fno-exceptions -fno-rtti
LDFLAGS = -L../../libpsplink_driver -L../../libusbhostfs_driver
LIBS = -lpsppower_driver -lusbhostfs_driver -lpspdisplay_driver -lpsplink_driver 

ifdef BUILD_PLUGIN
CFLAGS += -DBUILD_PLUGIN
#OBJS += libs.o apihook.o
LIBS += -lpspusb_driver
endif

PSPSDK=$(shell psp-config --pspsdk-path)
include $(PSPSDK)/lib/build_prx.mak

