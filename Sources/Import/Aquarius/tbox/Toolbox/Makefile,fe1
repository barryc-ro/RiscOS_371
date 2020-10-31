# Makefile for Toolbox
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name   Description
# ----       ----   -----------
# 06-Jan-94  AMcC   Created
#

#
# Component specific options:
#
COMPONENT  = Toolbox
ROM_MODULE = aof.${COMPONENT}

#
# Export Paths for Messages module
#
RESDIR = <resource$dir>.Resources2.${COMPONENT}

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

CPFLAGS = ~cfr~v
WFLAGS  = ~c~v

AFLAGS   = -depend !Depend -Stamp -quit -CloseExec
CFLAGS   = -c -depend !Depend ${INCLUDES} -zM -ffah -zps1 ${DFLAGS}
DFLAGS   = -DROM
INCLUDES = -Itbox:,C:

#
# Libraries
#
ANSILIB   = CLib:o.ansilib
CLIB      = CLIB:o.stubs
RLIB      = RISCOSLIB:o.risc_oslib
ROMCSTUBS = RISCOSLIB:o.romcstubs
ABSSYM    = RISC_OSLib:o.abssym
TBOXLIB   = tbox:tboxlib

OBJS =\
 o.Modhdr_NoD\
 o.base\
 o.callback\
 o.event\
 o.filters\
 o.filter_ven\
 o.globals\
 o.main\
 o.object\
 o.resf\
 o.task

#
# Rule patterns
#
.c.o:;    ${CC} ${CFLAGS} -o $@ $<
.cmhg.o:; ${CMHG} -O $@ $<
.s.o:;    ${AS} ${AFLAGS} -o $@ $<

#
# Main rules:
#
#
rom: ${ROM_MODULE}
        @echo ${COMPONENT}: Module built (ROM)

install_rom: ${ROM_MODULE}
        ${CP} ${ROM_MODULE} ${INSTDIR}.${COMPONENT} ${CPFLAGS}
        @echo ${COMPONENT}: Module installed (ROM)

resources: Messages
        ${MKDIR} ${RESDIR}
        ${CP} Messages ${RESDIR}.Messages ${CPFLAGS}
        @echo ${COMPONENT}: resource files copied to Messages module

clean:
        ${WIPE} o.* ${WFLAGS}
        ${WIPE} aof ${WFLAGS}
        ${WIPE} linked ${WFLAGS}
        ${WIPE} map ${WFLAGS}
        @echo ${COMPONENT}: cleaned

