# Makefile for Freeway
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name   Description
# ----       ----   -----------
# 21-Nov-94  AMcC   Created
# 05-Jan-95  AMcC   Added resources: rule and paths
#

#
# Component specific options:
#
COMPONENT  = Freeway
ROM_MODULE = aof.Freeway
RDIR       = Resources
LDIR       = ${RDIR}.${LOCALE}
RESDIR     = ^.^.AUNMsgs.Resources.${Locale}.Resources.${COMPONENT}

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

AFLAGS  = -depend !Depend -I<Hdr$Dir>.Global.,<Hdr$Dir>.Interface. -Stamp -quit
CFLAGS  = -ansi -zM -zps1 -ffah ${INCLUDES} ${DFLAGS}
DFLAGS  = -DAUTH32
CPFLAGS = ~cfr~v
WFLAGS  = ~c~v

INCLUDES  = -IINetInc:

#
# Libraries
#
ANSILIB   = CLib:o.ansilib
CLIB      = CLIB:o.stubs
RLIB      = RISCOSLIB:o.risc_oslib
ROMCSTUBS = RISCOSLIB:o.romcstubs
ABSSYM    = RISC_OSLib:o.abssym
C_ABSSYM  = RISCOSLIB:o.c_abssym

SOCKLIBZM = ^.^.libs.socklib.socklibzm

OBJS =\
 o.fwhdr\
 o.inetfn\
 o.irqs\
 o.module\
 o.objects

#
# Rule patterns
#
.c.o:;      ${CC} -c -depend !Depend ${CFLAGS} -o $@ $<
.c.s:;      ${CC} -S ${CFLAGS} $<
.s.o:;      ${AS} ${AFLAGS} $< $@
.cmhg.o:;   ${CMHG} -o $@ $<

#
# Main rules:
#
#
rom: ${ROM_MODULE}
        @echo ${COMPONENT}: Module built (ROM)

install_rom: ${ROM_MODULE}
        ${CP} ${ROM_MODULE} ${INSTDIR}.${COMPONENT} ${CPFLAGS}
        @echo ${COMPONENT}: Module installed (ROM)

resources:
        @echo ${COMPONENT}: Resources in AUNMsgs

clean:
        ${WIPE} o.* ${WFLAGS}
        ${WIPE} rm.* ${WFLAGS}
        ${RM} ${ROM_MODULE}
        ${WIPE} linked.* ${WFLAGS}
        ${WIPE} map.* ${WFLAGS}
        @echo ${COMPONENT}: cleaned

clean_all: clean
        ${WIPE} o.* ${WFLAGS}
        @echo ${COMPONENT}: imported objects removed

${ROM_MODULE}: ${OBJS} ${SOCKLIBZM} ${ROMCSTUBS}
        ${MKDIR} aof
        ${LD} -o $@ -aof ${OBJS} ${SOCKLIBZM} ${ROMCSTUBS}

rm.Freeway: ${OBJS} ${SOCKLIBZM} ${CLIB}
        ${LD} -o $@ -module ${OBJS} ${SOCKLIBZM} ${CLIB}


# final link for ROM Image (using given base address)
rom_link:
        ${MKDIR} linked
        ${MKDIR} map
        ${LD} -o linked.${COMPONENT} -bin -base ${ADDRESS} ${ROM_MODULE} ${C_ABSSYM} \
              -map > map.${COMPONENT}
        truncate map.${COMPONENT} linked.${COMPONENT}
        ${CP} linked.${COMPONENT} ${LINKDIR}.${COMPONENT} ${CPFLAGS}
        @echo ${COMPONENT}: rom_link complete

#---------------------------------------------------------------------------
# Dynamic dependencies:
o.inetfn:	c.inetfn
o.inetfn:	INetInc:sys.h.types
o.inetfn:	INetInc:netinet.h.in
o.inetfn:	h.module
o.inetfn:	C:h.kernel
o.inetfn:	INetInc:netinet.h.in
o.irqs: s.irqs
o.irqs: <Hdr$Dir>.Global.ListOpts
o.irqs: <Hdr$Dir>.Global.Macros
o.irqs: <Hdr$Dir>.Global.System
o.irqs: Hdr:SWIs
o.irqs: Hdr:CPU.Generic26
o.irqs: Hdr:IO.GenericIO
o.irqs: Hdr:RISCOS
o.module:	c.module
o.module:	INetInc:sys.h.types
o.module:	INetInc:sys.h.uio
o.module:	INetInc:sys.h.socket
o.module:	INetInc:sys.h.time
o.module:	INetInc:sys.h.time
o.module:	INetInc:sys.h.ioctl
o.module:	INetInc:sys.h.ttychars
o.module:	INetInc:sys.h.ttydev
o.module:	INetInc:sys.h.errno
o.module:	INetInc:sys.^.h.errno
o.module:	C:h.kernel
o.module:	INetInc:sys.h.dcistructs
o.module:	INetInc:netinet.h.in
o.module:	INetInc:net.h.if
o.module:	INetInc:sys.h.mbuf
o.module:	INetInc:net.h.if_arp
o.module:	INetInc:sys.h.socket
o.module:	C:h.kernel
o.module:	C:h.swis
o.module:	h.module
o.module:	C:h.kernel
o.module:	INetInc:netinet.h.in
o.module:	h.stubs
o.module:	C:h.kernel
o.module:	INetInc:sys.h.types
o.module:	INetInc:sys.h.socket
o.module:	INetInc:sys.h.socketvar
o.objects:	c.objects
o.objects:	C:h.kernel
o.objects:	C:h.swis
o.objects:	INetInc:sys.h.types
o.objects:	INetInc:sys.h.uio
o.objects:	INetInc:sys.h.socket
o.objects:	INetInc:netinet.h.in
o.objects:	INetInc:net.h.if
o.objects:	INetInc:sys.h.mbuf
o.objects:	INetInc:net.h.if_arp
o.objects:	INetInc:sys.h.socket
o.objects:	h.module
o.objects:	C:h.kernel
o.objects:	INetInc:netinet.h.in
o.objects:	h.stubs
o.objects:	C:h.kernel
o.objects:	INetInc:sys.h.types
o.objects:	INetInc:sys.h.socket
o.objects:	INetInc:sys.h.socketvar
