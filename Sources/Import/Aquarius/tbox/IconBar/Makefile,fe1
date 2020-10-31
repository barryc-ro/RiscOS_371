# Makefile for IconBar
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
COMPONENT  = IconBar
ROM_MODULE = aof.${COMPONENT}

#
# Export Paths for Messages module
#
RESDIR = <resource$dir>.Resources2.${COMPONENT}

#
# Generic options:
#
MKDIR   = cdir
CC      = cc
CMHG    = cmhg
CP      = copy
LD      = link
RM      = remove
WIPE    = -wipe

CPFLAGS = ~cfr~v
WFLAGS  = ~c~v

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
 o.copy\
 o.create\
 o.delete\
 o.events\
 o.getstate\
 o.globals\
 o.hide\
 o.main\
 o.miscop\
 o.show\
 o.task

#
# Rule patterns
#
.c.o:;    ${CC} ${CFLAGS} -o $@ $<
.cmhg.o:; ${CMHG} -O $@ $<

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
o.copy:	c.copy
o.copy:	C:h.kernel
o.copy:	C:h.swis
o.copy:	tbox:h.const
o.copy:	tbox:h.macros
o.copy:	tbox:h.services
o.copy:	tbox:h.debug
o.copy:	tbox:h.mem
o.copy:	tbox:h.messages
o.copy:	C:h.kernel
o.copy:	tbox:objects.h.toolbox
o.copy:	tbox:objects.h.toolbox
o.copy:	tbox:objects.h.iconbar
o.copy:	h.object
o.copy:	tbox:h.twimp
o.copy:	C:h.kernel
o.copy:	h.task
o.copy:	h.copy
o.copy:	C:h.kernel
o.create:	c.create
o.create:	C:h.kernel
o.create:	C:h.swis
o.create:	tbox:h.const
o.create:	tbox:h.macros
o.create:	tbox:h.services
o.create:	tbox:h.debug
o.create:	tbox:h.mem
o.create:	tbox:h.style
o.create:	tbox:h.twimp
o.create:	tbox:objects.h.toolbox
o.create:	C:h.kernel
o.create:	tbox:h.messages
o.create:	C:h.kernel
o.create:	tbox:h.string32
o.create:	tbox:objects.h.toolbox
o.create:	tbox:objects.h.iconbar
o.create:	h.object
o.create:	h.task
o.create:	h.create
o.create:	C:h.kernel
o.delete:	c.delete
o.delete:	C:h.kernel
o.delete:	C:h.swis
o.delete:	tbox:h.const
o.delete:	tbox:h.macros
o.delete:	tbox:h.services
o.delete:	tbox:h.debug
o.delete:	tbox:h.mem
o.delete:	tbox:h.messages
o.delete:	C:h.kernel
o.delete:	tbox:objects.h.toolbox
o.delete:	tbox:objects.h.toolbox
o.delete:	tbox:objects.h.iconbar
o.delete:	h.object
o.delete:	tbox:h.twimp
o.delete:	C:h.kernel
o.delete:	h.task
o.delete:	h.delete
o.delete:	C:h.kernel
o.events:	c.events
o.events:	C:h.kernel
o.events:	C:h.swis
o.events:	tbox:h.const
o.events:	tbox:h.macros
o.events:	tbox:h.services
o.events:	tbox:h.debug
o.events:	tbox:h.mem
o.events:	tbox:h.twimp
o.events:	tbox:objects.h.toolbox
o.events:	C:h.kernel
o.events:	tbox:h.style
o.events:	tbox:h.messages
o.events:	C:h.kernel
o.events:	tbox:h.string32
o.events:	tbox:objects.h.toolbox
o.events:	tbox:objects.h.iconbar
o.events:	tbox:objects.h.menu
o.events:	h.task
o.events:	h.object
o.events:	h.globals
o.events:	h.object
o.events:	h.events
o.events:	C:h.kernel
o.getstate:	c.getstate
o.getstate:	C:h.kernel
o.getstate:	C:h.swis
o.getstate:	tbox:h.const
o.getstate:	tbox:h.macros
o.getstate:	tbox:h.services
o.getstate:	tbox:h.debug
o.getstate:	tbox:h.mem
o.getstate:	tbox:h.messages
o.getstate:	C:h.kernel
o.getstate:	tbox:objects.h.toolbox
o.getstate:	tbox:objects.h.toolbox
o.getstate:	tbox:objects.h.iconbar
o.getstate:	h.object
o.getstate:	tbox:h.twimp
o.getstate:	C:h.kernel
o.getstate:	h.task
o.getstate:	h.getstate
o.getstate:	C:h.kernel
o.globals:	c.globals
o.globals:	tbox:h.const
o.globals:	tbox:h.macros
o.globals:	tbox:h.services
o.globals:	tbox:h.debug
o.globals:	tbox:h.mem
o.globals:	tbox:h.messages
o.globals:	C:h.kernel
o.globals:	tbox:objects.h.toolbox
o.globals:	tbox:h.twimp
o.globals:	C:h.kernel
o.globals:	tbox:objects.h.toolbox
o.globals:	tbox:objects.h.iconbar
o.globals:	h.globals
o.hide:	c.hide
o.hide:	C:h.kernel
o.hide:	C:h.swis
o.hide:	tbox:h.const
o.hide:	tbox:h.macros
o.hide:	tbox:h.services
o.hide:	tbox:h.debug
o.hide:	tbox:h.mem
o.hide:	tbox:h.messages
o.hide:	C:h.kernel
o.hide:	tbox:objects.h.toolbox
o.hide:	tbox:objects.h.toolbox
o.hide:	tbox:objects.h.iconbar
o.hide:	h.object
o.hide:	tbox:h.twimp
o.hide:	C:h.kernel
o.hide:	h.task
o.hide:	h.globals
o.hide:	h.hide
o.hide:	C:h.kernel
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
o.main:	tbox:h.string32
o.main:	tbox:objects.h.iconbar
o.main:	h.create
o.main:	C:h.kernel
o.main:	h.task
o.main:	h.object
o.main:	tbox:h.twimp
o.main:	C:h.kernel
o.main:	h.delete
o.main:	C:h.kernel
o.main:	h.copy
o.main:	C:h.kernel
o.main:	h.show
o.main:	C:h.kernel
o.main:	h.hide
o.main:	C:h.kernel
o.main:	h.getstate
o.main:	C:h.kernel
o.main:	h.miscop
o.main:	C:h.kernel
o.main:	h.events
o.main:	C:h.kernel
o.main:	h.globals
o.main:	h.task
o.main:	h.main
o.main:	C:h.kernel
o.miscop:	c.miscop
o.miscop:	C:h.kernel
o.miscop:	C:h.swis
o.miscop:	tbox:h.const
o.miscop:	tbox:h.macros
o.miscop:	tbox:h.services
o.miscop:	tbox:h.debug
o.miscop:	tbox:h.mem
o.miscop:	tbox:h.twimp
o.miscop:	tbox:objects.h.toolbox
o.miscop:	C:h.kernel
o.miscop:	tbox:h.messages
o.miscop:	C:h.kernel
o.miscop:	tbox:h.string32
o.miscop:	tbox:objects.h.toolbox
o.miscop:	tbox:objects.h.iconbar
o.miscop:	h.object
o.miscop:	h.task
o.miscop:	h.miscop
o.miscop:	C:h.kernel
o.show:	c.show
o.show:	C:h.kernel
o.show:	C:h.swis
o.show:	tbox:h.const
o.show:	tbox:h.macros
o.show:	tbox:h.services
o.show:	tbox:h.debug
o.show:	tbox:h.mem
o.show:	tbox:h.twimp
o.show:	tbox:objects.h.toolbox
o.show:	C:h.kernel
o.show:	tbox:h.messages
o.show:	C:h.kernel
o.show:	tbox:objects.h.toolbox
o.show:	tbox:objects.h.iconbar
o.show:	h.object
o.show:	h.task
o.show:	h.globals
o.show:	h.show
o.show:	C:h.kernel
o.task:	c.task
o.task:	C:h.kernel
o.task:	C:h.swis
o.task:	tbox:h.const
o.task:	tbox:h.macros
o.task:	tbox:h.services
o.task:	tbox:h.debug
o.task:	tbox:h.mem
o.task:	tbox:h.messages
o.task:	C:h.kernel
o.task:	tbox:objects.h.toolbox
o.task:	tbox:objects.h.toolbox
o.task:	tbox:objects.h.iconbar
o.task:	h.object
o.task:	tbox:h.twimp
o.task:	C:h.kernel
o.task:	h.task
