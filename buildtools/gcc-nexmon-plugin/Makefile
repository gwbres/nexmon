-include $(NEXMON_ROOT)/Makefile.in

TARGET_PLUGIN_DIR = $(shell $(TARGET_CXX) -print-file-name=plugin)/include

CFLAGS = -std=c++11
CFLAGS += -fPIC
CFLAGS += -fno-rtti 
CFLAGS += -I$(TARGET_PLUGIN_DIR)
CFLAGS += -Wall 
CFLAGS += -Wno-literal-suffix

all: nexmon.so

nexmon.so: nexmon.o
	$(HOST_CXX) -shared -o $@ $^

nexmon.o: nexmon.c
	$(HOST_CXX) $(CFLAGS) -c -o $@ $^

clean:
	rm -f *.o *.so
