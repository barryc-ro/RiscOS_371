# Makefile for RemPrnSpt (Support for AUN Access remote printing)
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name         Description
# ----       ----         -----------
# 04-Jul-94  AMcC         Created.
# 25-Nov-94  MJS          add s.init to source
#

#
# Program specific options:
#
COMPONENT  = RemPrnSpt
MODULE     = rm.RemPrnSpt
ROM_MODULE = aof.RemPrnSpt
LDIR       = ${LOCALE}

# Messages module:
MSGSMOD   = rm.RemPrnMsgs
MESSAGES  = ${LDIR}.Messages
MODNAME   = RemotePrinterMessages
HELPSTR   = "RemotePrinterMessages (English)"
RESPATH   = Resources.RemotePrin.Messages
VERSION   = 1.03

#
# Generic options:
#
MKDIR   = cdir
AS      = objasm
CC      = cc
CMHG    = cmhg
CP      = copy
LD      = link
MODGEN  = modgen
RM      = remove
WIPE    = -wipe

AFLAGS  = -depend !Depend -Stamp -quit
CFLAGS  = -c -depend !Depend ${INCLUDES} ${DFLAGS} -zM -wp
DFLAGS  = -DMessages
# For Disc-based !Printers
#DFLAGS  = -DMessages -DDisc
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
ABSSYM    = RISCOSLIB:o.abssym
C_ABSSYM  = RISCOSLIB:o.c_abssym

#
# Include files
#
INCLUDES = -IC:

OBJS =\
 debug.o\
 eventqueue.o\
 init.o\
 list.o\
 module.o\
 msgs.o\
 msgtrans.o\
 header.o\
 strextra.o

#
# Rule patterns
#
.c.o:;      ${CC} ${CFLAGS} -o $@ $<
.s.o:;      ${AS} ${AFLAGS} $< $@
.cmhg.o:;   ${CMHG} $< $@

#
# Build rules: Disc
#
all: ${MODULE} ${MSGSMOD}
        @echo ${COMPONENT}: all built (disc)

install: ${MODULE} ${MSGSMOD}
        ${CP} ${MODULE}  ${INSTDIR}.${COMPONENT} ${CPFLAGS}
        ${CP} ${MSGSMOD} ${INSTDIR}.RemPrnMsgs   ${CPFLAGS}
        Access ${INSTDIR}.${COMPONENT} lr/r
        Access ${INSTDIR}.RemPrnMsgs lr/r
        @echo ${COMPONENT}: installed (disc)

#
# Build rules: ROM
#
rom: ${ROM_MODULE}
        @echo ${COMPONENT}: all built (rom)

install_rom: ${ROM_MODULE}
        ${CP} ${ROM_MODULE} ${INSTDIR}.${COMPONENT} ${CPFLAGS}
        @echo ${COMPONENT}: installed (rom)

export: ${EXPORTS}
        @echo ${COMPONENT}: export complete

resources:
        ${MKDIR} ${RESDIR}.RemotePrin
        ${CP} ${LDIR}.Messages ${RESDIR}.RemotePrin.Messages ${CPFLAGS}
        @echo ${COMPONENT}: resource files will be included in Messages Module

clean:
        ${WIPE} o.* ${WFLAGS}
        ${RM} ${MODULE}
        ${RM} ${MSGSMOD}
        ${RM} ${ROM_MODULE}
        ${RM} linked.${COMPONENT}
        ${RM} map.${COMPONENT}
        @echo ${COMPONENT}: cleaned

${MODULE}: ${OBJS} ${CLIB}
        ${LD} -o $@ -Module ${OBJS} ${CLIB}

# Partially linked AOF object file
${ROM_MODULE}: ${OBJS} ${ROMCSTUBS}
        ${LD} -o $@ -aof ${OBJS} ${ROMCSTUBS}

#
# Final link for the ROM Image {using given base address}
#
rom_link:
        ${LD} -o linked.${COMPONENT} -map -bin -base ${ADDRESS} ${ROM_MODULE} ${C_ABSSYM} > map.${COMPONENT}
        truncate map.${COMPONENT} linked.${COMPONENT}
        ${CP} linked.${COMPONENT} ${LINKDIR}.${COMPONENT} ${CPFLAGS}
        @echo ${COMPONENT}: rom_link complete

${MSGSMOD}: ${MESSAGES} Makefile
        ${MODGEN} $@ ${MODNAME} ${HELPSTR} ${VERSION} ${MESSAGES} ${RESPATH}

# Dynamic dependencies:
o.debug:	c.debug
o.debug:	C:h.swis
o.debug:	C:h.kernel
o.debug:	C:h.kernel
o.eventqueue:	c.eventqueue
o.eventqueue:	C:h.kernel
o.eventqueue:	C:h.swis
o.eventqueue:	h.RemPrnSpt
o.eventqueue:	h.debug
o.eventqueue:	h.msgs
o.eventqueue:	h.List
o.eventqueue:	h.EventQueue
o.init: s.init
o.init: hdr:ListOpts
o.init: hdr:Macros
o.init: hdr:System
o.init: Hdr:SWIs
o.init: Hdr:CPU.Generic26
o.init: Hdr:IO.GenericIO
o.init: Hdr:RISCOS
o.init: hdr:ModHand
o.init: hdr:Services
o.init: hdr:FSNumbers
o.init: hdr:HighFSI
o.init: hdr:NewErrors
o.init: hdr:MsgTrans
o.init: hdr:PDriver
o.list:	c.list
o.list:	C:h.kernel
o.list:	h.RemPrnSpt
o.list:	h.Debug
o.list:	h.Errors
o.list:	h.ListP
o.list:	h.Msgs
o.module:	c.module
o.module:	C:h.kernel
o.module:	C:h.swis
o.module:	h.Module
o.module:	h.Freeway
o.module:	h.Pollword
o.module:	h.Debug
o.module:	h.Msgs
o.module:	h.StrExtra
o.module:	h.EventQueue
o.msgs:	c.msgs
o.msgs:	C:h.kernel
o.msgs:	C:h.swis
o.msgs:	h.debug
o.msgs:	h.msgs
o.msgs:	h.MsgTrans
o.msgs:	h.Module
o.msgtrans:	c.msgtrans
o.msgtrans:	C:h.kernel
o.msgtrans:	C:h.swis
o.msgtrans:	h.MsgTrans
o.msgtrans:	h.debug
o.strextra:	c.strextra
o.strextra:	C:h.kernel
o.strextra:	C:h.swis
