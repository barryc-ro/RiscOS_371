# Makefile for Internet
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name   Description
# ----       ----   -----------
# 18-Nov-94  AMcC   Created
# 05-Jan-95  AMcC   Added resources: rule and paths
# 21-Feb-95  AMcC   Resources now copied to AUNMsgs
# 22-Feb-95  AMcC   Added rules to build from sources
#

#
# Component specific options:
#
COMPONENT  = Internet
ROM_MODULE = aof.Internet
RDIR       = Resources
LDIR       = ${RDIR}.${LOCALE}
RESDIR    = ^.^.AUNMsgs.Resources.${Locale}.Resources.${COMPONENT}

VPATH     = @ ^.net ^.netinet ^.sys ^.riscos ^.lib ^.whoami

#
# Generic options:
#
AS      = objasm
CC      = cc
CMHG    = cmhg
CP      = copy
LD      = link
MKDIR   = cdir
RM      = remove
WIPE    = -wipe

AFLAGS   = -depend !Depend -I<Hdr$Dir>.Global.,<Hdr$Dir>.Interface. -Stamp -quit
CFLAGS   = -depend !Depend -pcc -zps1 -zM -ff ${INCLUDES} ${DFLAGS}
DFLAGS   = -DKERNEL -DINET -DGATEWAY
INCLUDES = -I^.^.include
CPFLAGS  = ~cfr~v
WFLAGS   = ~c~v

#
# Libraries
#
ANSILIB   = CLib:o.ansilib
CLIB      = CLIB:o.stubs
RLIB      = RISCOSLIB:o.risc_oslib
ROMCSTUBS = RISCOSLIB:o.romcstubs
ABSSYM    = RISC_OSLib:o.abssym

OBJS =\
 af.o\
 domain.o\
 globdata.o\
 if.o\
 if_ether.o\
 if_loop.o\
 if_module.o\
 in.o\
 inethdr.o\
 in_cksum.o\
 in_pcb.o\
 in_proto.o\
 ip_icmp.o\
 ip_input.o\
 ip_output.o\
 mbuf.o\
 mlink.o\
 module.o\
 poduleirq.o\
 raw_cb.o\
 raw_ip.o\
 raw_usrreq.o\
 route.o\
 setsoft.o\
 socket.o\
 socket1.o\
 socket_swi.o\
 tcp_debug.o\
 tcp_input.o\
 tcp_output.o\
 tcp_subr.o\
 tcp_timer.o\
 tcp_usrreq.o\
 udp_usrreq.o\
 unixenv.o\
 whoami.o

#
# Rule patterns
#
.c.o:;      ${CC} -c ${CFLAGS} -o $@ $<
.c.s:;      ${CC} -S ${CFLAGS} $<
.cmhg.o:;   ${CMHG} -o $@ $<
.s.o:;      ${AS} ${AFLAGS} $< $@

#
# Main rules:
#
rom: ${ROM_MODULE}
        @echo ${COMPONENT}: Module built (ROM)

install_rom: ${ROM_MODULE}
        ${CP} ${ROM_MODULE} ${INSTDIR}.${COMPONENT} ${CPFLAGS}
        @echo ${COMPONENT}: Module installed (ROM)

resources:
        @echo ${COMPONENT}: Resources in AUNMsgs

clean:
        ${RM} ${ROM_MODULE}
        ${WIPE} linked.* ${WFLAGS}
        ${WIPE} map.* ${WFLAGS}
        ${WIPE} o.* ${WFLAGS}
        @echo ${COMPONENT}: cleaned

${ROM_MODULE}: ${OBJS} ${ROMCSTUBS}
        ${LD} -o $@ -aof ${OBJS} ${ROMCSTUBS}

# final link for ROM Image (using given base address)
rom_link:
        ${MKDIR} linked
        ${MKDIR} map
        ${LD} -o linked.${COMPONENT} -bin -base ${ADDRESS} ${ROM_MODULE} ${ABSSYM} \
              -map > map.${COMPONENT}
        truncate map.${COMPONENT} linked.${COMPONENT}
        ${CP} linked.${COMPONENT} ${LINKDIR}.${COMPONENT} ${CPFLAGS}
        @echo ${COMPONENT}: rom_link complete

