# Makefile for Net
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name         Description
# ----       ----         -----------
# 25-May-94  AMcC         Created.
# 01-Dec-94  JDavies      Modified to allow build without Generic include files
#                         and to include disc-based, not built-in, swis.h
# 04-Jan-94  JDavies      Added build of NetMsgs module for use of Net module
#                         not with the RISC OS Black ROM. Start use of -fah
#                         option.
# 11-Jan-95  JDavies      Continue -fah use.
# 13-Jan-95  JDavies      Add -ff and -zps1 options
# 31-Jan-95  JDavies      Split c.debug off as a separate file
# 06-Feb-95  JDavies      Tidied
# 21-Feb-95  JDavies      Commented out NetMsgs stuff (rm.netMsgs is no longer
#                         needed or made.
# 22-Feb-95  JDavies      Removed need for CLibInc$Path to be set, uses
#                         C$Liboot instead.
# 14-Mar-95  JDavies      Added use of mnscommon.c. c.NetI now compilable -fahf
# 17-Mar-95  JDavies      Removed CNFLAGS definition, no longer needed
#

#
# Generic options:
#
MKDIR   = cdir
AS      = objasm
CC      = cc
CMHG    = cmhg
CP      = copy
LD      = link
RM      = remove
WIPE    = -wipe

AFLAGS  = -depend !Depend -Stamp -quit
CFLAGS  = -c -depend !Depend -fahf -zps1 -pcc -zM ${INCLUDES} ${DFLAGS}
CPFLAGS = ~cfr~v
WFLAGS  = ~c~v

#
# Libraries
#
CLIB      = CLIB:o.stubs
RLIB      = RISCOSLIB:o.risc_oslib
RSTUBS    = RISCOSLIB:o.rstubs
ROMSTUBS  = RISCOSLIB:o.romstubs
ROMCSTUBS = RISCOSLIB:o.romcstubs
ABSSYM    = RISC_OSLib:o.AbsSym

#
# Program specific options:
#
COMPONENT = Net
TARGET    = aof.Net

VPATH     = @ gwroute
INCLUDES  = -IInetInc4:,C:
#DFLAGS    = -DDEBUG

OBJS   = o.mns o.mnscommon o.io o.swis o.configure o.netasm o.route o.showrt \
         o.text o.inetfn o.debug ^.libs4.socklib.socklibzm

EOBJS  = o.mnsi o.mnscommon o.io_e o.swis_e o.configure o.netasm \
         o.text o.inetfn o.debug ^.libs4.socklib.socklibzm

IOBJS  = o.mnsi o.mnscommon o.io o.swis o.configure o.netasm \
         o.text o.inetfn o.debug ^.libs4.socklib.socklibzm

GOBJS  = o.mnsg o.mnscommon o.io o.swis o.configure o.netasm o.showrt \
	 o.text o.inetfn ^.^.libs4.socklib.socklibzm InetInc4:o.unixlibzm \
         o.af o.if o.input o.output o.startup o.tables \
         o.timer o.trace o.inet o.data
         

#
# Rule patterns
#
.c.o:;      ${CC} ${CFLAGS} -o $@ $<
.s.o:;      ${AS} ${AFLAGS} $< $@

#
# AUN build rules:
#
# all:    rm.Net rm.NetB rm.NetE rm.NetG rm.NetI
all:    rm.Net rm.NetB rm.NetE rm.NetI

install:    rm.NetI
        ${CP} rm.NetI ${INSTDIR}.NetI ${CPFLAGS}
        Access ${INSTDIR}.NetI WR/r
        @echo ${COMPONENT}: NetI installed
#
# RISC OS ROM build rules:
#
rom: ${TARGET}
        @echo ${COMPONENT}: rom module built

export: ${EXPORTS}
        @echo ${COMPONENT}: export complete

install_rom: ${TARGET}
        ${CP} ${TARGET} ${INSTDIR}.${COMPONENT} ${CPFLAGS}
        @echo ${COMPONENT}: rom module installed

clean:
        ${WIPE} o.* ${WFLAGS}
        ${WIPE} rm.* ${WFLAGS}
        ${WIPE} linked.* ${WFLAGS}
        ${WIPE} map.* ${WFLAGS}
        ${RM} ${TARGET}
        @echo ${COMPONENT}: cleaned

resources:
        @echo ${COMPONENT}: resource files are in AUNMsgs

