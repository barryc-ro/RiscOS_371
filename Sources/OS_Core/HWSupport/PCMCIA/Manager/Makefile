# Makefile for PCMCIA Manager
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name         Description
# ----       ----         -----------
# 15-Jul-94  AMcC         Created.
# 11-Oct-94  WT           Constituent files changed

#
# Paths
#
EXP_HDR = <export$dir>

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
COMPONENT = PCMCIA_Mgr
RELOC_MOD = rm.PCMCIA_Mgr
TARGET    = aof.PCMCIA_Mgr
EXPORTS   = ${EXP_HDR}.PCMCIA
RDIR      = Resources
LDIR      = ${RDIR}.${LOCALE}

#
# Export Paths for Messages module
#
RESDIR = <resource$dir>.Resources2.PCMCIA.Manager

OBJS =\
 CDIrqVenr.o\
 Cis.o\
 Debug.o\
 Driver.o\
 Driver_s.o\
 Error.o\
 Errors.o\
 FSOp.o\
 Header.o\
 Init.o\
 Interrupts.o\
 Misc.o\
 PowerOp.o\
 Read.o\
 Read_s.o\
 Resources.o\
 Services.o\
 StarCmd.o\
 Swi.o\
 Variables.o\
 Write.o\
 Write_s.o

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
        ${WIPE} linked ${WFLAGS}
        ${WIPE} map ${WFLAGS}
        ${RM} ${TARGET}
        @echo ${COMPONENT}: cleaned

resources:
        ${MKDIR} ${RESDIR}.^.^.PCMCIA
        ${MKDIR} ${RESDIR}
        ${CP} ${LDIR}.Messages ${RESDIR}.Messages ${CPFLAGS}
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

${EXP_HDR}.PCMCIA: hdr.PCMCIA
        ${CP} hdr.PCMCIA $@ ${CPFLAGS}

# Dynamic dependencies:
o.CDIrqVenr: s.CDIrqVenr
o.Cis:	c.Cis
o.Cis:	C:h.kernel
o.Cis:	h.Defs
o.Cis:	h.Structs
o.Cis:	h.Variables
o.Cis:	h.Read
o.Cis:	h.Driver
o.Cis:	h.Error
o.Cis:	h.Debug
o.Cis:	h.Cis
o.Cis:	h.Misc
o.Cis:	h.Swi
o.Debug:	c.Debug
o.Debug:	C:h.swis
o.Debug:	C:h.kernel
o.Debug:	C:h.kernel
o.Driver:	c.Driver
o.Driver:	C:h.kernel
o.Driver:	h.Defs
o.Driver:	h.Structs
o.Driver:	h.Variables
o.Driver:	h.Read
o.Driver:	h.Write
o.Driver:	h.Error
o.Driver:	h.Cis
o.Driver:	h.FSOp
o.Driver:	h.Interrupts
o.Driver:	h.misc
o.Driver:	h.Swi
o.Driver:	h.Driver
o.Driver:	h.Debug
o.Driver_s: s.Driver_s
o.Error:	c.Error
o.Error:	C:h.kernel
o.Error:	h.Defs
o.Error:	h.Structs
o.Error:	h.Error
o.Error:	h.Debug
o.Error:	h.Variables
o.Errors: s.Errors
o.FSOp:	c.FSOp
o.FSOp:	C:h.kernel
o.FSOp:	h.Defs
o.FSOp:	h.Structs
o.FSOp:	h.Variables
o.FSOp:	h.Error
o.FSOp:	h.Swi
o.FSOp:	h.Debug
o.Init:	c.Init
o.Init:	C:h.kernel
o.Init:	h.Defs
o.Init:	h.Structs
o.Init:	h.Variables
o.Init:	h.Init
o.Init:	h.Resources
o.Init:	h.Error
o.Init:	h.Misc
o.Init:	h.Driver
o.Init:	h.Services
o.Init:	h.Debug
o.Interrupts:	c.Interrupts
o.Interrupts:	C:h.kernel
o.Interrupts:	C:h.time
o.Interrupts:	h.Defs
o.Interrupts:	h.Structs
o.Interrupts:	h.Variables
o.Interrupts:	h.Driver
o.Interrupts:	h.Error
o.Interrupts:	h.Debug
o.Interrupts:	h.Swi
o.Interrupts:	h.Cis
o.Interrupts:	h.Misc
o.Interrupts:	h.Interrupts
o.Interrupts:	h.Services
o.Misc:	c.Misc
o.Misc:	C:h.kernel
o.Misc:	h.Defs
o.Misc:	h.Structs
o.Misc:	h.Misc
o.Misc:	h.Variables
o.Misc:	h.Driver
o.Misc:	h.Cis
o.Misc:	h.Error
o.Misc:	h.Debug
o.PowerOp:	c.PowerOp
o.PowerOp:	C:h.kernel
o.PowerOp:	h.Defs
o.PowerOp:	h.Structs
o.PowerOp:	h.Variables
o.PowerOp:	h.Error
o.PowerOp:	h.Debug
o.Read:	c.Read
o.Read:	C:h.kernel
o.Read:	h.Defs
o.Read:	h.Structs
o.Read:	h.Variables
o.Read:	h.Read
o.Read:	h.Driver
o.Read:	h.Error
o.Read:	h.Debug
o.Read_s: s.Read_s
o.Resources:	c.Resources
o.Resources:	C:h.kernel
o.Resources:	h.Defs
o.Resources:	h.Structs
o.Resources:	h.Resources
o.Resources:	h.error
o.Resources:	h.variables
o.Resources:	h.Debug
o.Services:	c.Services
o.Services:	C:h.kernel
o.Services:	h.Defs
o.Services:	h.Structs
o.Services:	h.Variables
o.Services:	h.Services
o.Services:	h.Resources
o.Services:	h.Misc
o.Services:	h.powerop
o.Services:	h.Debug
o.StarCmd:	c.StarCmd
o.StarCmd:	C:h.kernel
o.StarCmd:	h.Defs
o.StarCmd:	h.Structs
o.StarCmd:	h.Variables
o.StarCmd:	h.Error
o.StarCmd:	h.Cis
o.StarCmd:	h.StarCmd
o.StarCmd:	h.Driver
o.StarCmd:	h.Debug
o.Swi:	c.Swi
o.Swi:	C:h.kernel
o.Swi:	h.Defs
o.Swi:	h.Structs
o.Swi:	h.Variables
o.Swi:	h.Driver
o.Swi:	h.Read
o.Swi:	h.Write
o.Swi:	h.Error
o.Swi:	h.Cis
o.Swi:	h.FSOp
o.Swi:	h.PowerOp
o.Swi:	h.Interrupts
o.Swi:	h.misc
o.Swi:	h.Swi
o.Swi:	h.Debug
o.Variables:	c.Variables
o.Variables:	C:h.kernel
o.Variables:	h.Defs
o.Variables:	h.Structs
o.Write:	c.Write
o.Write:	C:h.kernel
o.Write:	h.Defs
o.Write:	h.Structs
o.Write:	h.Variables
o.Write:	h.Write
o.Write:	h.Driver
o.Write:	h.Error
o.Write:	h.Debug
o.Write_s: s.Write_s
