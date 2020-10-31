# Makefile for PCCardFS
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name         Description
# ----       ----         -----------
# 15-Jul-94  AMcC         Created.
# 11-Oct-94  WT           Changed constituent files.

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
COMPONENT   = PCCardFS
RELOC_MOD   = rm.PCCardFS
TARGET      = aof.PCCardFS
EXPORTS     = ${EXP_HDR}.PCCardFS
RDIR        = Resources
LDIR        = ${RDIR}.${LOCALE}

#
# Export Paths for Messages module
#
RESDIR = <resource$dir>.Resources2.${COMPONENT}

OBJS =\
 Debug.o\
 DefaultCIS.o\
 DiscOp.o\
 Error.o\
 FS_Veneer.o\
 Header.o\
 Init.o\
 Misc.o\
 MiscOp.o\
 Resources.o\
 Services.o\
 StarCmd.o\
 Swi.o\
 Variables.o

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
        ${RM} ${RELOC_MOD}
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

rom_link:
        ${MKDIR} linked
        ${MKDIR} map
        ${LD} -o linked.${COMPONENT} -map -bin -base ${ADDRESS} ${TARGET} ${ABSSYM} > map.${COMPONENT}
        truncate map.${COMPONENT} linked.${COMPONENT}
        ${CP} linked.${COMPONENT} ${LINKDIR}.${COMPONENT} ${CPFLAGS}
        @echo ${COMPONENT}: rom_link complete

${RELOC_MOD}: ${OBJS} ${CLIB}
        ${LD} -o $@ -Module ${OBJS} ${CLIB}

${EXP_HDR}.PCCardFS: hdr.PCCardFS
        ${CP} hdr.PCCardFS $@ ${CPFLAGS}

# Dynamic dependencies:
o.Debug:	c.Debug
o.Debug:	C:h.swis
o.Debug:	C:h.kernel
o.Debug:	C:h.kernel
o.DefaultCIS: s.DefaultCIS
o.DiscOp:	c.DiscOp
o.DiscOp:	C:h.kernel
o.DiscOp:	h.Defs
o.DiscOp:	h.Structs
o.DiscOp:	h.Variables
o.DiscOp:	h.DiscOp
o.DiscOp:	h.Error
o.DiscOp:	h.Misc
o.DiscOp:	h.Debug
o.Error:	c.Error
o.Error:	C:h.kernel
o.Error:	h.Defs
o.Error:	h.Structs
o.Error:	h.Error
o.Error:	h.Debug
o.Error:	h.Variables
o.FS_Veneer: s.FS_Veneer
o.Init:	c.Init
o.Init:	C:h.kernel
o.Init:	h.Defs
o.Init:	h.Structs
o.Init:	h.Variables
o.Init:	h.Init
o.Init:	h.Resources
o.Init:	h.Error
o.Init:	h.Misc
o.Init:	h.FS_Veneer
o.Init:	h.Debug
o.Misc:	c.Misc
o.Misc:	C:h.kernel
o.Misc:	h.Defs
o.Misc:	h.Structs
o.Misc:	h.Variables
o.Misc:	h.Misc
o.Misc:	h.Debug
o.MiscOp:	c.MiscOp
o.MiscOp:	C:h.kernel
o.MiscOp:	h.Defs
o.MiscOp:	h.Structs
o.MiscOp:	h.Variables
o.MiscOp:	h.MiscOp
o.MiscOp:	h.Error
o.MiscOp:	h.Misc
o.MiscOp:	h.Debug
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
o.Services:	h.Misc
o.Services:	h.Structs
o.Services:	h.Variables
o.Services:	h.Services
o.Services:	h.Resources
o.Services:	h.Debug
o.StarCmd:	c.StarCmd
o.StarCmd:	C:h.kernel
o.StarCmd:	h.Defs
o.StarCmd:	h.Structs
o.StarCmd:	h.Variables
o.StarCmd:	h.StarCmd
o.StarCmd:	h.Error
o.StarCmd:	h.Misc
o.StarCmd:	h.Debug
o.Swi:	c.Swi
o.Swi:	C:h.kernel
o.Swi:	h.Defs
o.Swi:	h.Structs
o.Swi:	h.Variables
o.Swi:	h.Swi
o.Swi:	h.Error
o.Swi:	h.MiscOp
o.Swi:	h.Debug
o.Variables:	c.Variables
o.Variables:	C:h.kernel
o.Variables:	h.Defs
o.Variables:	h.Structs
