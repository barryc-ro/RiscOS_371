# Makefile for Edit
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name         Description
# ----       ----         -----------
# 25-Oct-94  AMcC   Updated for Black build
# 28-Oct-94  AMcC   added -zps1 flag to .c.oz rule (module version)
#

#
# Program specific options:
#
COMPONENT  = Edit
APP        = !Edit
MODULE     = rm.Edit
ROM_MODULE = aof.Edit
RDIR       = Resources
LDIR       = ${RDIR}.${LOCALE}

#
# Export Paths for Messages module
#
RESDIR = <resource$dir>.Resources.${COMPONENT}
RESAPP = <resource$dir>.Apps.${APP}

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
SQUEEZE = squeeze
WIPE    = -wipe

AFLAGS  = ${THROWBACK} -depend !Depend -nocache -stamp -quit
CFLAGS  = ${THROWBACK} -c -depend !Depend -fah ${INCLUDES} ${DFLAGS} -wp
CPFLAGS = ~cfr~v
WFLAGS  = ~c~v

#
# Libraries
#
ANSILIB   = CLib:o.ansilib
CLIB      = CLib:o.stubs
RLIB      = RISC_OSLib:o.risc_oslib
RSTUBS    = RISC_OSLib:o.rstubs
ROMSTUBS  = RISC_OSLib:o.romstubs
ROMCSTUBS = RISC_OSLib:o.romcstubs
ABSSYM    = RISC_OSLib:o.abssym
WRAPPER   = RISC_OSLib:s.ModuleWrap

INCLUDES   = -IC:

DFLAGS     = 

FILES =\
 ${RDIR}.!Boot\
 ${RDIR}.!Run\
 abs.!RunImage\
 ${RDIR}.Export\
 ${LDIR}.!Help\
 ${LDIR}.Messages\
 ${LDIR}.Templates

# Include these in the ROM module
RESFILES =\
 ${RDIR}.Export

OBJS  = o.edit o.editv o.message o.slist
OBJSZ = oz.edit oz.editv oz.message oz.slist
OBJSD = od.edit od.editv od.message od.slist

#
# Rule patterns
#
.SUFFIXES: .oz .od
.c.o:;      ${CC} ${CFLAGS} -ff -o $@ $<
.c.oz:;     ${CC} ${CFLAGS} -ff -zM -zps1 -o $@ $<
.c.od:;     ${CC} ${CFLAGS} -DTRACE=1 -g -o $@ $<
.s.o:;    ${AS} ${AFLAGS} $< $@

#
# Main rules:
#
all: ${FILES}
        @echo ${COMPONENT}: Application built (Disc)

rom: ${ROM_MODULE}
        @echo ${COMPONENT}: Module built (ROM)

install: ${FILES}
        ${CP} ${RDIR}.!Boot        ${INSTDIR}.!Boot     ${CPFLAGS}
        ${CP} ${LDIR}.!Help        ${INSTDIR}.!Help     ${CPFLAGS}
        ${CP} ${RDIR}.!Run         ${INSTDIR}.!Run      ${CPFLAGS}
        ${CP} abs.!RunImage        ${INSTDIR}.!RunImage ${CPFLAGS}
        ${CP} ${RDIR}.Export       ${INSTDIR}.Export    ${CPFLAGS}
        ${CP} ${LDIR}.Messages     ${INSTDIR}.Messages  ${CPFLAGS}
        ${CP} ${LDIR}.Templates    ${INSTDIR}.Templates ${CPFLAGS}
        Access ${INSTDIR}.!Boot      lr/r
        Access ${INSTDIR}.!Help      lr/r
        Access ${INSTDIR}.!Run       lr/r
        Access ${INSTDIR}.!RunImage  lr/r
        Access ${INSTDIR}.Export    lr/r
        Access ${INSTDIR}.Messages   lr/r
        Access ${INSTDIR}.Templates  lr/r
        @echo ${COMPONENT}: Application installed (Disc)

install_rom: ${ROM_MODULE}
        ${CP} ${ROM_MODULE} ${INSTDIR}.${COMPONENT} ${CPFLAGS}
        @echo ${COMPONENT}: Module installed (ROM)

resources:
        ${MKDIR} ${RESDIR}
        ${MKDIR} ${RESAPP}
        ${CP} ${RDIR}.!Boot     ${RESAPP}.!Boot ${CPFLAGS}
        ${CP} ${LDIR}.!Help     ${RESAPP}.!Help ${CPFLAGS}
        ${CP} ${RDIR}.ROM.!Run  ${RESAPP}.!Run  ${CPFLAGS}
        ${CP} ${LDIR}.Messages  ${RESDIR}.Messages ${CPFLAGS}
        ${CP} ${LDIR}.Templates ${RESDIR}.Templates ${CPFLAGS}
        @echo ${COMPONENT}: resource files copied to Messages module

