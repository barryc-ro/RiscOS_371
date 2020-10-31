# Makefile for ShareFS
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name   Description
# ----       ----   -----------
# 21-Nov-94  AMcC   Created
# 05-Jan-95  AMcC   Added resources: rule and paths
# 21-Feb-95  AMcC    Resources now copied to AUNMsgs 
#

#
# Paths
#
EXP_HDR = <export$dir>

#
# Component specific options:
#
COMPONENT  = ShareFS
EXPORTS    = ${EXP_HDR}.ShareD
RAM_MODULE = rm.ShareFS
RAM_MODULE_PLUS = rm.Share+
ROM_MODULE = aof.ShareFS
RDIR       = Resources
LDIR       = ${RDIR}.${LOCALE}
RESDIR     = ^.^.^.AUNMsgs.Resources.${Locale}.Resources.${COMPONENT}

#
# Generic options:
#
AS      = objasm
CC      = cc
CMHG    = cmhg -b
CP      = copy
LD      = link
MKDIR   = cdir
RM      = remove
WIPE    = -wipe
CPFLAGS = ~cfr~v
WFLAGS  = ~c~v

LEVEL    = ^.^.^
INCLUDES = ^.rmalib,^.fslib,InetInc:,RISC_OSLib:,C:
DFLAGS   = -DDCI4 -DLOOKUPERR "-DFSNAME=\"Remote\"" #-DDEBUG -DPROFILING
CFLAGS   = -I${INCLUDES} -zM -zps1 -ffah ${DFLAGS} ${PLUSFLAGS} -wd
AFLAGS   = -I<Hdr$Dir>.Global.,<Hdr$Dir>.Interface. -Stamp -quit

# Always build Access+
PLUSFLAGS=-DACCESSPLUS

#
# Libraries
#
ANSILIB   = C:o.ansilib
CLIB      = C:o.stubs
RLIB      = RISCOSLIB:o.risc_oslib
ROMCSTUBS = RISCOSLIB:o.romcstubs
ABSSYM    = RISC_OSLib:o.abssym
C_ABSSYM  = RISCOSLIB:o.c_abssym

FSLIB     = ^.fslib.o.fslib
RMALIB    = ^.rmalib.o.rmalib
TCPLIB	  = ^.^.^.libs.socklib.socklibzm

# sharefsBITS
OBJS =\
 irqs.o\
 resourcefs.o\
 sharep.o\
 shared.o\
 sharefiler.o\
 sharefs.o\
 sharehow.o\
 shareinet.o\
 window.o

NORMOBJS =mshare.o

PLUSOBJS =msharep.o

#
# Rule patterns
#
.c.o:;      ${CC} -depend !Depend -c ${CFLAGS} -o $@ $<
.s.o:;      ${AS} -depend !Depend ${AFLAGS} $< $@
.cmhg.o:;   ${CMHG} -o $@ $<

#
# Main rules:
#
rom: ${ROM_MODULE}
        @echo ${COMPONENT}: Module built (ROM)

ram: ${RAM_MODULE}
        @echo ${COMPONENT}: Module built (RAM)

ramplus: ${RAM_MODULE_PLUS}
        @echo ${COMPONENT}: Module built (RAM)

#install_rom: ${ROM_MODULE}
#        ${CP} ${ROM_MODULE} ${INSTDIR}.${COMPONENT} ${CPFLAGS}
#        @echo ${COMPONENT}: Module installed (ROM)

resources:
        @echo ${COMPONENT}: Resources in AUNMsgs

export: ${EXPORTS}
        @echo ${COMPONENT}: export complete

${EXP_HDR}.ShareD: hdr.ShareD
        ${CP} hdr.ShareD $@ ${CPFLAGS}

clean:
        ${WIPE} o.* ${WFLAGS}
        ${RM} ${ROM_MODULE}
        ${WIPE} linked.* ${WFLAGS}
        ${WIPE} map.* ${WFLAGS}
        @echo ${COMPONENT}: cleaned

${ROM_MODULE}: ${OBJS} ${PLUSOBJS} ${RMALIB} ${FSLIB} ${ROMCSTUBS}
        ${LD} -o $@ -aof ${OBJS} ${PLUSOBJS} ${RMALIB} ${FSLIB} ${TCPLIB} ${ROMCSTUBS}

${RAM_MODULE}: ${OBJS} ${NORMOBJS} ${RMALIB} ${FSLIB} ${CLIB}
        ${LD} -o $@ -rmf ${OBJS} ${NORMOBJS} ${RMALIB} ${FSLIB} ${TCPLIB} ${CLIB}

