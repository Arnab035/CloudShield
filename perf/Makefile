KDIR := /lib/modules/$(shell uname -r)/build
CC = gcc
TARGET = event_open_user
obj-m += event_open_kernel.o

all: user gettime

kernel:
	$(MAKE) -C $(KDIR) SUBDIRS=$(shell pwd) modules

user: $(TARGET).c
	$(CC) -o $(TARGET) $(TARGET).c

gettimer: gettime.c
	$(CC) -o gettimer gettime.c

clean:
	rm -rf *.o *.ko *.mod.* *.cmd .module* modules* Module* .*.cmd .tmp* $(TARGET) gettime