#---------------------------------------------------------------------------
# Dynamic dependencies:
o.af:	^.net.c.af
o.af:	^.^.include.sys.h.param
o.af:	^.^.include.sys.h.sysconf
o.af:	^.^.include.sys.^.machine.h.machparam
o.af:	^.^.include.sys.h.signal
o.af:	^.^.include.sys.h.types
o.af:	^.^.include.sys.h.protosw
o.af:	^.^.include.sys.h.socket
o.af:	^.^.include.sys.h.socketvar
o.af:	^.^.include.net.h.af
o.domain:	^.sys.c.domain
o.domain:	C:h.kernel
o.domain:	^.^.include.sys.h.param
o.domain:	^.^.include.sys.h.sysconf
o.domain:	^.^.include.sys.^.machine.h.machparam
o.domain:	^.^.include.sys.h.signal
o.domain:	^.^.include.sys.h.types
o.domain:	^.^.include.sys.h.socket
o.domain:	^.^.include.sys.h.protosw
o.domain:	^.^.include.sys.h.domain
o.domain:	^.^.include.sys.h.time
o.globdata:	^.riscos.c.globdata
o.globdata:	h.debug
o.globdata:	^.^.include.sys.h.param
o.globdata:	^.^.include.sys.h.sysconf
o.globdata:	^.^.include.sys.^.machine.h.machparam
o.globdata:	^.^.include.sys.h.signal
o.globdata:	^.^.include.sys.h.types
o.globdata:	^.^.include.sys.h.socket
o.globdata:	^.^.include.sys.h.domain
o.globdata:	^.^.include.sys.h.mbuf
o.globdata:	^.^.include.sys.h.msgbuf
o.globdata:	^.^.include.net.h.route
o.globdata:	^.^.include.net.h.if
o.globdata:	^.^.include.sys.h.mbuf
o.globdata:	^.^.include.net.^.net.h.if_arp
o.globdata:	^.^.include.sys.h.socket
o.globdata:	^.^.include.net.h.af
o.globdata:	^.^.include.net.h.raw_cb
o.globdata:	^.^.include.netinet.h.in_systm
o.globdata:	^.^.include.netinet.h.in
o.globdata:	^.^.include.netinet.h.in_var
o.globdata:	^.^.include.netinet.h.ip
o.globdata:	^.^.include.netinet.h.in_systm
o.globdata:	^.^.include.netinet.h.ip_var
o.globdata:	^.^.include.netinet.h.ip_icmp
o.globdata:	^.^.include.netinet.h.icmp_var
o.globdata:	^.^.include.netinet.h.in_pcb
o.globdata:	^.^.include.netinet.h.tcp
o.globdata:	^.^.include.netinet.h.tcpip
o.globdata:	^.^.include.netinet.h.tcp_timer
o.globdata:	^.^.include.netinet.h.tcp_var
o.globdata:	^.^.include.netinet.h.udp
o.globdata:	^.^.include.netinet.h.udp_var
o.if:	^.net.c.if
o.if:	C:h.kernel
o.if:	^.^.include.sys.h.param
o.if:	^.^.include.sys.h.sysconf
o.if:	^.^.include.sys.^.machine.h.machparam
o.if:	^.^.include.sys.h.signal
o.if:	^.^.include.sys.h.types
o.if:	^.^.include.sys.h.systm
o.if:	^.^.include.sys.h.dir
o.if:	^.^.include.sys.h.user
o.if:	^.^.include.sys.h.errno
o.if:	^.^.include.sys.^.h.errno
o.if:	C:h.kernel
o.if:	^.^.include.sys.h.mbuf
o.if:	^.^.include.sys.h.socket
o.if:	^.^.include.sys.h.socketvar
o.if:	^.^.include.sys.h.protosw
o.if:	^.^.include.sys.h.errno
o.if:	^.^.include.sys.h.ioctl
o.if:	^.^.include.sys.h.ttychars
o.if:	^.^.include.sys.h.ttydev
o.if:	^.^.include.net.h.if
o.if:	^.^.include.sys.h.mbuf
o.if:	^.^.include.net.^.net.h.if_arp
o.if:	^.^.include.sys.h.socket
o.if:	^.^.include.net.h.af
o.if:	h.ether
o.if_ether:	^.netinet.c.if_ether
o.if_ether:	C:h.kernel
o.if_ether:	^.^.include.sys.h.param
o.if_ether:	^.^.include.sys.h.sysconf
o.if_ether:	^.^.include.sys.^.machine.h.machparam
o.if_ether:	^.^.include.sys.h.signal
o.if_ether:	^.^.include.sys.h.types
o.if_ether:	^.^.include.sys.h.systm
o.if_ether:	^.^.include.sys.h.syslog
o.if_ether:	^.^.include.sys.h.time
o.if_ether:	^.^.include.sys.h.mbuf
o.if_ether:	^.^.include.sys.h.socket
o.if_ether:	^.^.include.sys.h.errno
o.if_ether:	^.^.include.sys.^.h.errno
o.if_ether:	C:h.kernel
o.if_ether:	^.^.include.sys.h.ioctl
o.if_ether:	^.^.include.sys.h.ttychars
o.if_ether:	^.^.include.sys.h.ttydev
o.if_ether:	^.^.include.net.h.if
o.if_ether:	^.^.include.sys.h.mbuf
o.if_ether:	^.^.include.net.^.net.h.if_arp
o.if_ether:	^.^.include.sys.h.socket
o.if_ether:	^.^.include.netinet.h.in
o.if_ether:	^.^.include.netinet.h.in_systm
o.if_ether:	^.^.include.netinet.h.ip
o.if_ether:	^.^.include.netinet.h.in_systm
o.if_ether:	^.^.include.netinet.h.if_ether
o.if_ether:	^.^.include.sys.h.types
o.if_ether:	^.^.include.sys.h.socket
o.if_ether:	^.^.include.net.h.if
o.if_ether:	^.^.include.net.h.if_arp
o.if_ether:	^.^.include.netinet.h.in
o.if_ether:	h.debug
o.if_loop:	^.net.c.if_loop
o.if_loop:	^.^.include.sys.h.param
o.if_loop:	^.^.include.sys.h.sysconf
o.if_loop:	^.^.include.sys.^.machine.h.machparam
o.if_loop:	^.^.include.sys.h.signal
o.if_loop:	^.^.include.sys.h.types
o.if_loop:	^.^.include.sys.h.systm
o.if_loop:	^.^.include.sys.h.mbuf
o.if_loop:	^.^.include.sys.h.socket
o.if_loop:	^.^.include.sys.h.errno
o.if_loop:	^.^.include.sys.^.h.errno
o.if_loop:	C:h.kernel
o.if_loop:	^.^.include.sys.h.ioctl
o.if_loop:	^.^.include.sys.h.ttychars
o.if_loop:	^.^.include.sys.h.ttydev
o.if_loop:	^.^.include.sys.h.dcistructs
o.if_loop:	^.^.include.net.h.if
o.if_loop:	^.^.include.sys.h.mbuf
o.if_loop:	^.^.include.net.^.net.h.if_arp
o.if_loop:	^.^.include.sys.h.socket
o.if_loop:	^.^.include.net.h.netisr
o.if_loop:	^.^.include.net.h.route
o.if_loop:	^.^.include.netinet.h.in
o.if_loop:	^.^.include.netinet.h.in_systm
o.if_loop:	^.^.include.netinet.h.in_var
o.if_loop:	^.^.include.netinet.h.ip
o.if_loop:	^.^.include.netinet.h.in_systm
o.if_loop:	^.^.include.netinet.h.if_ether
o.if_loop:	^.^.include.sys.h.types
o.if_loop:	^.^.include.sys.h.socket
o.if_loop:	^.^.include.net.h.if
o.if_loop:	^.^.include.net.h.if_arp
o.if_loop:	^.^.include.netinet.h.in
o.if_module:	^.net.c.if_module
o.if_module:	C:h.kernel
o.if_module:	C:h.swis
o.if_module:	^.^.include.sys.h.param
o.if_module:	^.^.include.sys.h.sysconf
o.if_module:	^.^.include.sys.^.machine.h.machparam
o.if_module:	^.^.include.sys.h.signal
o.if_module:	^.^.include.sys.h.types
o.if_module:	^.^.include.sys.h.systm
o.if_module:	^.^.include.sys.h.socket
o.if_module:	^.^.include.sys.h.socketvar
o.if_module:	^.^.include.sys.h.protosw
o.if_module:	^.^.include.sys.h.errno
o.if_module:	^.^.include.sys.^.h.errno
o.if_module:	C:h.kernel
o.if_module:	^.^.include.sys.h.dir
o.if_module:	^.^.include.sys.h.ioctl
o.if_module:	^.^.include.sys.h.ttychars
o.if_module:	^.^.include.sys.h.ttydev
o.if_module:	^.^.include.sys.h.user
o.if_module:	^.^.include.sys.h.errno
o.if_module:	^.^.include.sys.h.mbuf
o.if_module:	^.^.include.sys.h.dcistructs
o.if_module:	^.^.include.net.h.if
o.if_module:	^.^.include.sys.h.mbuf
o.if_module:	^.^.include.net.^.net.h.if_arp
o.if_module:	^.^.include.sys.h.socket
o.if_module:	^.^.include.net.h.af
o.if_module:	^.^.include.net.h.netisr
o.if_module:	^.^.include.netinet.h.in
o.if_module:	^.^.include.netinet.h.in_systm
o.if_module:	^.^.include.netinet.h.in_var
o.if_module:	^.^.include.netinet.h.ip
o.if_module:	^.^.include.netinet.h.in_systm
o.if_module:	^.^.include.netinet.h.if_ether
o.if_module:	^.^.include.sys.h.types
o.if_module:	^.^.include.sys.h.socket
o.if_module:	^.^.include.net.h.if
o.if_module:	^.^.include.net.h.if_arp
o.if_module:	^.^.include.netinet.h.in
o.if_module:	h.module
o.if_module:	^.^.include.h.svcdebug
o.if_module:	h.debug
o.in:	^.netinet.c.in
o.in:	^.^.include.sys.h.param
o.in:	^.^.include.sys.h.sysconf
o.in:	^.^.include.sys.^.machine.h.machparam
o.in:	^.^.include.sys.h.signal
o.in:	^.^.include.sys.h.types
o.in:	^.^.include.sys.h.dir
o.in:	^.^.include.sys.h.user
o.in:	^.^.include.sys.h.errno
o.in:	^.^.include.sys.^.h.errno
o.in:	C:h.kernel
o.in:	^.^.include.sys.h.ioctl
o.in:	^.^.include.sys.h.ttychars
o.in:	^.^.include.sys.h.ttydev
o.in:	^.^.include.sys.h.mbuf
o.in:	^.^.include.sys.h.protosw
o.in:	^.^.include.sys.h.socket
o.in:	^.^.include.sys.h.socketvar
o.in:	^.^.include.sys.h.uio
o.in:	^.^.include.net.h.if
o.in:	^.^.include.sys.h.mbuf
o.in:	^.^.include.net.^.net.h.if_arp
o.in:	^.^.include.sys.h.socket
o.in:	^.^.include.net.h.route
o.in:	^.^.include.net.h.af
o.in:	^.^.include.netinet.h.in
o.in:	^.^.include.netinet.h.in_var
o.in:	^.^.include.netinet.h.in_systm
o.in_cksum:	^.netinet.c.in_cksum
o.in_cksum:	^.^.include.sys.h.param
o.in_cksum:	^.^.include.sys.h.sysconf
o.in_cksum:	^.^.include.sys.^.machine.h.machparam
o.in_cksum:	^.^.include.sys.h.signal
o.in_cksum:	^.^.include.sys.h.types
o.in_cksum:	^.^.include.sys.h.types
o.in_cksum:	^.^.include.sys.h.mbuf
o.in_cksum:	^.^.include.netinet.h.in
o.in_cksum:	^.^.include.netinet.h.in_systm
o.in_pcb:	^.netinet.c.in_pcb
o.in_pcb:	^.^.include.sys.h.param
o.in_pcb:	^.^.include.sys.h.sysconf
o.in_pcb:	^.^.include.sys.^.machine.h.machparam
o.in_pcb:	^.^.include.sys.h.signal
o.in_pcb:	^.^.include.sys.h.types
o.in_pcb:	^.^.include.sys.h.systm
o.in_pcb:	^.^.include.sys.h.dir
o.in_pcb:	^.^.include.sys.h.user
o.in_pcb:	^.^.include.sys.h.errno
o.in_pcb:	^.^.include.sys.^.h.errno
o.in_pcb:	C:h.kernel
o.in_pcb:	^.^.include.sys.h.mbuf
o.in_pcb:	^.^.include.sys.h.socket
o.in_pcb:	^.^.include.sys.h.socketvar
o.in_pcb:	^.^.include.sys.h.ioctl
o.in_pcb:	^.^.include.sys.h.ttychars
o.in_pcb:	^.^.include.sys.h.ttydev
o.in_pcb:	^.^.include.sys.h.protosw
o.in_pcb:	^.^.include.net.h.if
o.in_pcb:	^.^.include.sys.h.mbuf
o.in_pcb:	^.^.include.net.^.net.h.if_arp
o.in_pcb:	^.^.include.sys.h.socket
o.in_pcb:	^.^.include.net.h.route
o.in_pcb:	^.^.include.netinet.h.in
o.in_pcb:	^.^.include.netinet.h.in_systm
o.in_pcb:	^.^.include.netinet.h.in_pcb
o.in_pcb:	^.^.include.netinet.h.in_var
o.in_proto:	^.netinet.c.in_proto
o.in_proto:	^.^.include.sys.h.param
o.in_proto:	^.^.include.sys.h.sysconf
o.in_proto:	^.^.include.sys.^.machine.h.machparam
o.in_proto:	^.^.include.sys.h.signal
o.in_proto:	^.^.include.sys.h.types
o.in_proto:	^.^.include.sys.h.socket
o.in_proto:	^.^.include.sys.h.protosw
o.in_proto:	^.^.include.sys.h.domain
o.in_proto:	^.^.include.sys.h.mbuf
o.in_proto:	^.^.include.netinet.h.in
o.in_proto:	^.^.include.netinet.h.in_systm
o.ip_icmp:	^.netinet.c.ip_icmp
o.ip_icmp:	C:h.kernel
o.ip_icmp:	^.^.include.sys.h.param
o.ip_icmp:	^.^.include.sys.h.sysconf
o.ip_icmp:	^.^.include.sys.^.machine.h.machparam
o.ip_icmp:	^.^.include.sys.h.signal
o.ip_icmp:	^.^.include.sys.h.types
o.ip_icmp:	^.^.include.sys.h.systm
o.ip_icmp:	^.^.include.sys.h.time
o.ip_icmp:	^.^.include.sys.h.mbuf
o.ip_icmp:	^.^.include.sys.h.protosw
o.ip_icmp:	^.^.include.sys.h.socket
o.ip_icmp:	^.^.include.net.h.route
o.ip_icmp:	^.^.include.net.h.if
o.ip_icmp:	^.^.include.sys.h.mbuf
o.ip_icmp:	^.^.include.net.^.net.h.if_arp
o.ip_icmp:	^.^.include.sys.h.socket
o.ip_icmp:	^.^.include.netinet.h.in
o.ip_icmp:	^.^.include.netinet.h.in_systm
o.ip_icmp:	^.^.include.netinet.h.in_var
o.ip_icmp:	^.^.include.netinet.h.ip
o.ip_icmp:	^.^.include.netinet.h.in_systm
o.ip_icmp:	^.^.include.netinet.h.ip_icmp
o.ip_icmp:	^.^.include.netinet.h.icmp_var
o.ip_icmp:	^.^.include.h.svcdebug
o.ip_input:	^.netinet.c.ip_input
o.ip_input:	C:h.kernel
o.ip_input:	^.^.include.sys.h.param
o.ip_input:	^.^.include.sys.h.sysconf
o.ip_input:	^.^.include.sys.^.machine.h.machparam
o.ip_input:	^.^.include.sys.h.signal
o.ip_input:	^.^.include.sys.h.types
o.ip_input:	^.^.include.sys.h.systm
o.ip_input:	^.^.include.sys.h.time
o.ip_input:	^.^.include.sys.h.mbuf
o.ip_input:	^.^.include.sys.h.domain
o.ip_input:	^.^.include.sys.h.protosw
o.ip_input:	^.^.include.sys.h.socket
o.ip_input:	^.^.include.sys.h.errno
o.ip_input:	^.^.include.sys.^.h.errno
o.ip_input:	C:h.kernel
o.ip_input:	^.^.include.net.h.if
o.ip_input:	^.^.include.sys.h.mbuf
o.ip_input:	^.^.include.net.^.net.h.if_arp
o.ip_input:	^.^.include.sys.h.socket
o.ip_input:	^.^.include.net.h.route
o.ip_input:	^.^.include.netinet.h.in
o.ip_input:	^.^.include.netinet.h.in_pcb
o.ip_input:	^.^.include.netinet.h.in_systm
o.ip_input:	^.^.include.netinet.h.in_var
o.ip_input:	^.^.include.netinet.h.ip
o.ip_input:	^.^.include.netinet.h.in_systm
o.ip_input:	^.^.include.netinet.h.ip_var
o.ip_input:	^.^.include.netinet.h.ip_icmp
o.ip_input:	^.^.include.netinet.h.tcp
o.ip_input:	^.^.include.h.svcdebug
o.ip_input:	h.debug
o.ip_output:	^.netinet.c.ip_output
o.ip_output:	^.^.include.sys.h.param
o.ip_output:	^.^.include.sys.h.sysconf
o.ip_output:	^.^.include.sys.^.machine.h.machparam
o.ip_output:	^.^.include.sys.h.signal
o.ip_output:	^.^.include.sys.h.types
o.ip_output:	^.^.include.sys.h.mbuf
o.ip_output:	^.^.include.sys.h.errno
o.ip_output:	^.^.include.sys.^.h.errno
o.ip_output:	C:h.kernel
o.ip_output:	^.^.include.sys.h.protosw
o.ip_output:	^.^.include.sys.h.socket
o.ip_output:	^.^.include.sys.h.socketvar
o.ip_output:	^.^.include.net.h.if
o.ip_output:	^.^.include.sys.h.mbuf
o.ip_output:	^.^.include.net.^.net.h.if_arp
o.ip_output:	^.^.include.sys.h.socket
o.ip_output:	^.^.include.net.h.route
o.ip_output:	^.^.include.netinet.h.in
o.ip_output:	^.^.include.netinet.h.in_pcb
o.ip_output:	^.^.include.netinet.h.in_systm
o.ip_output:	^.^.include.netinet.h.in_var
o.ip_output:	^.^.include.netinet.h.ip
o.ip_output:	^.^.include.netinet.h.in_systm
o.ip_output:	^.^.include.netinet.h.ip_var
o.ip_output:	^.^.include.h.svcdebug
o.mbuf:	^.riscos.c.mbuf
o.mbuf:	C:h.kernel
o.mbuf:	C:h.swis
o.mbuf:	^.^.include.sys.h.param
o.mbuf:	^.^.include.sys.h.sysconf
o.mbuf:	^.^.include.sys.^.machine.h.machparam
o.mbuf:	^.^.include.sys.h.signal
o.mbuf:	^.^.include.sys.h.types
o.mbuf:	^.^.include.sys.h.errno
o.mbuf:	^.^.include.sys.^.h.errno
o.mbuf:	C:h.kernel
o.mbuf:	^.^.include.sys.h.mbuf
o.mbuf:	^.^.include.netinet.h.if_ether
o.mbuf:	^.^.include.sys.h.types
o.mbuf:	^.^.include.sys.h.socket
o.mbuf:	^.^.include.net.h.if
o.mbuf:	^.^.include.sys.h.mbuf
o.mbuf:	^.^.include.net.^.net.h.if_arp
o.mbuf:	^.^.include.sys.h.socket
o.mbuf:	^.^.include.net.h.if_arp
o.mbuf:	^.^.include.netinet.h.in
o.mlink: ^.riscos.s.mlink
o.mlink: <Hdr$Dir>.Global.ListOpts
o.mlink: <Hdr$Dir>.Global.Macros
o.mlink: <Hdr$Dir>.Global.System
o.mlink: Hdr:SWIs
o.mlink: Hdr:CPU.Generic26
o.mlink: Hdr:IO.GenericIO
o.mlink: Hdr:RISCOS
o.mlink: <Hdr$Dir>.Interface.EnvNumbers
o.mlink: <Hdr$Dir>.Interface.ModHand
o.module:	^.riscos.c.module
o.module:	C:h.kernel
o.module:	C:h.swis
o.module:	^.^.include.h.int_hndlr
o.module:	^.^.include.sys.h.param
o.module:	^.^.include.sys.h.sysconf
o.module:	^.^.include.sys.^.machine.h.machparam
o.module:	^.^.include.sys.h.signal
o.module:	^.^.include.sys.h.types
o.module:	^.^.include.sys.h.errno
o.module:	^.^.include.sys.^.h.errno
o.module:	C:h.kernel
o.module:	^.^.include.sys.h.dcistructs
o.module:	^.^.include.sys.h.types
o.module:	^.^.include.sys.h.socket
o.module:	^.^.include.sys.h.mbuf
o.module:	^.^.include.net.h.if
o.module:	^.^.include.sys.h.mbuf
o.module:	^.^.include.net.^.net.h.if_arp
o.module:	^.^.include.sys.h.socket
o.module:	^.^.include.net.h.route
o.module:	^.^.include.net.h.netisr
o.module:	^.^.include.netinet.h.in
o.module:	^.^.include.netinet.h.ip
o.module:	^.^.include.netinet.h.in_systm
o.module:	^.^.include.netinet.h.ip_icmp
o.module:	^.^.include.netinet.h.if_ether
o.module:	^.^.include.sys.h.types
o.module:	^.^.include.sys.h.socket
o.module:	^.^.include.net.h.if
o.module:	^.^.include.net.h.if_arp
o.module:	^.^.include.netinet.h.in
o.module:	^.^.include.netinet.h.udp
o.module:	^.^.include.netinet.h.in_pcb
o.module:	^.^.include.netinet.h.tcp
o.module:	^.^.include.netinet.h.tcp_timer
o.module:	^.^.include.netinet.h.in_var
o.module:	^.^.include.netinet.h.icmp_var
o.module:	h.module
o.module:	^.^.include.h.instats
o.module:	^.^.include.netinet.h.in
o.module:	^.^.include.netinet.h.ip
o.module:	^.^.include.netinet.h.ip_var
o.module:	^.^.include.netinet.h.tcp_var
o.module:	^.^.include.netinet.h.udp_var
o.module:	^.^.include.h.svcdebug
o.module:	h.debug
o.poduleirq: s.poduleirq
o.poduleirq: <Hdr$Dir>.Global.ListOpts
o.poduleirq: <Hdr$Dir>.Global.Macros
o.poduleirq: <Hdr$Dir>.Global.System
o.poduleirq: Hdr:SWIs
o.poduleirq: Hdr:CPU.Generic26
o.poduleirq: Hdr:IO.GenericIO
o.poduleirq: Hdr:RISCOS
o.poduleirq: <Hdr$Dir>.Interface.EnvNumbers
o.poduleirq: <Hdr$Dir>.Interface.ModHand
o.raw_cb:	^.net.c.raw_cb
o.raw_cb:	^.^.include.sys.h.param
o.raw_cb:	^.^.include.sys.h.sysconf
o.raw_cb:	^.^.include.sys.^.machine.h.machparam
o.raw_cb:	^.^.include.sys.h.signal
o.raw_cb:	^.^.include.sys.h.types
o.raw_cb:	^.^.include.sys.h.systm
o.raw_cb:	^.^.include.sys.h.mbuf
o.raw_cb:	^.^.include.sys.h.socket
o.raw_cb:	^.^.include.sys.h.socketvar
o.raw_cb:	^.^.include.sys.h.domain
o.raw_cb:	^.^.include.sys.h.protosw
o.raw_cb:	^.^.include.sys.h.errno
o.raw_cb:	^.^.include.sys.^.h.errno
o.raw_cb:	C:h.kernel
o.raw_cb:	^.^.include.net.h.route
o.raw_cb:	^.^.include.net.h.raw_cb
o.raw_cb:	^.^.include.net.h.if
o.raw_cb:	^.^.include.sys.h.mbuf
o.raw_cb:	^.^.include.net.^.net.h.if_arp
o.raw_cb:	^.^.include.sys.h.socket
o.raw_cb:	^.^.include.netinet.h.in
o.raw_ip:	^.netinet.c.raw_ip
o.raw_ip:	^.^.include.sys.h.param
o.raw_ip:	^.^.include.sys.h.sysconf
o.raw_ip:	^.^.include.sys.^.machine.h.machparam
o.raw_ip:	^.^.include.sys.h.signal
o.raw_ip:	^.^.include.sys.h.types
o.raw_ip:	^.^.include.sys.h.mbuf
o.raw_ip:	^.^.include.sys.h.socket
o.raw_ip:	^.^.include.sys.h.protosw
o.raw_ip:	^.^.include.sys.h.socketvar
o.raw_ip:	^.^.include.sys.h.errno
o.raw_ip:	^.^.include.sys.^.h.errno
o.raw_ip:	C:h.kernel
o.raw_ip:	^.^.include.net.h.if
o.raw_ip:	^.^.include.sys.h.mbuf
o.raw_ip:	^.^.include.net.^.net.h.if_arp
o.raw_ip:	^.^.include.sys.h.socket
o.raw_ip:	^.^.include.net.h.route
o.raw_ip:	^.^.include.net.h.raw_cb
o.raw_ip:	^.^.include.netinet.h.in
o.raw_ip:	^.^.include.netinet.h.in_systm
o.raw_ip:	^.^.include.netinet.h.ip
o.raw_ip:	^.^.include.netinet.h.in_systm
o.raw_ip:	^.^.include.netinet.h.ip_var
o.raw_usrreq:	^.net.c.raw_usrreq
o.raw_usrreq:	^.^.include.sys.h.param
o.raw_usrreq:	^.^.include.sys.h.sysconf
o.raw_usrreq:	^.^.include.sys.^.machine.h.machparam
o.raw_usrreq:	^.^.include.sys.h.signal
o.raw_usrreq:	^.^.include.sys.h.types
o.raw_usrreq:	^.^.include.sys.h.mbuf
o.raw_usrreq:	^.^.include.sys.h.domain
o.raw_usrreq:	^.^.include.sys.h.protosw
o.raw_usrreq:	^.^.include.sys.h.socket
o.raw_usrreq:	^.^.include.sys.h.socketvar
o.raw_usrreq:	^.^.include.sys.h.errno
o.raw_usrreq:	^.^.include.sys.^.h.errno
o.raw_usrreq:	C:h.kernel
o.raw_usrreq:	^.^.include.net.h.if
o.raw_usrreq:	^.^.include.sys.h.mbuf
o.raw_usrreq:	^.^.include.net.^.net.h.if_arp
o.raw_usrreq:	^.^.include.sys.h.socket
o.raw_usrreq:	^.^.include.net.h.route
o.raw_usrreq:	^.^.include.net.h.netisr
o.raw_usrreq:	^.^.include.net.h.raw_cb
o.route:	^.net.c.route
o.route:	^.^.include.sys.h.param
o.route:	^.^.include.sys.h.sysconf
o.route:	^.^.include.sys.^.machine.h.machparam
o.route:	^.^.include.sys.h.signal
o.route:	^.^.include.sys.h.types
o.route:	^.^.include.sys.h.systm
o.route:	^.^.include.sys.h.dir
o.route:	^.^.include.sys.h.user
o.route:	^.^.include.sys.h.errno
o.route:	^.^.include.sys.^.h.errno
o.route:	C:h.kernel
o.route:	^.^.include.sys.h.mbuf
o.route:	^.^.include.sys.h.protosw
o.route:	^.^.include.sys.h.socket
o.route:	^.^.include.sys.h.ioctl
o.route:	^.^.include.sys.h.ttychars
o.route:	^.^.include.sys.h.ttydev
o.route:	^.^.include.sys.h.errno
o.route:	^.^.include.net.h.if
o.route:	^.^.include.sys.h.mbuf
o.route:	^.^.include.net.^.net.h.if_arp
o.route:	^.^.include.sys.h.socket
o.route:	^.^.include.net.h.af
o.route:	^.^.include.net.h.route
o.setsoft:	^.riscos.c.setsoft
o.setsoft:	C:h.kernel
o.setsoft:	^.^.include.h.ioc
o.setsoft:	^.^.include.h.int_hndlr
o.setsoft:	^.^.include.sys.h.param
o.setsoft:	^.^.include.sys.h.sysconf
o.setsoft:	^.^.include.sys.^.machine.h.machparam
o.setsoft:	^.^.include.sys.h.signal
o.setsoft:	^.^.include.sys.h.types
o.setsoft:	^.^.include.sys.h.time
o.setsoft:	^.^.include.net.h.netisr
o.setsoft:	h.module
o.socket:	^.sys.c.socket
o.socket:	^.^.include.sys.h.param
o.socket:	^.^.include.sys.h.sysconf
o.socket:	^.^.include.sys.^.machine.h.machparam
o.socket:	^.^.include.sys.h.signal
o.socket:	^.^.include.sys.h.types
o.socket:	^.^.include.sys.h.dir
o.socket:	^.^.include.sys.h.file
o.socket:	^.^.include.sys.h.fcntl
o.socket:	^.^.include.sys.h.uio
o.socket:	^.^.include.sys.h.user
o.socket:	^.^.include.sys.h.errno
o.socket:	^.^.include.sys.^.h.errno
o.socket:	C:h.kernel
o.socket:	^.^.include.sys.h.proc
o.socket:	^.^.include.sys.h.mbuf
o.socket:	^.^.include.sys.h.domain
o.socket:	^.^.include.sys.h.protosw
o.socket:	^.^.include.sys.h.socket
o.socket:	^.^.include.sys.h.socketvar
o.socket:	^.^.include.h.svcdebug
o.socket:	h.debug
o.socket1:	^.sys.c.socket1
o.socket1:	^.^.include.sys.h.param
o.socket1:	^.^.include.sys.h.sysconf
o.socket1:	^.^.include.sys.^.machine.h.machparam
o.socket1:	^.^.include.sys.h.signal
o.socket1:	^.^.include.sys.h.types
o.socket1:	^.^.include.sys.h.systm
o.socket1:	^.^.include.sys.h.dir
o.socket1:	^.^.include.sys.h.file
o.socket1:	^.^.include.sys.h.fcntl
o.socket1:	^.^.include.sys.h.buf
o.socket1:	^.^.include.sys.h.user
o.socket1:	^.^.include.sys.h.errno
o.socket1:	^.^.include.sys.^.h.errno
o.socket1:	C:h.kernel
o.socket1:	^.^.include.sys.h.proc
o.socket1:	^.^.include.sys.h.mbuf
o.socket1:	^.^.include.sys.h.protosw
o.socket1:	^.^.include.sys.h.socket
o.socket1:	^.^.include.sys.h.socketvar
o.socket1:	h.debug
o.socket_swi:	^.riscos.c.socket_swi
o.socket_swi:	^.^.include.sys.h.param
o.socket_swi:	^.^.include.sys.h.sysconf
o.socket_swi:	^.^.include.sys.^.machine.h.machparam
o.socket_swi:	^.^.include.sys.h.signal
o.socket_swi:	^.^.include.sys.h.types
o.socket_swi:	^.^.include.sys.h.errno
o.socket_swi:	^.^.include.sys.^.h.errno
o.socket_swi:	C:h.kernel
o.socket_swi:	^.^.include.sys.h.uio
o.socket_swi:	^.^.include.sys.h.mbuf
o.socket_swi:	^.^.include.sys.h.domain
o.socket_swi:	^.^.include.sys.h.protosw
o.socket_swi:	^.^.include.sys.h.socket
o.socket_swi:	^.^.include.sys.h.socketvar
o.socket_swi:	^.^.include.sys.h.ioctl
o.socket_swi:	^.^.include.sys.h.ttychars
o.socket_swi:	^.^.include.sys.h.ttydev
o.socket_swi:	^.^.include.sys.h.stat
o.socket_swi:	^.^.include.sys.h.time
o.socket_swi:	^.^.include.sys.h.file
o.socket_swi:	^.^.include.sys.h.fcntl
o.socket_swi:	h.debug
o.tcp_debug:	^.netinet.c.tcp_debug
o.tcp_input:	^.netinet.c.tcp_input
o.tcp_input:	^.^.include.sys.h.param
o.tcp_input:	^.^.include.sys.h.sysconf
o.tcp_input:	^.^.include.sys.^.machine.h.machparam
o.tcp_input:	^.^.include.sys.h.signal
o.tcp_input:	^.^.include.sys.h.types
o.tcp_input:	^.^.include.sys.h.systm
o.tcp_input:	^.^.include.sys.h.mbuf
o.tcp_input:	^.^.include.sys.h.protosw
o.tcp_input:	^.^.include.sys.h.socket
o.tcp_input:	^.^.include.sys.h.socketvar
o.tcp_input:	^.^.include.sys.h.errno
o.tcp_input:	^.^.include.sys.^.h.errno
o.tcp_input:	C:h.kernel
o.tcp_input:	^.^.include.net.h.if
o.tcp_input:	^.^.include.sys.h.mbuf
o.tcp_input:	^.^.include.net.^.net.h.if_arp
o.tcp_input:	^.^.include.sys.h.socket
o.tcp_input:	^.^.include.net.h.route
o.tcp_input:	^.^.include.netinet.h.in
o.tcp_input:	^.^.include.netinet.h.in_pcb
o.tcp_input:	^.^.include.netinet.h.in_systm
o.tcp_input:	^.^.include.netinet.h.ip
o.tcp_input:	^.^.include.netinet.h.in_systm
o.tcp_input:	^.^.include.netinet.h.ip_var
o.tcp_input:	^.^.include.netinet.h.tcp
o.tcp_input:	^.^.include.netinet.h.tcp_fsm
o.tcp_input:	^.^.include.netinet.h.tcp_seq
o.tcp_input:	^.^.include.netinet.h.tcp_timer
o.tcp_input:	^.^.include.netinet.h.tcp_var
o.tcp_input:	^.^.include.netinet.h.tcpip
o.tcp_input:	^.^.include.netinet.h.tcp_debug
o.tcp_input:	h.debug
o.tcp_output:	^.netinet.c.tcp_output
o.tcp_output:	^.^.include.sys.h.param
o.tcp_output:	^.^.include.sys.h.sysconf
o.tcp_output:	^.^.include.sys.^.machine.h.machparam
o.tcp_output:	^.^.include.sys.h.signal
o.tcp_output:	^.^.include.sys.h.types
o.tcp_output:	^.^.include.sys.h.systm
o.tcp_output:	^.^.include.sys.h.mbuf
o.tcp_output:	^.^.include.sys.h.protosw
o.tcp_output:	^.^.include.sys.h.socket
o.tcp_output:	^.^.include.sys.h.socketvar
o.tcp_output:	^.^.include.sys.h.errno
o.tcp_output:	^.^.include.sys.^.h.errno
o.tcp_output:	C:h.kernel
o.tcp_output:	^.^.include.net.h.route
o.tcp_output:	^.^.include.netinet.h.in
o.tcp_output:	^.^.include.netinet.h.in_pcb
o.tcp_output:	^.^.include.netinet.h.in_systm
o.tcp_output:	^.^.include.netinet.h.ip
o.tcp_output:	^.^.include.netinet.h.in_systm
o.tcp_output:	^.^.include.netinet.h.ip_var
o.tcp_output:	^.^.include.netinet.h.tcp
o.tcp_output:	^.^.include.netinet.h.tcp_fsm
o.tcp_output:	^.^.include.netinet.h.tcp_seq
o.tcp_output:	^.^.include.netinet.h.tcp_timer
o.tcp_output:	^.^.include.netinet.h.tcp_var
o.tcp_output:	^.^.include.netinet.h.tcpip
o.tcp_output:	^.^.include.netinet.h.tcp_debug
o.tcp_output:	^.^.include.h.svcdebug
o.tcp_subr:	^.netinet.c.tcp_subr
o.tcp_subr:	^.^.include.sys.h.param
o.tcp_subr:	^.^.include.sys.h.sysconf
o.tcp_subr:	^.^.include.sys.^.machine.h.machparam
o.tcp_subr:	^.^.include.sys.h.signal
o.tcp_subr:	^.^.include.sys.h.types
o.tcp_subr:	^.^.include.sys.h.systm
o.tcp_subr:	^.^.include.sys.h.mbuf
o.tcp_subr:	^.^.include.sys.h.socket
o.tcp_subr:	^.^.include.sys.h.socketvar
o.tcp_subr:	^.^.include.sys.h.protosw
o.tcp_subr:	^.^.include.sys.h.errno
o.tcp_subr:	^.^.include.sys.^.h.errno
o.tcp_subr:	C:h.kernel
o.tcp_subr:	^.^.include.net.h.route
o.tcp_subr:	^.^.include.net.h.if
o.tcp_subr:	^.^.include.sys.h.mbuf
o.tcp_subr:	^.^.include.net.^.net.h.if_arp
o.tcp_subr:	^.^.include.sys.h.socket
o.tcp_subr:	^.^.include.netinet.h.in
o.tcp_subr:	^.^.include.netinet.h.in_pcb
o.tcp_subr:	^.^.include.netinet.h.in_systm
o.tcp_subr:	^.^.include.netinet.h.ip
o.tcp_subr:	^.^.include.netinet.h.in_systm
o.tcp_subr:	^.^.include.netinet.h.ip_var
o.tcp_subr:	^.^.include.netinet.h.ip_icmp
o.tcp_subr:	^.^.include.netinet.h.tcp
o.tcp_subr:	^.^.include.netinet.h.tcp_fsm
o.tcp_subr:	^.^.include.netinet.h.tcp_seq
o.tcp_subr:	^.^.include.netinet.h.tcp_timer
o.tcp_subr:	^.^.include.netinet.h.tcp_var
o.tcp_subr:	^.^.include.netinet.h.tcpip
o.tcp_timer:	^.netinet.c.tcp_timer
o.tcp_timer:	^.^.include.sys.h.param
o.tcp_timer:	^.^.include.sys.h.sysconf
o.tcp_timer:	^.^.include.sys.^.machine.h.machparam
o.tcp_timer:	^.^.include.sys.h.signal
o.tcp_timer:	^.^.include.sys.h.types
o.tcp_timer:	^.^.include.sys.h.systm
o.tcp_timer:	^.^.include.sys.h.mbuf
o.tcp_timer:	^.^.include.sys.h.socket
o.tcp_timer:	^.^.include.sys.h.socketvar
o.tcp_timer:	^.^.include.sys.h.protosw
o.tcp_timer:	^.^.include.sys.h.errno
o.tcp_timer:	^.^.include.sys.^.h.errno
o.tcp_timer:	C:h.kernel
o.tcp_timer:	^.^.include.net.h.if
o.tcp_timer:	^.^.include.sys.h.mbuf
o.tcp_timer:	^.^.include.net.^.net.h.if_arp
o.tcp_timer:	^.^.include.sys.h.socket
o.tcp_timer:	^.^.include.net.h.route
o.tcp_timer:	^.^.include.netinet.h.in
o.tcp_timer:	^.^.include.netinet.h.in_pcb
o.tcp_timer:	^.^.include.netinet.h.in_systm
o.tcp_timer:	^.^.include.netinet.h.ip
o.tcp_timer:	^.^.include.netinet.h.in_systm
o.tcp_timer:	^.^.include.netinet.h.ip_var
o.tcp_timer:	^.^.include.netinet.h.tcp
o.tcp_timer:	^.^.include.netinet.h.tcp_fsm
o.tcp_timer:	^.^.include.netinet.h.tcp_seq
o.tcp_timer:	^.^.include.netinet.h.tcp_timer
o.tcp_timer:	^.^.include.netinet.h.tcp_var
o.tcp_timer:	^.^.include.netinet.h.tcpip
o.tcp_usrreq:	^.netinet.c.tcp_usrreq
o.tcp_usrreq:	^.^.include.sys.h.param
o.tcp_usrreq:	^.^.include.sys.h.sysconf
o.tcp_usrreq:	^.^.include.sys.^.machine.h.machparam
o.tcp_usrreq:	^.^.include.sys.h.signal
o.tcp_usrreq:	^.^.include.sys.h.types
o.tcp_usrreq:	^.^.include.sys.h.systm
o.tcp_usrreq:	^.^.include.sys.h.stat
o.tcp_usrreq:	^.^.include.sys.h.mbuf
o.tcp_usrreq:	^.^.include.sys.h.socket
o.tcp_usrreq:	^.^.include.sys.h.socketvar
o.tcp_usrreq:	^.^.include.sys.h.protosw
o.tcp_usrreq:	^.^.include.sys.h.errno
o.tcp_usrreq:	^.^.include.sys.^.h.errno
o.tcp_usrreq:	C:h.kernel
o.tcp_usrreq:	^.^.include.net.h.if
o.tcp_usrreq:	^.^.include.sys.h.mbuf
o.tcp_usrreq:	^.^.include.net.^.net.h.if_arp
o.tcp_usrreq:	^.^.include.sys.h.socket
o.tcp_usrreq:	^.^.include.net.h.route
o.tcp_usrreq:	^.^.include.netinet.h.in
o.tcp_usrreq:	^.^.include.netinet.h.in_pcb
o.tcp_usrreq:	^.^.include.netinet.h.in_systm
o.tcp_usrreq:	^.^.include.netinet.h.ip
o.tcp_usrreq:	^.^.include.netinet.h.in_systm
o.tcp_usrreq:	^.^.include.netinet.h.ip_var
o.tcp_usrreq:	^.^.include.netinet.h.tcp
o.tcp_usrreq:	^.^.include.netinet.h.tcp_fsm
o.tcp_usrreq:	^.^.include.netinet.h.tcp_seq
o.tcp_usrreq:	^.^.include.netinet.h.tcp_timer
o.tcp_usrreq:	^.^.include.netinet.h.tcp_var
o.tcp_usrreq:	^.^.include.netinet.h.tcpip
o.tcp_usrreq:	^.^.include.netinet.h.tcp_debug
o.udp_usrreq:	^.netinet.c.udp_usrreq
o.udp_usrreq:	^.^.include.sys.h.param
o.udp_usrreq:	^.^.include.sys.h.sysconf
o.udp_usrreq:	^.^.include.sys.^.machine.h.machparam
o.udp_usrreq:	^.^.include.sys.h.signal
o.udp_usrreq:	^.^.include.sys.h.types
o.udp_usrreq:	^.^.include.sys.h.dir
o.udp_usrreq:	^.^.include.sys.h.user
o.udp_usrreq:	^.^.include.sys.h.errno
o.udp_usrreq:	^.^.include.sys.^.h.errno
o.udp_usrreq:	C:h.kernel
o.udp_usrreq:	^.^.include.sys.h.stat
o.udp_usrreq:	^.^.include.sys.h.mbuf
o.udp_usrreq:	^.^.include.sys.h.protosw
o.udp_usrreq:	^.^.include.sys.h.socket
o.udp_usrreq:	^.^.include.sys.h.socketvar
o.udp_usrreq:	^.^.include.sys.h.errno
o.udp_usrreq:	^.^.include.sys.h.dcistructs
o.udp_usrreq:	^.^.include.net.h.if
o.udp_usrreq:	^.^.include.sys.h.mbuf
o.udp_usrreq:	^.^.include.net.^.net.h.if_arp
o.udp_usrreq:	^.^.include.sys.h.socket
o.udp_usrreq:	^.^.include.net.h.route
o.udp_usrreq:	^.^.include.netinet.h.in
o.udp_usrreq:	^.^.include.netinet.h.in_pcb
o.udp_usrreq:	^.^.include.netinet.h.in_systm
o.udp_usrreq:	^.^.include.netinet.h.ip
o.udp_usrreq:	^.^.include.netinet.h.in_systm
o.udp_usrreq:	^.^.include.netinet.h.ip_var
o.udp_usrreq:	^.^.include.netinet.h.ip_icmp
o.udp_usrreq:	^.^.include.netinet.h.udp
o.udp_usrreq:	^.^.include.netinet.h.udp_var
o.udp_usrreq:	^.^.include.h.svcdebug
o.udp_usrreq:	h.debug
o.unixenv:	^.lib.c.unixenv
o.unixenv:	C:h.kernel
o.unixenv:	C:h.swis
o.unixenv:	^.^.include.sys.h.param
o.unixenv:	^.^.include.sys.h.sysconf
o.unixenv:	^.^.include.sys.^.machine.h.machparam
o.unixenv:	^.^.include.sys.h.signal
o.unixenv:	^.^.include.sys.h.types
o.unixenv:	^.^.include.sys.h.uio
o.unixenv:	^.^.include.sys.h.time
o.unixenv:	^.^.include.sys.h.mbuf
o.unixenv:	^.^.include.sys.h.user
o.unixenv:	^.^.include.sys.h.errno
o.unixenv:	^.^.include.sys.^.h.errno
o.unixenv:	C:h.kernel
o.unixenv:	^.^.include.sys.h.proc
o.unixenv:	^.^.include.net.h.netisr
o.unixenv:	h.module
o.whoami:	^.whoami.c.whoami
o.whoami:	C:h.kernel
o.whoami:	C:h.swis
o.whoami:	^.^.include.sys.h.param
o.whoami:	^.^.include.sys.h.sysconf
o.whoami:	^.^.include.sys.^.machine.h.machparam
o.whoami:	^.^.include.sys.h.signal
o.whoami:	^.^.include.sys.h.types
o.whoami:	^.^.include.sys.h.systm
o.whoami:	^.^.include.sys.h.syslog
o.whoami:	^.^.include.sys.h.time
o.whoami:	^.^.include.sys.h.mbuf
o.whoami:	^.^.include.sys.h.socket
o.whoami:	^.^.include.sys.h.errno
o.whoami:	^.^.include.sys.^.h.errno
o.whoami:	C:h.kernel
o.whoami:	^.^.include.sys.h.ioctl
o.whoami:	^.^.include.sys.h.ttychars
o.whoami:	^.^.include.sys.h.ttydev
o.whoami:	^.^.include.sys.h.bootp
o.whoami:	^.^.include.net.h.if
o.whoami:	^.^.include.sys.h.mbuf
o.whoami:	^.^.include.net.^.net.h.if_arp
o.whoami:	^.^.include.sys.h.socket
o.whoami:	^.^.include.net.h.route
o.whoami:	^.^.include.netinet.h.in
o.whoami:	^.^.include.netinet.h.in_var
o.whoami:	^.^.include.netinet.h.in_pcb
o.whoami:	^.^.include.netinet.h.in_systm
o.whoami:	^.^.include.netinet.h.ip
o.whoami:	^.^.include.netinet.h.in_systm
o.whoami:	^.^.include.netinet.h.if_ether
o.whoami:	^.^.include.sys.h.types
o.whoami:	^.^.include.sys.h.socket
o.whoami:	^.^.include.net.h.if
o.whoami:	^.^.include.net.h.if_arp
o.whoami:	^.^.include.netinet.h.in
o.whoami:	^.^.include.netinet.h.ip_icmp
o.whoami:	^.^.include.netinet.h.ip_var
o.whoami:	^.^.include.netinet.h.icmp_var
o.whoami:	^.^.include.netinet.h.tcp
o.whoami:	^.^.include.netinet.h.udp
o.whoami:	^.^.include.netinet.h.udp_var
o.whoami:	h.debug