${TARGET}: ${OBJS} cmhg.MNSHdr_b ${ROMSTUBS}
        ${CMHG} cmhg.mnsHdr_b o.mnshdr_b
        ${LD} -o $@ -aof o.mnshdr_b ${OBJS} ${ROMSTUBS}

rom_link:
        ${LD} -o linked.${COMPONENT} -map -bin -base ${ADDRESS} ${TARGET} ${ABSSYM} > map.${COMPONENT}
        truncate map.${COMPONENT} linked.${COMPONENT}
        ${CP} linked.${COMPONENT} ${LINKDIR}.${COMPONENT} ${CPFLAGS}
        @echo ${COMPONENT}: rom_link complete

#
# AUN:
#
#rm.NetMsgs: Resources.UK.Messages
#        modgen rm.~NetMsgs NetMsgs NetMsgs 0.03 Resources.UK.Messages Resources.Net.Messages
#        modsqz rm.~NetMsgs
#        remove rm.NetMsgs
#        rename rm.~NetMsgs rm.NetMsgs

rm.Net:  ${OBJS} cmhg.MNSHdr_c ${LCLIB}
         ${CMHG} cmhg.mnsHdr_c o.mnshdr_c
         ${LD} -o $@ -module -map o.mnshdr_c ${OBJS} ${CLIB} > map.linkmap_c

rm.NetB: ${OBJS} cmhg.MNSHdr_b ${LCLIB}
         ${CMHG} cmhg.mnsHdr_b o.mnshdr_b
         ${LD} -o $@ -module -map o.mnshdr_b ${OBJS} ${CLIB} > map.linkmap_b

rm.NetE: ${EOBJS} cmhg.MNSHdr_e ${LCLIB}
         ${CMHG} cmhg.mnshdr_e o.mnshdr_e
         ${LD} -o $@ -module -map o.mnshdr_e ${EOBJS} ${CLIB} > map.linkmap_e

rm.NetI: ${IOBJS} cmhg.MNSHdr_i ${LCLIB}
         ${CMHG} cmhg.mnshdr_i o.mnshdr_i
         ${LD} -o $@ -module -map o.mnshdr_i ${IOBJS} ${CLIB} > map.linkmap_i

rm.NetG: ${GOBJS} cmhg.Mnshdr_g ${LCLIB}
         ${CMHG} cmhg.mnshdr_g o.mnshdr_g
         ${LD} -o $@ -module -map o.mnshdr_g ${GOBJS} ${CLIB} > map.linkmap_g

#
# Special rules:
#

io_e.o: c.io
        ${CC} ${CFLAGS} -DEDDS c.io -o o.io_e

swis_e.o: c.swis
        ${CC} ${CFLAGS} -DEDDS c.swis -o o.swis_e