clean:
        ${WIPE} o.* ${WFLAGS}
        ${WIPE} oz.* ${WFLAGS}
        ${WIPE} od.* ${WFLAGS}
        ${WIPE} map.* ${WFLAGS}
        ${WIPE} linked.* ${WFLAGS}
        ${RM} abs.!RunImage
        ${RM} ${ROM_MODULE}
        ${RM} ${MODULE}
        ${RM} s.ModuleWrap
        ${RM} s.AppName
        @echo ${COMPONENT}: cleaned

#
# Development rules:
#
mod: ${MODULE}
        @echo ${COMPONENT}: Module built (RAM)

#
# Static dependencies:
#
abs.!RunImage: ${OBJS} ${RLIB} ${CLIB}
        ${LD} -o $@ ${OBJS} ${RLIB} ${CLIB}

${MODULE}: oz.ModuleWrap ${OBJSZ} ${RLIB} ${CLIB}
        ${LD} -o $@ -module oz.ModuleWrap ${OBJSZ} ${RLIB} ${CLIB}

${ROM_MODULE}: oz.ModuleWrap ${OBJSZ} ${ROMSTUBS}
        ${LD} -o $@ -aof oz.ModuleWrap ${OBJSZ} ${ROMSTUBS}

# final link for ROM Image (using given base address)
rom_link:
        ${LD} -o linked.${COMPONENT} -bin -base ${ADDRESS} ${ROM_MODULE} ${ABSSYM} \
              -map > map.${COMPONENT}
        truncate map.${COMPONENT} linked.${COMPONENT}
        ${CP} linked.${COMPONENT} ${LINKDIR}.${COMPONENT} ${CPFLAGS}
        @echo ${COMPONENT}: rom_link complete

oz.ModuleWrap: s.ModuleWrap s.AppName ${RESFILES}
        ${AS} ${AFLAGS} s.ModuleWrap $@

s.ModuleWrap: ${WRAPPER}
        ${CP} ${WRAPPER} $@ ${CPFLAGS}

s.AppName: ${LDIR}.Messages
        awk -f awk.AppName ${LDIR}.Messages > $@

#---------------------------------------------------------------------------
# Debugging version:
#
debug.${APP}.!RunImage: ${OBJSD} ${RLIB} ${CLIB}
        ${MKDIR} debug
        ${MKDIR} debug.${APP}
        ${LD} -o $@ -debug ${OBJSD} ${RLIB} ${CLIB}

