NAME=rz_crypto
RZ_DEPS=rz_hash rz_util
CFLAGS+=-DRZ_PLUGIN_INCORE

include ../config.mk

foo:
	@for TARGET in ${LIBSO} ${LIBAR} plugins ; do ${MAKE} $$TARGET ; done

include ${STATIC_CRYPTO_PLUGINS}
STATIC_OBJS=$(subst ..,p/..,$(subst crypto_,p/crypto_,$(STATIC_OBJ)))

OBJS=${STATIC_OBJS} crypto.o des.o

pre:
	@if [ ! -e ${LIBSO} ]; then rm -f ${STATIC_OBJS} ; fi

plugins:
	cd p && ${MAKE} all

include ../rules.mk
