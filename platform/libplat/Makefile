
ifndef PLAT_INC_DIR_INNER
	PLAT_INC_DIR_INNER=$(WORKDIR)/libplat/include_inner
endif

CFLAGS += $(addprefix -I,$(PLAT_INC_DIR))
CFLAGS += $(addprefix -I,$(PLAT_INC_DIR_INNER))

dir_y :=
ifeq ($(PLAT_RELEASE), n)
	dir_y += src
endif
dir_y += lib

ifeq ($(COMPILE_SO), n)
	LOCAL_COMMON_FLAG := $(ARFLAGS)
	LOCAL_GEN := $(AR)
else
	LOCAL_COMMON_FLAG := -shared -fPIC -o
	LOCAL_GEN := $(CC)
endif

ifeq ($(COMPILE_DEMO), y)
	dir_y += demo
endif

all:
	@for i in $(dir_y); \
	do \
		$(MAKE) -C $$i; \
		if [ $$? -ne 0 ];then exit 1; fi \
	done

install:
	@for i in $(dir_y); \
	do \
		$(MAKE) -C $$i install; \
	done

clean:
	@for i in $(dir_y); \
	do \
		$(MAKE) -C $$i clean; \
	done

image:

demo:
	$(MAKE) -C demo


.PHONY: all install clean image demo
