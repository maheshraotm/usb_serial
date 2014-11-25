
obj-m:=chardriver_lowlevel.o


KERN_SRC :=/lib/modules/$(shell uname -r)/build
PWD:=$(shell pwd)

modules:
	make -C $(KERN_SRC) M=$(PWD) modules
	gcc ../app.c -o ../app -g
	
install:
	make -C $(KERN_SRC) M=$(PWD) modules_install
	depmod -a

clean:
	make -C $(KERN_SRC) M=$(PWD) clean
	rm -f ../app
	
	
