
ifneq ($(KERNELRELEASE),)

obj-m += intel_sgx.o
intel_sgx-y := encl.o encls.o main.o reclaim.o driver.o ioctl.o

else

KDIR := /lib/modules/$(shell uname -r)/build
PWD  := $(shell pwd)
default:
	$(MAKE) -C $(KDIR) M=$(PWD) CFLAGS_MODULE="-include dcap.h -I$(PWD) -I$(PWD)/include" modules

endif

clean:
	rm -vrf *.o *.ko *.order *.symvers *.mod.c .tmp_versions .*.cmd *.o.ur-safe