#---------------------------------------------------------------------------
# Dynamic dependencies:
o.edit:	c.edit
o.edit:	C:h.kernel
o.edit:	C:h.akbd
o.edit:	C:h.help
o.edit:	C:h.wimp
o.edit:	C:h.os
o.edit:	C:h.sprite
o.edit:	C:h.event
o.edit:	C:h.menu
o.edit:	C:h.dbox
o.edit:	C:h.flex
o.edit:	C:h.os
o.edit:	C:h.swis
o.edit:	C:h.wimp
o.edit:	C:h.sprite
o.edit:	C:h.wimpt
o.edit:	C:h.werr
o.edit:	C:h.win
o.edit:	C:h.menu
o.edit:	C:h.template
o.edit:	C:h.dbox
o.edit:	C:h.txt
o.edit:	C:h.EditIntern.txtar
o.edit:	C:h.txtscrap
o.edit:	C:h.EditIntern.txtoptmenu
o.edit:	C:h.typdat
o.edit:	C:h.txtedit
o.edit:	C:h.event
o.edit:	C:h.res
o.edit:	C:h.resspr
o.edit:	C:h.trace
o.edit:	C:h.dboxquery
o.edit:	h.editv
o.edit:	C:h.baricon
o.edit:	C:h.EditIntern.message
o.edit:	C:h.xferrecv
o.edit:	C:h.msgs
o.edit:	C:h.visdelay
o.edit:	C:h.pointer
o.edit:	C:h.editintern.txtfile
o.message:	c.message
o.message:	C:h.akbd
o.message:	C:h.dboxquery
o.message:	C:h.flex
o.message:	C:h.os
o.message:	C:h.kernel
o.message:	C:h.menu
o.message:	C:h.event
o.message:	C:h.wimp
o.message:	C:h.sprite
o.message:	C:h.txt
o.message:	C:h.txtscrap
o.message:	C:h.typdat
o.message:	C:h.txtedit
o.message:	C:h.EditIntern.txtoptmenu
o.message:	C:h.txtwin
o.message:	C:h.trace
o.message:	C:h.werr
o.message:	C:h.wimp
o.message:	C:h.wimpt
o.message:	C:h.win
o.message:	C:h.EditIntern.message
o.message:	h.slist
o.message:	C:h.msgs
o.message:	C:h.msgtrans
o.message:	C:h.swis
o.message:	C:h.help
o.message:	C:h.dbox
o.slist:	c.slist
o.editv:	c.editv
o.editv:	C:h.txt
o.editv:	C:h.dbox
o.editv:	C:h.help
o.editv:	C:h.wimp
o.editv:	C:h.os
o.editv:	C:h.kernel
o.editv:	C:h.sprite
o.editv:	C:h.event
o.editv:	C:h.menu
o.editv:	C:h.msgs
o.editv:	h.editv
oz.ModuleWrap: s.ModuleWrap
oz.ModuleWrap: s.AppName
oz.ModuleWrap: Hdr:ListOpts
oz.ModuleWrap: Hdr:Macros
oz.ModuleWrap: Hdr:System
oz.ModuleWrap: Hdr:SWIs
oz.ModuleWrap: Hdr:CPU.Generic26
oz.ModuleWrap: Hdr:IO.GenericIO
oz.ModuleWrap: Hdr:RISCOS
oz.ModuleWrap: Hdr:ModHand
oz.ModuleWrap: Hdr:EnvNumbers
oz.ModuleWrap: Hdr:Proc
oz.ModuleWrap: Hdr:FSNumbers
oz.ModuleWrap: Hdr:NewErrors
oz.ModuleWrap: Hdr:Services
oz.ModuleWrap: Hdr:ResourceFS
oz.ModuleWrap: Hdr:MsgTrans
oz.ModuleWrap: Hdr:Variables
oz.ModuleWrap: Hdr:UpCall
oz.ModuleWrap: s.ResFiles
oz.edit:	c.edit
oz.edit:	C:h.kernel
oz.edit:	C:h.akbd
oz.edit:	C:h.help
oz.edit:	C:h.wimp
oz.edit:	C:h.os
oz.edit:	C:h.sprite
oz.edit:	C:h.event
oz.edit:	C:h.menu
oz.edit:	C:h.dbox
oz.edit:	C:h.flex
oz.edit:	C:h.os
oz.edit:	C:h.swis
oz.edit:	C:h.wimp
oz.edit:	C:h.sprite
oz.edit:	C:h.wimpt
oz.edit:	C:h.werr
oz.edit:	C:h.win
oz.edit:	C:h.menu
oz.edit:	C:h.template
oz.edit:	C:h.dbox
oz.edit:	C:h.txt
oz.edit:	C:h.EditIntern.txtar
oz.edit:	C:h.txtscrap
oz.edit:	C:h.EditIntern.txtoptmenu
oz.edit:	C:h.typdat
oz.edit:	C:h.txtedit
oz.edit:	C:h.event
oz.edit:	C:h.res
oz.edit:	C:h.resspr
oz.edit:	C:h.trace
oz.edit:	C:h.dboxquery
oz.edit:	h.editv
oz.edit:	C:h.baricon
oz.edit:	C:h.EditIntern.message
oz.edit:	C:h.xferrecv
oz.edit:	C:h.msgs
oz.edit:	C:h.visdelay
oz.edit:	C:h.pointer
oz.edit:	C:h.editintern.txtfile
oz.editv:	c.editv
oz.editv:	C:h.txt
oz.editv:	C:h.dbox
oz.editv:	C:h.help
oz.editv:	C:h.wimp
oz.editv:	C:h.os
oz.editv:	C:h.kernel
oz.editv:	C:h.sprite
oz.editv:	C:h.event
oz.editv:	C:h.menu
oz.editv:	C:h.msgs
oz.editv:	h.editv
oz.message:	c.message
oz.message:	C:h.akbd
oz.message:	C:h.dboxquery
oz.message:	C:h.flex
oz.message:	C:h.os
oz.message:	C:h.kernel
oz.message:	C:h.menu
oz.message:	C:h.event
oz.message:	C:h.wimp
oz.message:	C:h.sprite
oz.message:	C:h.txt
oz.message:	C:h.txtscrap
oz.message:	C:h.typdat
oz.message:	C:h.txtedit
oz.message:	C:h.EditIntern.txtoptmenu
oz.message:	C:h.txtwin
oz.message:	C:h.trace
oz.message:	C:h.werr
oz.message:	C:h.wimp
oz.message:	C:h.wimpt
oz.message:	C:h.win
oz.message:	C:h.EditIntern.message
oz.message:	h.slist
oz.message:	C:h.msgs
oz.message:	C:h.msgtrans
oz.message:	C:h.swis
oz.message:	C:h.help
oz.message:	C:h.dbox
oz.slist:	c.slist