${RAM_MODULE_PLUS}: ${OBJS} ${PLUSOBJS} ${RMALIB} ${FSLIB} ${CLIB}
        ${LD} -o $@ -rmf ${OBJS} ${PLUSOBJS} ${RMALIB} ${FSLIB} ${TCPLIB} ${CLIB}

${FSLIB}:
        dir ^.fslib; amu fslib.o; back

${RMALIB}:
        dir ^.rmalib; amu rmalib.o; back

# final link for ROM Image (using given base address)
rom_link:
        ${MKDIR} map
        ${MKDIR} linked
        ${LD} -o linked.${COMPONENT} -bin -base ${ADDRESS} ${ROM_MODULE} ${C_ABSSYM} \
              -map > map.${COMPONENT}
        truncate map.${COMPONENT} linked.${COMPONENT}
        ${CP} linked.${COMPONENT} ${LINKDIR}.${COMPONENT} ${CPFLAGS}
        @echo ${COMPONENT}: rom_link complete

#---------------------------------------------------------------------------
# Dynamic dependencies:
o.share:	c.share
o.share:	^.fslib.h.ker
o.share:	C:h.kernel
o.share:	^.fslib.h.ModuleWrap
o.share:	C:h.kernel
o.share:	^.fslib.h.lookup
o.share:	^.rmalib.h.ralloc
o.share:	^.fslib.h.util
o.share:	^.fslib.h.interface
o.share:	^.fslib.h.lookup
o.share:	h.remswis
o.share:	h.errnum
o.share:	^.fslib.h.debug
o.share:	C:h.swis
o.share:	h.how
o.share:	h.msgproc
o.share:	^.fslib.h.ticker
o.share:	h.modface
o.share:	h.freeway
o.svcprint:	c.svcprint
o.svcprint:	C:h.kernel
o.svcprint:	C:h.swis
o.svcprint:	^.fslib.h.debug
o.irqs: s.irqs
o.irqs: <Hdr$Dir>.Global.ListOpts
o.irqs: <Hdr$Dir>.Global.Macros
o.irqs: <Hdr$Dir>.Global.System
o.irqs: Hdr:SWIs
o.irqs: Hdr:CPU.Generic26
o.irqs: Hdr:IO.GenericIO
o.irqs: Hdr:RISCOS
o.resourcefs:	c.resourcefs
o.resourcefs:	C:h.swis
o.resourcefs:	C:h.kernel
o.resourcefs:	h.resourcefs
o.resourcefs:	^.rmalib.h.ralloc
o.resourcefs:	^.fslib.h.debug
o.resourcefs:	^.fslib.h.interface
o.resourcefs:	^.fslib.h.util
o.resourcefs:	^.fslib.h.lookup
o.sharep:	c.sharep
o.sharep:	^.fslib.h.ker
o.sharep:	C:h.kernel
o.sharep:	^.fslib.h.ModuleWrap
o.sharep:	C:h.kernel
o.sharep:	^.fslib.h.lookup
o.sharep:	^.fslib.h.util
o.sharep:	^.fslib.h.interface
o.sharep:	^.fslib.h.lookup
o.sharep:	h.remswis
o.sharep:	h.errnum
o.sharep:	^.fslib.h.debug
o.sharep:	C:h.swis
o.sharep:	h.how
o.sharep:	h.msgproc
o.sharep:	^.fslib.h.ticker
o.sharep:	h.modface
o.sharep:	C:h.swis
o.sharep:	h.freeway
o.sharep:	^.rmalib.h.ralloc
o.shared:	c.shared
o.shared:	c.daemon
o.shared:	^.fslib.h.debug
o.shared:	^.fslib.h.ker
o.shared:	C:h.kernel
o.shared:	C:h.swis
o.shared:	h.remswis
o.shared:	h.errnum
o.shared:	^.rmalib.h.ralloc
o.shared:	^.fslib.h.interface
o.shared:	^.fslib.h.ModuleWrap
o.shared:	C:h.kernel
o.shared:	^.fslib.h.util
o.shared:	^.fslib.h.lookup
o.shared:	^.fslib.h.fscore
o.shared:	^.fslib.h.evil
o.shared:	^.fslib.h.ticker
o.shared:	h.msgproc
o.shared:	h.remote
o.shared:	h.freeway
o.shared:	h.modface
o.shared:	h.how
o.shared:	h.how
o.sharefiler:	c.sharefiler
o.sharefiler:	c.filer
o.sharefiler:	^.fslib.h.ker
o.sharefiler:	C:h.kernel
o.sharefiler:	C:h.swis
o.sharefiler:	^.fslib.h.ModuleWrap
o.sharefiler:	C:h.kernel
o.sharefiler:	^.fslib.h.util
o.sharefiler:	^.fslib.h.interface
o.sharefiler:	^.fslib.h.lookup
o.sharefiler:	^.fslib.h.cstart
o.sharefiler:	RISC_OSLib:h.wimp
o.sharefiler:	RISC_OSLib:h.os
o.sharefiler:	RISC_OSLib:h.sprite
o.sharefiler:	h.remswis
o.sharefiler:	h.errnum
o.sharefiler:	^.rmalib.h.ralloc
o.sharefiler:	h.modface
o.sharefiler:	h.how
o.sharefiler:	h.wimpswis
o.sharefiler:	h.freeway
o.sharefiler:	^.fslib.h.util
o.sharefs:	c.sharefs
o.sharefs:	c.remotefs
o.sharefs:	^.fslib.h.debug
o.sharefs:	^.fslib.h.FS
o.sharefs:	^.fslib.h.ker
o.sharefs:	C:h.kernel
o.sharefs:	C:h.swis
o.sharefs:	^.fslib.h.interface
o.sharefs:	^.fslib.h.ModuleWrap
o.sharefs:	C:h.kernel
o.sharefs:	^.fslib.h.util
o.sharefs:	^.fslib.h.lookup
o.sharefs:	^.fslib.h.fscore
o.sharefs:	^.fslib.h.lookup
o.sharefs:	^.fslib.h.visdelay
o.sharefs:	C:h.swis
o.sharefs:	h.msgproc
o.sharefs:	h.remote
o.sharefs:	h.remswis
o.sharefs:	h.errnum
o.sharefs:	h.econetv
o.sharefs:	^.fslib.h.evil
o.sharefs:	^.rmalib.h.ralloc
o.sharefs:	^.fslib.h.ticker
o.sharefs:	h.freeway
o.sharefs:	h.resourcefs
o.sharefs:	h.modface
o.sharefs:	h.how
o.sharehow:	c.sharehow
o.sharehow:	h.how
o.sharehow:	^.fslib.h.util
o.sharehow:	^.fslib.h.interface
o.sharehow:	C:h.kernel
o.sharehow:	^.fslib.h.lookup
o.shareinet:	c.shareinet
o.shareinet:	c.internet
o.shareinet:	^.fslib.h.debug
o.shareinet:	^.fslib.h.ker
o.shareinet:	C:h.kernel
o.shareinet:	C:h.swis
o.shareinet:	^.fslib.h.interface
o.shareinet:	^.fslib.h.ModuleWrap
o.shareinet:	C:h.kernel
o.shareinet:	^.fslib.h.util
o.shareinet:	^.fslib.h.lookup
o.shareinet:	^.fslib.h.fscore
o.shareinet:	^.fslib.h.esc
o.shareinet:	^.fslib.h.evil
o.shareinet:	^.rmalib.h.ralloc
o.shareinet:	h.remswis
o.shareinet:	h.errnum
o.shareinet:	^.fslib.h.ticker
o.shareinet:	h.window
o.shareinet:	h.msgproc
o.shareinet:	h.freeway
o.shareinet:	h.resourcefs
o.shareinet:	h.modface
o.shareinet:	h.how
o.shareinet:	h.tcplibs
o.shareinet:	InetInc:sys.h.types
o.shareinet:	InetInc:sys.h.time
o.shareinet:	InetInc:netinet.h.in
o.shareinet:	InetInc:sys.h.socket
o.shareinet:	InetInc:sys.h.ioctl
o.shareinet:	InetInc:sys.h.ttychars
o.shareinet:	InetInc:sys.h.ttydev
o.shareinet:	InetInc:h.netdb
o.shareinet:	InetInc:sys.h.errno
o.shareinet:	InetInc:sys.^.h.errno
o.shareinet:	C:h.kernel
o.shareinet:	InetInc:net.h.if
o.shareinet:	InetInc:sys.h.mbuf
o.shareinet:	InetInc:net.h.if_arp
o.shareinet:	InetInc:sys.h.socket
o.window:	c.window
o.window:	^.fslib.h.debug
o.window:	^.fslib.h.ker
o.window:	C:h.kernel
o.window:	C:h.swis
o.window:	^.fslib.h.interface
o.window:	^.fslib.h.ModuleWrap
o.window:	C:h.kernel
o.window:	^.fslib.h.util
o.window:	^.fslib.h.lookup
o.window:	^.fslib.h.fscore
o.window:	^.fslib.h.evil
o.window:	^.rmalib.h.ralloc
o.window:	^.fslib.h.visdelay
o.window:	^.fslib.h.esc
o.window:	h.remswis
o.window:	h.errnum
o.window:	h.stream
o.window:	h.window
o.window:	h.msgproc
o.window:	^.fslib.h.ticker
