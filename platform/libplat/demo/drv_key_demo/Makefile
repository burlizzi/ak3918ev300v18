# appointed libs and their dir
LOCAL_SHARED_LIB:= 

ifeq ($(COMPILE_SO), y)
LOCAL_SHARED_LIB += plat_common plat_thread plat_drv
else
LOCAL_STATIC_LIB:= plat_drv plat_common  plat_thread
endif

LOCAL_LDFLAGS := -L$(PLAT_LIB_DIR)
LOCAL_LDFLAGS += $(addprefix $(PLAT_LIB_DIR)/,$(patsubst %,lib%.a,$(LOCAL_STATIC_LIB)))

LDFLAGS := $(LOCAL_LDFLAGS)
LDFLAGS += $(addprefix -l,$(patsubst lib%,%,$(LOCAL_SHARED_LIB)))
LDFLAGS += $(STD_LDFLAGS)

SRCS := $(wildcard *.c)
OBJS := $(patsubst %.c,%.o,$(SRCS))
TARGET := ak_drv_key_demo

all:$(TARGET)
	
$(TARGET):$(OBJS)
	$(LD) $^ $(LDFLAGS) -o $@
	$(STRIP) $@
	
%.o : %.c
	$(CC) $(CFLAGS) -c $^ -o $@
	@echo ""

install:
	@$(CP) $(TARGET) $(ROOTFS_BIN_DIR)
	@echo ""

clean:
	$(RM) *.o
	$(RM) $(TARGET)

.PHONY: all install clean
