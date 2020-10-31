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
INCLUDES  = -IINetInc:
#DFLAGS    = -DDEBUG

OBJS   = o.mns o.mnscommon o.io o.swis o.configure o.netasm o.route o.showrt \
         o.text o.stubs o.inetfn o.debug

EOBJS  = o.mnsi o.mnscommon o.io_e o.swis_e o.configure o.netasm \
         o.text o.stubs o.inetfn o.debug

IOBJS  = o.mnsi o.mnscommon o.io o.swis o.configure o.netasm \
         o.text o.stubs o.inetfn o.debug

GOBJS  = o.mnsg o.io o.swis o.configure o.netasm o.showrt o.af o.if o.input\
         o.output o.startup o.tables o.timer o.trace o.inet o.data \
         o.text o.stubs o.inetfn

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
o.io_e:	c.io
o.io_e:	INetInc:sys.h.types
o.io_e:	INetInc:sys.h.socket
o.io_e:	INetInc:netinet.h.in
o.io_e:	INetInc:netinet.h.in_systm
o.io_e:	INetInc:netinet.h.ip
o.io_e:	INetInc:netinet.h.in_systm
o.io_e:	INetInc:netinet.h.ip_var
o.io_e:	INetInc:netinet.h.udp
o.io_e:	INetInc:netinet.h.udp_var
o.io_e:	INetInc:sys.h.errno
o.io_e:	INetInc:sys.^.h.errno
o.io_e:	C:h.kernel
o.io_e:	INetInc:sys.h.mbuf
o.io_e:	C:h.kernel
o.io_e:	C:h.swis
o.io_e:	h.module
o.io_e:	h.io
o.io_e:	h.mns
o.io_e:	h.netasm
o.io_e:	h.stubs
o.swis_e:	c.swis
o.swis_e:	C:h.kernel
o.swis_e:	C:h.swis
o.swis_e:	INetInc:sys.h.types
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
o.mnsi:	INetInc:sys.h.types
o.mnsi:	INetInc:sys.h.uio
o.mnsi:	INetInc:sys.h.socket
o.mnsi:	INetInc:sys.h.time
o.mnsi:	INetInc:sys.h.time
o.mnsi:	INetInc:sys.h.ioctl
o.mnsi:	INetInc:sys.h.ttychars
o.mnsi:	INetInc:sys.h.ttydev
o.mnsi:	INetInc:netinet.h.in
o.mnsi:	INetInc:net.h.if
o.mnsi:	INetInc:sys.h.mbuf
o.mnsi:	INetInc:net.h.if_arp
o.mnsi:	INetInc:sys.h.socket
o.mnsi:	INetInc:sys.h.dcistructs
o.mnsi:	h.netasm
o.mnsi:	h.module
o.mnsi:	h.mns
o.mnsi:	h.mnscommon
o.mnsi:	h.debug
o.mnsi:	h.text
o.mnsi:	h.swicode
o.mns:	c.mns
o.mns:	C:h.kernel
o.mns:	C:h.swis
o.mns:	INetInc:sys.h.types
o.mns:	INetInc:sys.h.uio
o.mns:	INetInc:sys.h.socket
o.mns:	INetInc:sys.h.time
o.mns:	INetInc:sys.h.time
o.mns:	INetInc:sys.h.ioctl
o.mns:	INetInc:sys.h.ttychars
o.mns:	INetInc:sys.h.ttydev
o.mns:	INetInc:sys.h.dcistructs
o.mns:	INetInc:netinet.h.in
o.mns:	INetInc:net.h.if
o.mns:	INetInc:sys.h.mbuf
o.mns:	INetInc:net.h.if_arp
o.mns:	INetInc:sys.h.socket
o.mns:	INetInc:protocols.h.routed
o.mns:	h.netasm
o.mns:	h.module
o.mns:	h.mnscommon
o.mns:	h.configure
o.mns:	h.debug
o.mns:	h.inetfn
o.mns:	h.io
o.mns:	h.showrt
o.mns:	h.stubs
o.mns:	h.swicode
o.mns:	h.text
o.mns:	h.routecode
o.mns:	h.mns
o.mnscommon:	c.mnscommon
o.mnscommon:	C:h.kernel
o.mnscommon:	C:h.swis
o.mnscommon:	INetInc:sys.h.types
o.mnscommon:	INetInc:sys.h.socket
o.mnscommon:	INetInc:sys.h.ioctl
o.mnscommon:	INetInc:sys.h.ttychars
o.mnscommon:	INetInc:sys.h.ttydev
o.mnscommon:	INetInc:netinet.h.in
o.mnscommon:	INetInc:sys.h.dcistructs
o.mnscommon:	h.netasm
o.mnscommon:	h.module
o.mnscommon:	h.debug
o.mnscommon:	h.mns
o.mnscommon:	h.mnscommon
o.mnscommon:	h.text
o.io:	c.io
o.io:	INetInc:sys.h.types
o.io:	INetInc:sys.h.socket
o.io:	INetInc:netinet.h.in
o.io:	INetInc:netinet.h.in_systm
o.io:	INetInc:netinet.h.ip
o.io:	INetInc:netinet.h.in_systm
o.io:	INetInc:netinet.h.ip_var
o.io:	INetInc:netinet.h.udp
o.io:	INetInc:netinet.h.udp_var
o.io:	INetInc:sys.h.errno
o.io:	INetInc:sys.^.h.errno
o.io:	C:h.kernel
o.io:	INetInc:sys.h.mbuf
o.io:	C:h.kernel
o.io:	C:h.swis
o.io:	h.module
o.io:	h.io
o.io:	h.mns
o.io:	h.netasm
o.io:	h.stubs
o.swis:	c.swis
o.swis:	C:h.kernel
o.swis:	C:h.swis
o.swis:	INetInc:sys.h.types
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
o.configure:	INetInc:sys.h.types
o.configure:	INetInc:sys.h.socket
o.configure:	INetInc:sys.h.ioctl
o.configure:	INetInc:sys.h.ttychars
o.configure:	INetInc:sys.h.ttydev
o.configure:	INetInc:sys.h.dcistructs
o.configure:	INetInc:net.h.if
o.configure:	INetInc:sys.h.mbuf
o.configure:	INetInc:net.h.if_arp
o.configure:	INetInc:sys.h.socket
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
o.route:	INetInc:sys.h.types
o.route:	INetInc:sys.h.socket
o.route:	INetInc:sys.h.ioctl
o.route:	INetInc:sys.h.ttychars
o.route:	INetInc:sys.h.ttydev
o.route:	INetInc:net.h.route
o.route:	INetInc:protocols.h.routed
o.route:	INetInc:netinet.h.in
o.route:	h.module
o.route:	h.routecode
o.route:	h.stubs
o.showrt:	c.showrt
o.showrt:	C:h.kernel
o.showrt:	INetInc:sys.h.types
o.showrt:	INetInc:sys.h.socket
o.showrt:	INetInc:sys.h.ioctl
o.showrt:	INetInc:sys.h.ttychars
o.showrt:	INetInc:sys.h.ttydev
o.showrt:	INetInc:sys.h.mbuf
o.showrt:	INetInc:net.h.route
o.showrt:	INetInc:netinet.h.in
o.showrt:	h.module
o.showrt:	h.mnscommon
o.showrt:	h.mns
o.showrt:	h.showrt
o.showrt:	h.stubs
o.text:	c.text
o.text:	INetInc:sys.h.types
o.text:	h.module
o.text:	h.text
o.stubs:	c.stubs
o.stubs:	C:h.kernel
o.stubs:	INetInc:sys.h.types
o.stubs:	INetInc:sys.h.errno
o.stubs:	INetInc:sys.^.h.errno
o.stubs:	C:h.kernel
o.stubs:	INetInc:sys.h.socket
o.stubs:	INetInc:sys.h.time
o.stubs:	INetInc:sys.h.time
o.stubs:	h.stubs
o.stubs:	h.debug
o.inetfn:	c.inetfn
o.inetfn:	INetInc:sys.h.types
o.inetfn:	INetInc:netinet.h.in
o.inetfn:	h.inetfn
o.debug:	c.debug
o.debug:	C:h.kernel
o.debug:	C:h.swis
o.debug:	h.debug