${ROM_MODULE}: ${OBJS} ${TBOXLIB} ${ROMCSTUBS}
        ${MKDIR} aof
        ${LD} -o $@ -aof ${OBJS} ${TBOXLIB} ${ROMCSTUBS}

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
o.base: s.base
o.callback: s.callback
o.event:	c.event
o.event:	C:h.kernel
o.event:	C:h.swis
o.event:	tbox:h.const
o.event:	tbox:h.macros
o.event:	tbox:h.services
o.event:	tbox:h.debug
o.event:	tbox:h.mem
o.event:	tbox:h.twimp
o.event:	tbox:objects.h.toolbox
o.event:	C:h.kernel
o.event:	tbox:h.messages
o.event:	C:h.kernel
o.event:	tbox:objects.h.toolbox
o.event:	h.globals
o.event:	h.task
o.event:	h.object
o.event:	tbox:objects.h.toolbox
o.event:	C:h.kernel
o.event:	h.resf
o.event:	tbox:objects.h.toolbox
o.event:	C:h.kernel
o.event:	h.filters
o.event:	tbox:objects.h.toolbox
o.event:	C:h.kernel
o.event:	C:h.kernel
o.event:	C:h.kernel
o.event:	h.task
o.event:	h.event
o.event:	tbox:objects.h.toolbox
o.event:	C:h.kernel
o.filters:	c.filters
o.filters:	C:h.kernel
o.filters:	C:h.swis
o.filters:	tbox:h.const
o.filters:	tbox:h.macros
o.filters:	tbox:h.services
o.filters:	tbox:h.debug
o.filters:	tbox:h.mem
o.filters:	tbox:h.twimp
o.filters:	tbox:objects.h.toolbox
o.filters:	C:h.kernel
o.filters:	tbox:h.messages
o.filters:	C:h.kernel
o.filters:	tbox:objects.h.toolbox
o.filters:	h.globals
o.filters:	h.task
o.filters:	h.object
o.filters:	tbox:objects.h.toolbox
o.filters:	C:h.kernel
o.filters:	h.resf
o.filters:	tbox:objects.h.toolbox
o.filters:	C:h.kernel
o.filters:	h.filters
o.filters:	tbox:objects.h.toolbox
o.filters:	C:h.kernel
o.filters:	C:h.kernel
o.filters:	C:h.kernel
o.filters:	h.task
o.filters:	h.object
o.filters:	h.event
o.filters:	tbox:objects.h.toolbox
o.filters:	C:h.kernel
o.filters:	h.filters
o.filter_ven: s.filter_ven
o.globals:	c.globals
o.globals:	tbox:h.const
o.globals:	tbox:h.macros
o.globals:	tbox:h.services
o.globals:	tbox:h.debug
o.globals:	tbox:h.mem
o.globals:	tbox:objects.h.toolbox
o.globals:	h.globals
o.globals:	h.task
o.globals:	h.object
o.globals:	tbox:objects.h.toolbox
o.globals:	C:h.kernel
o.globals:	tbox:h.twimp
o.globals:	C:h.kernel
o.globals:	h.resf
o.globals:	tbox:objects.h.toolbox
o.globals:	C:h.kernel
o.globals:	h.filters
o.globals:	tbox:objects.h.toolbox
o.globals:	C:h.kernel
o.globals:	C:h.kernel
o.globals:	C:h.kernel
o.globals:	C:h.kernel
o.main:	c.main
o.main:	C:h.kernel
o.main:	C:h.swis
o.main:	tbox:h.const
o.main:	tbox:h.macros
o.main:	tbox:h.services
o.main:	tbox:h.debug
o.main:	tbox:h.mem
o.main:	tbox:h.messages
o.main:	C:h.kernel
o.main:	tbox:objects.h.toolbox
o.main:	tbox:h.rmensure
o.main:	tbox:objects.h.toolbox
o.main:	h.globals
o.main:	h.task
o.main:	h.object
o.main:	tbox:objects.h.toolbox
o.main:	C:h.kernel
o.main:	tbox:h.twimp
o.main:	C:h.kernel
o.main:	h.resf
o.main:	tbox:objects.h.toolbox
o.main:	C:h.kernel
o.main:	h.filters
o.main:	tbox:objects.h.toolbox
o.main:	C:h.kernel
o.main:	C:h.kernel
o.main:	C:h.kernel
o.main:	tbox:h.services
o.main:	h.object
o.main:	h.task
o.main:	h.resf
o.main:	h.event
o.main:	tbox:objects.h.toolbox
o.main:	C:h.kernel
o.main:	h.filters
o.main:	h.callback
o.main:	h.main
o.main:	C:h.kernel
o.object:	c.object
o.object:	C:h.kernel
o.object:	C:h.swis
o.object:	tbox:h.const
o.object:	tbox:h.macros
o.object:	tbox:h.services
o.object:	tbox:h.debug
o.object:	tbox:h.mem
o.object:	tbox:h.string32
o.object:	tbox:h.messages
o.object:	C:h.kernel
o.object:	tbox:objects.h.toolbox
o.object:	tbox:objects.h.toolbox
o.object:	h.globals
o.object:	h.task
o.object:	h.object
o.object:	tbox:objects.h.toolbox
o.object:	C:h.kernel
o.object:	tbox:h.twimp
o.object:	C:h.kernel
o.object:	h.resf
o.object:	tbox:objects.h.toolbox
o.object:	C:h.kernel
o.object:	h.filters
o.object:	tbox:objects.h.toolbox
o.object:	C:h.kernel
o.object:	C:h.kernel
o.object:	C:h.kernel
o.object:	h.task
o.object:	h.resf
o.object:	h.event
o.object:	tbox:objects.h.toolbox
o.object:	C:h.kernel
o.object:	h.object
o.resf:	c.resf
o.resf:	C:h.swis
o.resf:	C:h.kernel
o.resf:	C:h.kernel
o.resf:	tbox:h.const
o.resf:	tbox:h.macros
o.resf:	tbox:h.services
o.resf:	tbox:h.debug
o.resf:	tbox:h.mem
o.resf:	tbox:h.messages
o.resf:	C:h.kernel
o.resf:	tbox:objects.h.toolbox
o.resf:	tbox:objects.h.toolbox
o.resf:	h.globals
o.resf:	h.task
o.resf:	h.object
o.resf:	tbox:objects.h.toolbox
o.resf:	C:h.kernel
o.resf:	tbox:h.twimp
o.resf:	C:h.kernel
o.resf:	h.resf
o.resf:	tbox:objects.h.toolbox
o.resf:	C:h.kernel
o.resf:	h.filters
o.resf:	tbox:objects.h.toolbox
o.resf:	C:h.kernel
o.resf:	C:h.kernel
o.resf:	C:h.kernel
o.resf:	h.resf
o.resf:	h.task
o.resf:	h.object
o.task:	c.task
o.task:	C:h.kernel
o.task:	C:h.swis
o.task:	tbox:h.const
o.task:	tbox:h.macros
o.task:	tbox:h.services
o.task:	tbox:h.debug
o.task:	tbox:h.mem
o.task:	tbox:h.twimp
o.task:	tbox:objects.h.toolbox
o.task:	C:h.kernel
o.task:	tbox:h.string32
o.task:	tbox:h.messages
o.task:	C:h.kernel
o.task:	tbox:objects.h.toolbox
o.task:	h.globals
o.task:	h.task
o.task:	h.object
o.task:	tbox:objects.h.toolbox
o.task:	C:h.kernel
o.task:	h.resf
o.task:	tbox:objects.h.toolbox
o.task:	C:h.kernel
o.task:	h.filters
o.task:	tbox:objects.h.toolbox
o.task:	C:h.kernel
o.task:	C:h.kernel
o.task:	C:h.kernel
o.task:	tbox:h.services
o.task:	h.resf
o.task:	h.filters
o.task:	h.object
o.task:	h.callback
o.task:	h.task
