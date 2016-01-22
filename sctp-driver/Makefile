#
# Makefile for SCTP support code.
#
PWD=`pwd`
VER=`uname -r`
obj-$(CONFIG_IP_SCTP) += sctp_ha.o

sctp_ha-y := sm_statetable.o sm_statefuns.o sm_sideeffect.o \
	  protocol.o endpointola.o associola.o \
	  transport.o chunk.o sm_make_chunk.o ulpevent.o \
	  inqueue.o outqueue.o ulpqueue.o command.o \
	  tsnmap.o bind_addr.o socket.o primitive.o \
	  output.o input.o debug.o ssnmap.o auth.o \
	  sysctl.o proc.o 

sctp_ha-$(CONFIG_SCTP_DBG_OBJCNT) += objcnt.o


sctp_ha-$(subst m,y,$(CONFIG_IPV6))	+= ipv6.o

all:
	make -C /lib/modules/$(VER)/build M=$(PWD) modules

clean:
	rm -f *.o *.ko .*.cmd

