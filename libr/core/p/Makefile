include ../../config.mk
include ../../../mk/platform.mk
include ../../../shlr/zip/deps.mk

CFLAGS+=-I../../include -Wall -shared ${PIC_CFLAGS} ${LDFLAGS_LIB} ${LDFLAGS_LINKPATH}..
CFLAGS+=-L../../util -lr_util -L../../reg -lr_reg -L.. -lr_core
#CFLAGS+=-L../../db -lr_db
CFLAGS+=-L../../cons -lr_cons -L../../bin -lr_bin
CFLAGS+=-L../../parse -lr_parse -L../../io -lr_io -L../../fs -lr_fs
CFLAGS+=-L../../magic -lr_magic -L../../hash -lr_hash -L../../config -lr_config
CFLAGS+=-L../../anal -lr_anal -L../../egg -lr_egg -L../../flag -lr_flag
CFLAGS+=-L../../syscall -lr_syscall -L../../socket -lr_socket -L../../search -lr_search
CFLAGS+= -L../../lang -lr_lang -L../../debug -lr_debug
CFLAGS+=-L../../bp -lr_bp -L../../reg -lr_reg -L../../asm -lr_asm

#CFLAGS+=../../../shlr/sdb/src/libsdb.a

LDFLAGS+=$(STOP)/sdb/src/libsdb.a
include $(STOP)/java/deps.mk
include $(STOP)/gdb/deps.mk
include $(STOP)/windbg/deps.mk
#CFLAGS+=-L../../anal -lr_anal -L../../core -lr_core
LDFLAGS+=${LINK}

ifeq ($(WITHPIC),1)
all: ${ALL_TARGETS}

ALL_TARGETS=
PLUGS=java.mk anal.mk
include $(PLUGS)

clean:
	-rm -f *.${EXT_SO} *.o ${STATIC_OBJ}

mrproper: clean
	-rm -f *.d

.PHONY: all clean foo mrproper
else
all clean mrproper:

.PHONY: all clean mrproper
endif