# Dynamic dependencies:
o.timer:	gwroute.c.timer
o.timer:	h.mnsg
o.timer:	gwroute.h.output
o.timer:	gwroute.h.timer
o.inet:	gwroute.c.inet
o.inet:	InetInc4:sys.h.types
o.inet:	InetInc4:sys.h.cdefs
o.inet:	InetInc4:machine.h.endian
o.inet:	InetInc4:machine.h.ansi
o.inet:	InetInc4:machine.h.types
o.inet:	InetInc4:sys.h.socket
o.inet:	InetInc4:sys.h.cdefs
o.inet:	InetInc4:netinet.h.in
o.inet:	InetInc4:net.h.route
o.inet:	InetInc4:net.h.radix
o.inet:	InetInc4:protocols.h.routed
o.inet:	gwroute.h.table
o.inet:	gwroute.h.data
o.inet:	gwroute.h.interface
o.inet:	gwroute.h.inetcode
o.data:	gwroute.c.data
o.data:	InetInc4:sys.h.types
o.data:	InetInc4:sys.h.cdefs
o.data:	InetInc4:machine.h.endian
o.data:	InetInc4:machine.h.ansi
o.data:	InetInc4:machine.h.types
o.data:	InetInc4:sys.h.socket
o.data:	InetInc4:sys.h.cdefs
o.data:	InetInc4:sys.h.time
o.data:	InetInc4:sys.h.cdefs
o.data:	InetInc4:net.h.route
o.data:	InetInc4:net.h.radix
o.data:	InetInc4:protocols.h.routed
o.data:	gwroute.h.interface
o.data:	gwroute.h.table
o.data:	gwroute.h.data
o.mnsg:	c.mnsg
o.mnsg:	C:h.kernel
o.mnsg:	C:h.swis
o.mnsg:	InetInc4:sys.h.types
o.mnsg:	InetInc4:sys.h.cdefs
o.mnsg:	InetInc4:machine.h.endian
o.mnsg:	InetInc4:machine.h.ansi
o.mnsg:	InetInc4:machine.h.types
o.mnsg:	InetInc4:sys.h.uio
o.mnsg:	InetInc4:sys.h.cdefs
o.mnsg:	InetInc4:sys.h.socket
o.mnsg:	InetInc4:sys.h.cdefs
o.mnsg:	InetInc4:sys.h.time
o.mnsg:	InetInc4:sys.h.cdefs
o.mnsg:	InetInc4:sys.h.ioctl
o.mnsg:	InetInc4:sys.h.ttycom
o.mnsg:	InetInc4:sys.h.ioccom
o.mnsg:	InetInc4:sys.h.ioccom
o.mnsg:	InetInc4:sys.h.filio
o.mnsg:	InetInc4:sys.h.ioccom
o.mnsg:	InetInc4:sys.h.sockio
o.mnsg:	InetInc4:sys.h.ioccom
o.mnsg:	InetInc4:sys.h.cdefs
o.mnsg:	InetInc4:netinet.h.in
o.mnsg:	InetInc4:net.h.if
o.mnsg:	InetInc4:sys.h.socket
o.mnsg:	InetInc4:sys.h.time
o.mnsg:	InetInc4:net.h.if_arp
o.mnsg:	InetInc4:sys.h.socket
o.mnsg:	InetInc4:sys.h.dcistructs
o.mnsg:	InetInc4:protocols.h.routed
o.mnsg:	h.netasm
o.mnsg:	h.module
o.mnsg:	h.mnscommon
o.mnsg:	h.configure
o.mnsg:	h.debug
o.mnsg:	h.inetfn
o.mnsg:	h.io
o.mnsg:	h.showrt
o.mnsg:	InetInc4:h.socklib
o.mnsg:	InetInc4:sys.h.types
o.mnsg:	InetInc4:sys.h.socket
o.mnsg:	InetInc4:sys.h.stat
o.mnsg:	InetInc4:sys.h.time
o.mnsg:	InetInc4:sys.h.cdefs
o.mnsg:	InetInc4:sys.h.time
o.mnsg:	InetInc4:sys.h.uio
o.mnsg:	C:h.kernel
o.mnsg:	h.swicode
o.mnsg:	h.text
o.mnsg:	h.mns
o.mnsg:	h.mnsg
o.mnsg:	gwroute.h.startup
o.mnsg:	gwroute.h.input
o.mnsg:	gwroute.h.trace
o.af:	gwroute.c.af
o.af:	InetInc4:sys.h.types
o.af:	InetInc4:sys.h.cdefs
o.af:	InetInc4:machine.h.endian
o.af:	InetInc4:machine.h.ansi
o.af:	InetInc4:machine.h.types
o.af:	InetInc4:sys.h.socket
o.af:	InetInc4:sys.h.cdefs
o.af:	InetInc4:netinet.h.in
o.af:	InetInc4:net.h.route
o.af:	InetInc4:net.h.radix
o.af:	InetInc4:protocols.h.routed
o.af:	h.module
o.af:	InetInc4:h.socklib
o.af:	InetInc4:sys.h.types
o.af:	InetInc4:sys.h.socket
o.af:	InetInc4:sys.h.stat
o.af:	InetInc4:sys.h.time
o.af:	InetInc4:sys.h.cdefs
o.af:	InetInc4:sys.h.cdefs
o.af:	InetInc4:sys.h.time
o.af:	InetInc4:sys.h.uio
o.af:	InetInc4:sys.h.cdefs
o.af:	C:h.kernel
o.af:	gwroute.h.inetcode
o.af:	gwroute.h.table
o.af:	gwroute.h.data
o.af:	gwroute.h.af
o.if:	gwroute.c.if
o.if:	InetInc4:sys.h.types
o.if:	InetInc4:sys.h.cdefs
o.if:	InetInc4:machine.h.endian
o.if:	InetInc4:machine.h.ansi
o.if:	InetInc4:machine.h.types
o.if:	InetInc4:sys.h.socket
o.if:	InetInc4:sys.h.cdefs
o.if:	InetInc4:net.h.route
o.if:	InetInc4:net.h.radix
o.if:	InetInc4:netinet.h.in
o.if:	InetInc4:protocols.h.routed
o.if:	InetInc4:net.h.if
o.if:	InetInc4:sys.h.socket
o.if:	InetInc4:sys.h.time
o.if:	InetInc4:sys.h.cdefs
o.if:	InetInc4:net.h.if_arp
o.if:	InetInc4:sys.h.socket
o.if:	gwroute.h.interface
o.if:	gwroute.h.table
o.if:	gwroute.h.data
o.input:	gwroute.c.input
o.input:	InetInc4:sys.h.types
o.input:	InetInc4:sys.h.cdefs
o.input:	InetInc4:machine.h.endian
o.input:	InetInc4:machine.h.ansi
o.input:	InetInc4:machine.h.types
o.input:	InetInc4:sys.h.socket
o.input:	InetInc4:sys.h.cdefs
o.input:	InetInc4:net.h.if
o.input:	InetInc4:sys.h.socket
o.input:	InetInc4:sys.h.time
o.input:	InetInc4:sys.h.cdefs
o.input:	InetInc4:net.h.if_arp
o.input:	InetInc4:sys.h.socket
o.input:	InetInc4:netinet.h.in
o.input:	InetInc4:net.h.route
o.input:	InetInc4:net.h.radix
o.input:	InetInc4:protocols.h.routed
o.input:	h.mnsg
o.input:	h.debug
o.input:	gwroute.h.interface
o.input:	gwroute.h.table
o.input:	gwroute.h.data
o.input:	gwroute.h.startup
o.input:	gwroute.h.trace
o.input:	gwroute.h.defs
o.input:	gwroute.h.input
o.output:	gwroute.c.output
o.output:	InetInc4:sys.h.types
o.output:	InetInc4:sys.h.cdefs
o.output:	InetInc4:machine.h.endian
o.output:	InetInc4:machine.h.ansi
o.output:	InetInc4:machine.h.types
o.output:	InetInc4:sys.h.socket
o.output:	InetInc4:sys.h.cdefs
o.output:	InetInc4:net.h.if
o.output:	InetInc4:sys.h.socket
o.output:	InetInc4:sys.h.time
o.output:	InetInc4:sys.h.cdefs
o.output:	InetInc4:net.h.if_arp
o.output:	InetInc4:sys.h.socket
o.output:	InetInc4:netinet.h.in
o.output:	InetInc4:net.h.route
o.output:	InetInc4:net.h.radix
o.output:	InetInc4:protocols.h.routed
o.output:	h.module
o.output:	h.mnsg
o.output:	gwroute.h.interface
o.output:	gwroute.h.table
o.output:	gwroute.h.data
o.output:	gwroute.h.trace
o.output:	gwroute.h.output
o.startup:	gwroute.c.startup
o.startup:	InetInc4:sys.h.types
o.startup:	InetInc4:sys.h.cdefs
o.startup:	InetInc4:machine.h.endian
o.startup:	InetInc4:machine.h.ansi
o.startup:	InetInc4:machine.h.types
o.startup:	InetInc4:sys.h.time
o.startup:	InetInc4:sys.h.cdefs
o.startup:	InetInc4:sys.h.ioctl
o.startup:	InetInc4:sys.h.ttycom
o.startup:	InetInc4:sys.h.ioccom
o.startup:	InetInc4:sys.h.ioccom
o.startup:	InetInc4:sys.h.filio
o.startup:	InetInc4:sys.h.ioccom
o.startup:	InetInc4:sys.h.sockio
o.startup:	InetInc4:sys.h.ioccom
o.startup:	InetInc4:sys.h.cdefs
o.startup:	InetInc4:sys.h.socket
o.startup:	InetInc4:sys.h.cdefs
o.startup:	InetInc4:netinet.h.in
o.startup:	InetInc4:net.h.if
o.startup:	InetInc4:sys.h.socket
o.startup:	InetInc4:sys.h.time
o.startup:	InetInc4:net.h.if_arp
o.startup:	InetInc4:sys.h.socket
o.startup:	InetInc4:net.h.route
o.startup:	InetInc4:net.h.radix
o.startup:	InetInc4:protocols.h.routed
o.startup:	h.mnsg
o.startup:	h.module
o.startup:	h.debug
o.startup:	gwroute.h.table
o.startup:	gwroute.h.data
o.startup:	gwroute.h.inetcode
o.startup:	gwroute.h.output
o.startup:	gwroute.h.interface
o.startup:	gwroute.h.startup
o.tables:	gwroute.c.tables
o.tables:	InetInc4:sys.h.types
o.tables:	InetInc4:sys.h.cdefs
o.tables:	InetInc4:machine.h.endian
o.tables:	InetInc4:machine.h.ansi
o.tables:	InetInc4:machine.h.types
o.tables:	InetInc4:sys.h.socket
o.tables:	InetInc4:sys.h.cdefs
o.tables:	InetInc4:net.h.route
o.tables:	InetInc4:net.h.radix
o.tables:	InetInc4:netinet.h.in
o.tables:	InetInc4:sys.h.ioctl
o.tables:	InetInc4:sys.h.ttycom
o.tables:	InetInc4:sys.h.ioccom
o.tables:	InetInc4:sys.h.ioccom
o.tables:	InetInc4:sys.h.filio
o.tables:	InetInc4:sys.h.ioccom
o.tables:	InetInc4:sys.h.sockio
o.tables:	InetInc4:sys.h.ioccom
o.tables:	InetInc4:sys.h.cdefs
o.tables:	InetInc4:protocols.h.routed
o.tables:	h.mnsg
o.tables:	h.debug
o.tables:	gwroute.h.af
o.tables:	gwroute.h.trace
o.tables:	gwroute.h.table
o.tables:	gwroute.h.data
o.tables:	gwroute.h.startup
o.tables:	gwroute.h.defs
o.tables:	gwroute.h.interface
o.mns:	c.mns
o.mns:	C:h.kernel
o.mns:	C:h.swis
o.mns:	InetInc4:sys.h.types
o.mns:	InetInc4:sys.h.cdefs
o.mns:	InetInc4:machine.h.endian
o.mns:	InetInc4:machine.h.ansi
o.mns:	InetInc4:machine.h.types
o.mns:	InetInc4:sys.h.uio
o.mns:	InetInc4:sys.h.cdefs
o.mns:	InetInc4:sys.h.socket
o.mns:	InetInc4:sys.h.cdefs
o.mns:	InetInc4:sys.h.time
o.mns:	InetInc4:sys.h.cdefs
o.mns:	InetInc4:sys.h.ioctl
o.mns:	InetInc4:sys.h.ttycom
o.mns:	InetInc4:sys.h.ioccom
o.mns:	InetInc4:sys.h.ioccom
o.mns:	InetInc4:sys.h.filio
o.mns:	InetInc4:sys.h.ioccom
o.mns:	InetInc4:sys.h.sockio
o.mns:	InetInc4:sys.h.ioccom
o.mns:	InetInc4:sys.h.cdefs
o.mns:	InetInc4:sys.h.dcistructs
o.mns:	InetInc4:netinet.h.in
o.mns:	InetInc4:net.h.if
o.mns:	InetInc4:sys.h.socket
o.mns:	InetInc4:sys.h.time
o.mns:	InetInc4:net.h.if_arp
o.mns:	InetInc4:sys.h.socket
o.mns:	InetInc4:protocols.h.routed
o.mns:	h.netasm
o.mns:	h.module
o.mns:	h.mnscommon
o.mns:	h.configure
o.mns:	h.debug
o.mns:	h.inetfn
o.mns:	h.io
o.mns:	h.showrt
o.mns:	InetInc4:h.socklib
o.mns:	InetInc4:sys.h.types
o.mns:	InetInc4:sys.h.socket
o.mns:	InetInc4:sys.h.stat
o.mns:	InetInc4:sys.h.time
o.mns:	InetInc4:sys.h.cdefs
o.mns:	InetInc4:sys.h.time
o.mns:	InetInc4:sys.h.uio
o.mns:	C:h.kernel
o.mns:	h.swicode
o.mns:	h.text
o.mns:	h.routecode
o.mns:	h.mns
o.mnscommon:	c.mnscommon
o.mnscommon:	C:h.kernel
o.mnscommon:	C:h.swis
o.mnscommon:	InetInc4:sys.h.types
o.mnscommon:	InetInc4:sys.h.cdefs
o.mnscommon:	InetInc4:machine.h.endian
o.mnscommon:	InetInc4:machine.h.ansi
o.mnscommon:	InetInc4:machine.h.types
o.mnscommon:	InetInc4:sys.h.socket
o.mnscommon:	InetInc4:sys.h.cdefs
o.mnscommon:	InetInc4:sys.h.ioctl
o.mnscommon:	InetInc4:sys.h.ttycom
o.mnscommon:	InetInc4:sys.h.ioccom
o.mnscommon:	InetInc4:sys.h.ioccom
o.mnscommon:	InetInc4:sys.h.filio
o.mnscommon:	InetInc4:sys.h.ioccom
o.mnscommon:	InetInc4:sys.h.sockio
o.mnscommon:	InetInc4:sys.h.ioccom
o.mnscommon:	InetInc4:sys.h.cdefs
o.mnscommon:	InetInc4:netinet.h.in
o.mnscommon:	InetInc4:sys.h.dcistructs
o.mnscommon:	h.netasm
o.mnscommon:	h.module
o.mnscommon:	h.debug
o.mnscommon:	h.mns
o.mnscommon:	h.mnscommon
o.mnscommon:	h.text
o.io:	c.io
o.io:	InetInc4:sys.h.types
o.io:	InetInc4:sys.h.cdefs
o.io:	InetInc4:machine.h.endian
o.io:	InetInc4:machine.h.ansi
o.io:	InetInc4:machine.h.types
o.io:	InetInc4:sys.h.socket
o.io:	InetInc4:sys.h.cdefs
o.io:	InetInc4:netinet.h.in
o.io:	InetInc4:netinet.h.in_systm
o.io:	InetInc4:netinet.h.ip
o.io:	InetInc4:netinet.h.ip_var
o.io:	InetInc4:netinet.h.udp
o.io:	InetInc4:netinet.h.udp_var
o.io:	InetInc4:sys.h.errno
o.io:	C:h.kernel
o.io:	InetInc4:sys.h.mbuf
o.io:	C:h.kernel
o.io:	C:h.swis
o.io:	h.module
o.io:	h.io
o.io:	h.mns
o.io:	h.netasm
o.io:	InetInc4:h.socklib
o.io:	InetInc4:sys.h.types
o.io:	InetInc4:sys.h.socket
o.io:	InetInc4:sys.h.stat
o.io:	InetInc4:sys.h.time
o.io:	InetInc4:sys.h.cdefs
o.io:	InetInc4:sys.h.cdefs
o.io:	InetInc4:sys.h.time
o.io:	InetInc4:sys.h.uio
o.io:	InetInc4:sys.h.cdefs
o.io:	C:h.kernel
o.swis:	c.swis
o.swis:	C:h.kernel
o.swis:	C:h.swis
o.swis:	InetInc4:sys.h.types
o.swis:	InetInc4:sys.h.cdefs
o.swis:	InetInc4:machine.h.endian
o.swis:	InetInc4:machine.h.ansi
o.swis:	InetInc4:machine.h.types
o.swis:	h.module
o.swis:	h.debug
o.swis:	h.inetfn
o.swis:	h.mns
o.swis:	h.mnscommon
o.swis:	h.netasm
o.swis:	h.io
o.swis:	h.swicode
o.configure:	c.configure
o.configure:	C:h.kernel
o.configure:	C:h.swis
o.configure:	InetInc4:sys.h.types
o.configure:	InetInc4:sys.h.cdefs
o.configure:	InetInc4:machine.h.endian
o.configure:	InetInc4:machine.h.ansi
o.configure:	InetInc4:machine.h.types
o.configure:	InetInc4:sys.h.socket
o.configure:	InetInc4:sys.h.cdefs
o.configure:	InetInc4:sys.h.ioctl
o.configure:	InetInc4:sys.h.ttycom
o.configure:	InetInc4:sys.h.ioccom
o.configure:	InetInc4:sys.h.ioccom
o.configure:	InetInc4:sys.h.filio
o.configure:	InetInc4:sys.h.ioccom
o.configure:	InetInc4:sys.h.sockio
o.configure:	InetInc4:sys.h.ioccom
o.configure:	InetInc4:sys.h.cdefs
o.configure:	InetInc4:sys.h.dcistructs
o.configure:	InetInc4:net.h.if
o.configure:	InetInc4:sys.h.socket
o.configure:	InetInc4:sys.h.time
o.configure:	InetInc4:sys.h.cdefs
o.configure:	InetInc4:net.h.if_arp
o.configure:	InetInc4:sys.h.socket
o.configure:	h.configure
o.configure:	h.swicode
o.configure:	h.module
o.configure:	h.debug
o.netasm: s.netasm
o.netasm: Hdr:ListOpts
o.netasm: Hdr:Macros
o.netasm: Hdr:System
o.netasm: Hdr:SWIs
o.netasm: Hdr:CPU.Generic26
o.netasm: Hdr:IO.GenericIO
o.netasm: Hdr:RISCOS
o.netasm: Hdr:EnvNumbers
o.netasm: Hdr:FSNumbers
o.netasm: Hdr:NewErrors
o.netasm: Hdr:ModHand
o.netasm: Hdr:Econet
o.netasm: Hdr:MsgTrans
o.netasm: Hdr:Symbols
o.netasm: Hdr:CMOS
o.route:	c.route
o.route:	InetInc4:sys.h.types
o.route:	InetInc4:sys.h.cdefs
o.route:	InetInc4:machine.h.endian
o.route:	InetInc4:machine.h.ansi
o.route:	InetInc4:machine.h.types
o.route:	InetInc4:sys.h.socket
o.route:	InetInc4:sys.h.cdefs
o.route:	InetInc4:sys.h.ioctl
o.route:	InetInc4:sys.h.ttycom
o.route:	InetInc4:sys.h.ioccom
o.route:	InetInc4:sys.h.ioccom
o.route:	InetInc4:sys.h.filio
o.route:	InetInc4:sys.h.ioccom
o.route:	InetInc4:sys.h.sockio
o.route:	InetInc4:sys.h.ioccom
o.route:	InetInc4:sys.h.cdefs
o.route:	InetInc4:net.h.route
o.route:	InetInc4:net.h.radix
o.route:	InetInc4:protocols.h.routed
o.route:	InetInc4:netinet.h.in
o.route:	h.module
o.route:	h.routecode
o.route:	InetInc4:h.socklib
o.route:	InetInc4:sys.h.types
o.route:	InetInc4:sys.h.socket
o.route:	InetInc4:sys.h.stat
o.route:	InetInc4:sys.h.time
o.route:	InetInc4:sys.h.cdefs
o.route:	InetInc4:sys.h.cdefs
o.route:	InetInc4:sys.h.time
o.route:	InetInc4:sys.h.uio
o.route:	InetInc4:sys.h.cdefs
o.route:	C:h.kernel
o.showrt:	c.showrt
o.showrt:	C:h.kernel
o.showrt:	InetInc4:sys.h.types
o.showrt:	InetInc4:sys.h.cdefs
o.showrt:	InetInc4:machine.h.endian
o.showrt:	InetInc4:machine.h.ansi
o.showrt:	InetInc4:machine.h.types
o.showrt:	InetInc4:sys.h.socket
o.showrt:	InetInc4:sys.h.cdefs
o.showrt:	InetInc4:sys.h.ioctl
o.showrt:	InetInc4:sys.h.ttycom
o.showrt:	InetInc4:sys.h.ioccom
o.showrt:	InetInc4:sys.h.ioccom
o.showrt:	InetInc4:sys.h.filio
o.showrt:	InetInc4:sys.h.ioccom
o.showrt:	InetInc4:sys.h.sockio
o.showrt:	InetInc4:sys.h.ioccom
o.showrt:	InetInc4:sys.h.cdefs
o.showrt:	InetInc4:sys.h.mbuf
o.showrt:	InetInc4:net.h.route
o.showrt:	InetInc4:net.h.radix
o.showrt:	InetInc4:netinet.h.in
o.showrt:	InetInc4:h.nlist
o.showrt:	InetInc4:sys.h.cdefs
o.showrt:	h.module
o.showrt:	h.mnscommon
o.showrt:	h.mns
o.showrt:	h.showrt
o.showrt:	InetInc4:h.socklib
o.showrt:	InetInc4:sys.h.types
o.showrt:	InetInc4:sys.h.socket
o.showrt:	InetInc4:sys.h.stat
o.showrt:	InetInc4:sys.h.time
o.showrt:	InetInc4:sys.h.cdefs
o.showrt:	InetInc4:sys.h.cdefs
o.showrt:	InetInc4:sys.h.time
o.showrt:	InetInc4:sys.h.uio
o.showrt:	InetInc4:sys.h.cdefs
o.showrt:	C:h.kernel
o.text:	c.text
o.text:	InetInc4:sys.h.types
o.text:	InetInc4:sys.h.cdefs
o.text:	InetInc4:machine.h.endian
o.text:	InetInc4:machine.h.ansi
o.text:	InetInc4:machine.h.types
o.text:	h.module
o.text:	h.text
o.inetfn:	c.inetfn
o.inetfn:	InetInc4:sys.h.types
o.inetfn:	InetInc4:sys.h.cdefs
o.inetfn:	InetInc4:machine.h.endian
o.inetfn:	InetInc4:machine.h.ansi
o.inetfn:	InetInc4:machine.h.types
o.inetfn:	InetInc4:netinet.h.in
o.inetfn:	h.inetfn
o.debug:	c.debug
o.debug:	C:h.kernel
o.debug:	C:h.swis
o.debug:	h.debug
o.io_e:	c.io
o.io_e:	InetInc4:sys.h.types
o.io_e:	InetInc4:sys.h.cdefs
o.io_e:	InetInc4:machine.h.endian
o.io_e:	InetInc4:machine.h.ansi
o.io_e:	InetInc4:machine.h.types
o.io_e:	InetInc4:sys.h.socket
o.io_e:	InetInc4:sys.h.cdefs
o.io_e:	InetInc4:netinet.h.in
o.io_e:	InetInc4:netinet.h.in_systm
o.io_e:	InetInc4:netinet.h.ip
o.io_e:	InetInc4:netinet.h.ip_var
o.io_e:	InetInc4:netinet.h.udp
o.io_e:	InetInc4:netinet.h.udp_var
o.io_e:	InetInc4:sys.h.errno
o.io_e:	C:h.kernel
o.io_e:	InetInc4:sys.h.mbuf
o.io_e:	C:h.kernel
o.io_e:	C:h.swis
o.io_e:	h.module
o.io_e:	h.io
o.io_e:	h.mns
o.io_e:	h.netasm
o.io_e:	InetInc4:h.socklib
o.io_e:	InetInc4:sys.h.types
o.io_e:	InetInc4:sys.h.socket
o.io_e:	InetInc4:sys.h.stat
o.io_e:	InetInc4:sys.h.time
o.io_e:	InetInc4:sys.h.cdefs
o.io_e:	InetInc4:sys.h.cdefs
o.io_e:	InetInc4:sys.h.time
o.io_e:	InetInc4:sys.h.uio
o.io_e:	InetInc4:sys.h.cdefs
o.io_e:	C:h.kernel
o.swis_e:	c.swis
o.swis_e:	C:h.kernel
o.swis_e:	C:h.swis
o.swis_e:	InetInc4:sys.h.types
o.swis_e:	InetInc4:sys.h.cdefs
o.swis_e:	InetInc4:machine.h.endian
o.swis_e:	InetInc4:machine.h.ansi
o.swis_e:	InetInc4:machine.h.types
o.swis_e:	h.module
o.swis_e:	h.debug
o.swis_e:	h.inetfn
o.swis_e:	h.mns
o.swis_e:	h.mnscommon
o.swis_e:	h.netasm
o.swis_e:	h.io
o.swis_e:	h.swicode
o.mnsi:	c.mnsi
o.mnsi:	C:h.kernel
o.mnsi:	C:h.swis
o.mnsi:	InetInc4:sys.h.types
o.mnsi:	InetInc4:sys.h.cdefs
o.mnsi:	InetInc4:machine.h.endian
o.mnsi:	InetInc4:machine.h.ansi
o.mnsi:	InetInc4:machine.h.types
o.mnsi:	InetInc4:sys.h.uio
o.mnsi:	InetInc4:sys.h.cdefs
o.mnsi:	InetInc4:sys.h.socket
o.mnsi:	InetInc4:sys.h.cdefs
o.mnsi:	InetInc4:sys.h.time
o.mnsi:	InetInc4:sys.h.cdefs
o.mnsi:	InetInc4:sys.h.ioctl
o.mnsi:	InetInc4:sys.h.ttycom
o.mnsi:	InetInc4:sys.h.ioccom
o.mnsi:	InetInc4:sys.h.ioccom
o.mnsi:	InetInc4:sys.h.filio
o.mnsi:	InetInc4:sys.h.ioccom
o.mnsi:	InetInc4:sys.h.sockio
o.mnsi:	InetInc4:sys.h.ioccom
o.mnsi:	InetInc4:sys.h.cdefs
o.mnsi:	InetInc4:netinet.h.in
o.mnsi:	InetInc4:net.h.if
o.mnsi:	InetInc4:sys.h.socket
o.mnsi:	InetInc4:sys.h.time
o.mnsi:	InetInc4:net.h.if_arp
o.mnsi:	InetInc4:sys.h.socket
o.mnsi:	InetInc4:sys.h.dcistructs
o.mnsi:	h.netasm
o.mnsi:	h.module
o.mnsi:	h.mns
o.mnsi:	h.mnscommon
o.mnsi:	h.debug
o.mnsi:	h.text
o.mnsi:	h.swicode
