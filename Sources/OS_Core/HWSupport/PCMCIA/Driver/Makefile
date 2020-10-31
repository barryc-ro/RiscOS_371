# Makefile for PCMCIA Driver
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name         Description
# ----       ----         -----------
# 15-Jul-94  AMcC         Created.
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
CFLAGS  = -c -depend !Depend ${INCLUDES} ${DFLAGS} -zM -ff
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
# Include files
#
INCLUDES = -IC:

#
# Program specific options:
#
COMPONENT = PCMCIA_Drv
RELOC_MOD = rm.PCMCIA_Drv
TARGET    = aof.PCMCIA_Drv

#
# Export Paths for Messages module
#
RESDIR = <resource$dir>.Resources2.PCMCIA.Driver

OBJS =\
 o.debug\
 o.enableIRQ\
 o.error\
 o.errors\
 o.functions\
 o.header\
 o.hwops\
 o.irq_jump\
 o.init\
 o.misc\
 o.resources\
 o.services\
 o.variables

#
# Rule patterns
#
.c.o:;      ${CC} ${CFLAGS} -o $@ $<
.s.o:;      ${AS} ${AFLAGS} $< $@
.cmhg.o:;    ${CMHG} $< $@

#
# Build rules:
#
all: ${RELOC_MOD}
        @echo ${COMPONENT}: all built

rom: ${TARGET}
        @echo ${COMPONENT}: all built (rom version)

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
        ${MKDIR} ${RESDIR}
        ${CP} Resources.${LOCALE}.Messages ${RESDIR}.Messages ${CPFLAGS}
        @echo ${COMPONENT}: resource files copied

# ROM target (re-linked at ROM Image build time)
#
${TARGET}: ${OBJS} ${ROMCSTUBS}
        ${LD} -o $@ -aof ${OBJS} ${ROMCSTUBS}

#
# Final link for the ROM Image (using given base address)
#
rom_link:
        ${MKDIR} linked
        ${MKDIR} map
        ${LD} -o linked.${COMPONENT} -map -bin -base ${ADDRESS} ${TARGET} ${ABSSYM} > map.${COMPONENT}
        truncate map.${COMPONENT} linked.${COMPONENT}
        ${CP} linked.${COMPONENT} ${LINKDIR}.${COMPONENT} ${CPFLAGS}
        @echo ${COMPONENT}: rom_link complete

${RELOC_MOD}: ${OBJS} ${CLIB}
        ${LD} -o $@ -Module ${OBJS} ${CLIB}

# Dynamic dependencies:
o.debug:	c.debug
o.debug:	C:h.swis
o.debug:	C:h.kernel
o.debug:	C:h.kernel
o.enableIRQ: s.enableIRQ
o.error:	c.error
o.error:	C:h.kernel
o.error:	h.Defs
o.error:	h.Structs
o.error:	h.Error
o.error:	h.Debug
o.error:	h.Variables
o.errors: s.errors
o.functions:	c.functions
o.functions:	C:h.kernel
o.functions:	C:h.time
o.functions:	h.Defs
o.functions:	h.Structs
o.functions:	h.Hardware
o.functions:	h.Variables
o.functions:	h.Functions
o.functions:	h.Misc
o.functions:	h.Error
o.functions:	h.HWOps
o.functions:	h.Debug
o.hwops:	c.hwops
o.hwops:	C:h.kernel
o.hwops:	C:h.time
o.hwops:	h.Defs
o.hwops:	h.Structs
o.hwops:	h.Error
o.hwops:	h.hwops
o.hwops:	h.hardware
o.hwops:	h.Misc
o.hwops:	h.Variables
o.hwops:	h.Interrupts
o.hwops:	h.functions
o.hwops:	h.Debug
o.irq_jump: s.irq_jump
o.init:	c.init
o.init:	C:h.kernel
o.init:	h.Defs
o.init:	h.Structs
o.init:	h.Variables
o.init:	h.Init
o.init:	h.Resources
o.init:	h.HWOps
o.init:	h.Error
o.init:	h.Misc
o.init:	h.Debug
o.misc:	c.misc
o.misc:	C:h.kernel
o.misc:	h.Defs
o.misc:	h.Structs
o.misc:	h.Variables
o.misc:	h.Misc
o.misc:	h.Error
o.misc:	h.Hardware
o.misc:	h.Functions
o.misc:	h.HWOps
o.misc:	h.Interrupts
o.misc:	h.Debug
o.resources:	c.resources
o.resources:	C:h.kernel
o.resources:	h.Defs
o.resources:	h.Structs
o.resources:	h.Resources
o.resources:	h.error
o.resources:	h.variables
o.resources:	h.Debug
o.services:	c.services
o.services:	C:h.kernel
o.services:	h.Defs
o.services:	h.Structs
o.services:	h.Variables
o.services:	h.Services
o.services:	h.Resources
o.services:	h.Misc
o.services:	h.Debug
o.variables:	c.variables
o.variables:	C:h.kernel
o.variables:	h.Defs
o.variables:	h.Structs
o.variables:	h.Hardware
