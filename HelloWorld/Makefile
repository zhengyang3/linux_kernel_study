#这是一个通用的编译module的Makefile文件，只需要根据实际情况去修改obj-m这个变量的值就行了！
＃这是一个递归式的Makefile,"M=$(PUD)"这个命令行参数起到了决定性作用！
ifeq ($(KERNELRELEASE),)
KERNELDIR ?= /lib/modules/$(shell uname -r)/build
PWD := $(shell pwd)
modules: 
	$(MAKE) -C $(KERNELDIR) M=$(PWD) modules
modules_install:
	$(MAKE) -C $(KERNELDIR) M=$(PWD) modules_install

clean:
	rm -rf *.o *~ core .depend .*.cmd *.ko *.mod.c .tmp_versions
.PHONY: modules modules_install clean
else
obj-m := first_time.o
endif
