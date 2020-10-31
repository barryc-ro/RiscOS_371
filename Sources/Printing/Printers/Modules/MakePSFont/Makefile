# Makefile for MakePSFont
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name         Description
# ----       ----         -----------
# 14-Sep-94  AMcC         Created.
# 25-Nov-94  MJS          s.init added to source
#

#
# Paths
#
EXP_HDR = <export$dir>

#
# Program specific options:
#
COMPONENT  = MakePSFont
MODULE     = rm.MakePSFont
ROM_MODULE = aof.MakePSFont
EXPORTS    = ${EXP_HDR}.MakePSFont
RDIR      = Resources
LDIR      = ${RDIR}.${LOCALE}


#
# Export Paths for Messages module
#
RESDIR  = <resource$dir>.Resources2.${COMPONENT}

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
CFLAGS  = -c -depend !Depend ${INCLUDES} ${DFLAGS} -zM
CPFLAGS = ~cfr~v
WFLAGS  = ~c~v

#
# Libraries
#
CLIB      = CLIB:o.stubs
RLIB      = RISCOSLIB:o.risc_oslib
RSTUBS    = RISCOSLIB:o.rstubs
ROMCSTUBS = RISCOSLIB:o.romcstubs
ROMSTUBS  = RISCOSLIB:o.romstubs
ABSSYM    = RISCOSLIB:o.abssym

#
# Include files
#
INCLUDES = -IC:

OBJS =\
 o.convert\
 o.float\
 o.init \
 o.mheader\
 o.module\
 o.provide\
 o.registry\
 o.swicall\
 o.use

#
# Rule patterns
#
.c.o:;      ${CC} ${CFLAGS} -o $@ $<
.s.o:;      ${AS} ${AFLAGS} $< $@
.cmhg.o:;   ${CMHG} $< $@

#
# Build rules:
#
all: ${MODULE}
        @echo ${COMPONENT}: all built (disc)

rom: ${ROM_MODULE}
        @echo ${COMPONENT}: all built (rom)

export: ${EXPORTS}
        @echo ${COMPONENT}: export complete

install: ${MODULE}
        ${CP} ${MODULE} ${INSTDIR}.${COMPONENT} ${CPFLAGS}
        Access ${INSTDIR}.${COMPONENT} lr/r
        @echo ${COMPONENT}: installed (disc)

install_rom: ${ROM_MODULE}
        ${CP} ${ROM_MODULE} ${INSTDIR}.${COMPONENT} ${CPFLAGS}
        @echo ${COMPONENT}: installed (rom)

resources:
        ${MKDIR} ${RESDIR}
        ${CP} ${LDIR}.Messages  ${RESDIR}.Messages  ${CPFLAGS}
        @echo ${COMPONENT}: resource files copied to Messages module

clean:
        ${WIPE} o.* ${WFLAGS}
        ${RM} ${MODULE}
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
        ${LD} -o linked.${COMPONENT} -map -bin -base ${ADDRESS} ${ROM_MODULE} ${ABSSYM} > map.${COMPONENT}
        truncate map.${COMPONENT} linked.${COMPONENT}
        ${CP} linked.${COMPONENT} ${LINKDIR}.${COMPONENT} ${CPFLAGS}
        @echo ${COMPONENT}: rom_link complete

${EXP_HDR}.MakePSFont: hdr.MakePSFont
        ${CP} hdr.MakePSFont $@ ${CPFLAGS}

# Dynamic dependencies:
o.convert:	c.convert
o.convert:	h.module
o.convert:	C:h.kernel
o.convert:	C:h.swis
o.convert:	h.misc
o.convert:	h.swicall
o.convert:	C:h.kernel
o.convert:	C:h.swis
o.convert:	h.convert
o.convert:	h.convert
o.float: s.float
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
o.module:	c.module
o.module:	h.module
o.module:	C:h.kernel
o.module:	C:h.swis
o.module:	h.misc
o.module:	h.swicall
o.module:	C:h.kernel
o.module:	C:h.swis
o.module:	h.convert
o.module:	h.swicall
o.module:	C:h.kernel
o.module:	C:h.swis
o.provide:	c.provide
o.provide:	h.module
o.provide:	C:h.kernel
o.provide:	C:h.swis
o.provide:	h.misc
o.provide:	h.swicall
o.provide:	C:h.kernel
o.provide:	C:h.swis
o.provide:	h.convert
o.provide:	h.registry
o.provide:	h.misc
o.provide:	h.use
o.registry:	c.registry
o.registry:	h.module
o.registry:	C:h.kernel
o.registry:	C:h.swis
o.registry:	h.misc
o.registry:	h.swicall
o.registry:	C:h.kernel
o.registry:	C:h.swis
o.registry:	h.convert
o.swicall: s.swicall
o.use:	c.use
o.use:	h.module
o.use:	C:h.kernel
o.use:	C:h.swis
o.use:	h.misc
o.use:	h.swicall
o.use:	C:h.kernel
o.use:	C:h.swis
o.use:	h.convert
