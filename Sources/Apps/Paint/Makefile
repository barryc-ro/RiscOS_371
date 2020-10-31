# Makefile for Paint
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name   Description
# ----       ----   -----------
# 25-Oct-94  AMcC   Updated for Black build
# 28-Oct-94  AMcC   added -zps1 flag to .c.oz rule (module version)
#

#
# Program specific options:
#
COMPONENT  = Paint
APP        = !Paint
MODULE     = rm.!Paint
ROM_MODULE = aof.Paint
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
CFLAGS  = ${THROWBACK} -c -depend !Depend -fah ${INCLUDES} -wp
CPFLAGS = ~cfr~v
SQFLAGS = 
WFLAGS  = ~c~v

#
# Libraries
#
ANSILIB   = CLib:o.ansilib
CLIB      = CLIB:o.stubs
RLIB      = RISC_OSLib:o.risc_oslib
ROMSTUBS  = RISC_OSLib:o.romstubs
ABSSYM    = RISC_OSLib:o.abssym
WRAPPER   = RISC_OSLib:s.ModuleWrap

#
# Include files
#
INCLUDES = -IC:

FILES = \
 ${RDIR}.!Boot\
 ${LDIR}.!Help\
 ${LDIR}.!Run\
 ${LDIR}.Messages\
 ${LDIR}.Sprites\
 ${LDIR}.Templates\
 abs.!RunImage

FILESD = \
 ${RDIR}.!Boot\
 ${LDIR}.!Help\
 ${LDIR}.!Run\
 ${LDIR}.Messages\
 ${LDIR}.Sprites\
 ${LDIR}.Templates\
 abs.!RunImageD

# Include these in the ROM module
RESFILES =

DFILES = \
 debug.${APP}.!Boot\
 debug.${APP}.!Help\
 debug.${APP}.!Run\
 debug.${APP}.!RunImage\
 debug.${APP}.Messages\
 debug.${APP}.Sprites\
 debug.${APP}.Templates

OBJS      = o.colours o.main o.menus o.psprite o.sprwindow o.tools o.toolwindow \
            o.jpeg o.writepixel
OBJSZ     = oz.colours oz.main oz.menus oz.psprite oz.sprwindow\
            oz.tools oz.toolwindow o.jpeg o.writepixel
OBJSD     = od.colours od.ftrace od.guard od.main od.menus\
            od.psprite od.sprwindow od.tools od.toolwindow o.jpeg o.m  o.writepixel
ASMS      = s.colours s.main s.menus s.psprite s.sprwindow s.tools s.toolwindow
INCS      = i.colours i.main i.menus i.psprite i.sprwindow i.tools i.toolwindow

#
# Rule patterns
#
.SUFFIXES: .oz .od .i .asm
.c.o:;      ${CC} ${CFLAGS} -ff -o $@ $<
.c.oz:;     ${CC} ${CFLAGS} -ff -zM -zps1 -o $@ $<
.c.od:;     ${CC} ${CFLAGS} -DTRACE=1 -o $@ $<
.asm.o:;    ${AS} ${AFLAGS} $< $@
.c.i:;      ${CC} -E ${CFLAGS} $< > $@
.c.s:;      ${CC} ${CFLAGS} -s $<

#
# Main rules:
#
# Application
#
all: ${FILES}
        @echo ${COMPONENT}: Application built (Disc)

rom: ${ROM_MODULE}
        @echo ${COMPONENT}: Module built (ROM)

install: ${FILES}
        ${CP} ${RDIR}.!Boot      ${INSTDIR}.!Boot      ${CPFLAGS}
        ${CP} ${LDIR}.!Help      ${INSTDIR}.!Help      ${CPFLAGS}
        ${CP} ${LDIR}.!Run       ${INSTDIR}.!Run       ${CPFLAGS}
        ${CP} abs.!RunImage      ${INSTDIR}.!RunImage  ${CPFLAGS}
        ${CP} ${LDIR}.Messages   ${INSTDIR}.Messages   ${CPFLAGS}
        ${CP} ${LDIR}.Sprites    ${INSTDIR}.Sprites    ${CPFLAGS}
        ${CP} ${LDIR}.Templates  ${INSTDIR}.Templates  ${CPFLAGS}
        Access ${INSTDIR}.!Boot      lr/r
        Access ${INSTDIR}.!Help      lr/r
        Access ${INSTDIR}.!Run       lr/r
        Access ${INSTDIR}.!RunImage  lr/r
        Access ${INSTDIR}.Messages   lr/r
        Access ${INSTDIR}.Sprites    lr/r
        Access ${INSTDIR}.Templates  lr/r
        @echo ${COMPONENT}: Application installed (Disc)

installd: ${FILESD}
        ${CP} ${RDIR}.!Boot      ${INSTDIR}.!Boot      ${CPFLAGS}
        ${CP} ${LDIR}.!Help      ${INSTDIR}.!Help      ${CPFLAGS}
        ${CP} ${LDIR}.!Run       ${INSTDIR}.!Run       ${CPFLAGS}
        ${CP} abs.!RunImageD     ${INSTDIR}.!RunImage  ${CPFLAGS}
        ${CP} ${LDIR}.Messages   ${INSTDIR}.Messages   ${CPFLAGS}
        ${CP} ${LDIR}.Sprites    ${INSTDIR}.Sprites    ${CPFLAGS}
        ${CP} ${LDIR}.Templates  ${INSTDIR}.Templates  ${CPFLAGS}
        Access ${INSTDIR}.!Boot      lr/r
        Access ${INSTDIR}.!Help      lr/r
        Access ${INSTDIR}.!Run       lr/r
        Access ${INSTDIR}.!RunImage  lr/r
        Access ${INSTDIR}.Messages   lr/r
        Access ${INSTDIR}.Sprites    lr/r
        Access ${INSTDIR}.Templates  lr/r
        @echo ${COMPONENT}: Debug application installed (Disc)

install_rom: ${ROM_MODULE}
        ${CP} ${ROM_MODULE} ${INSTDIR}.${COMPONENT} ${CPFLAGS}
        @echo ${COMPONENT}: Module installed (ROM)

resources:
        ${MKDIR} ${RESDIR}
        ${MKDIR} ${RESAPP}
        ${CP} ${RDIR}.!Boot     ${RESAPP}.!Boot  ${CPFLAGS}
        ${CP} ${LDIR}.!Help     ${RESAPP}.!Help  ${CPFLAGS}
        ${CP} ${RDIR}.ROM.!Run  ${RESAPP}.!Run   ${CPFLAGS}
        |
        ${CP} ${LDIR}.Messages  ${RESDIR}.Messages  ${CPFLAGS}
        ${CP} ${LDIR}.Sprites   ${RESDIR}.Sprites   ${CPFLAGS}
        ${CP} ${LDIR}.Templates ${RESDIR}.Templates ${CPFLAGS}
        @echo ${COMPONENT}: resource files copied to Messages module

clean:
        ${WIPE} o.* ${WFLAGS}
        ${WIPE} oz.* ${WFLAGS}
        ${WIPE} od.* ${WFLAGS}
        ${WIPE} s.* ${WFLAGS}
        ${WIPE} linked.* ${WFLAGS}
        ${WIPE} map.* ${WFLAGS}
        ${RM} abs.!RunImage
        ${RM} abs.!RunImageD
        ${RM} ${ROM_MODULE}
        ${RM} ${MODULE}
        @echo ${COMPONENT}: cleaned

#
# Development rules:
# 
app: ${FILES}
        @echo Made application ${APP}

appd: ${DFILES}
        @echo Made debug.${APP}

mod: ${MODULE}
        @echo ${COMPONENT}: Module built (RAM)

asms: ${ASMS}

incs: ${INCS}

clean_all:
        Access ${INSTDIR}.!Boot      rw/rw
        Access ${INSTDIR}.!Help      rw/rw
        Access ${INSTDIR}.!Run       rw/rw
        Access ${INSTDIR}.!RunImage  rw/rw
        Access ${INSTDIR}.Messages   rw/rw
        Access ${INSTDIR}.Sprites    rw/rw
        Access ${INSTDIR}.Templates  rw/rw
        Destroy ${OBJS} ${OBJSZ} ${OBJSD} o.ModuleWrap \
        ${APP}.!RunImage \
        debug.${APP}.!RunImage \
        ${ROM_MODULE} ${MODULE} \
        ${ASMS} s.AppName s.ModuleWrap s.ResFiles \
        ${DFILES} ${INSTDIR}.!Boot ${INSTDIR}.!Help ${INSTDIR}.!Run \
        ${INSTDIR}.!RunImage ${INSTDIR}.Messages ${INSTDIR}.Sprites \
        ${INSTDIR}.Templates

#
# Static dependencies:
#
abs.!RunImage: ${OBJS} ${RLIB} ${CLIB}
        ${LD} -o $@ ${OBJS} ${RLIB} ${CLIB}
        ${SQUEEZE} ${SQFLAGS} $@

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

oz.ModuleWrap: s.ModuleWrap ${RESFILES}
        ${AS} ${AFLAGS} s.ModuleWrap $@

s.ModuleWrap: ${WRAPPER}
        ${CP} ${WRAPPER} $@ ${CPFLAGS}

s.AppName: ${LDIR}.Messages
        awk -f awk.AppName ${LDIR}.Messages > $@

s.ResFiles: asm.ResFiles
        ${CP} asm.ResFiles $@ ${CPFLAGS}

#---------------------------------------------------------------------------
# debugging version:
#
abs.!RunImageD: ${OBJSD} ${RLIB} ${CLIB}
        ${LD} -o $@ ${OBJSD} ${RLIB} ${CLIB}
        SetType $@ Absolute

debug.${APP}.!Boot: ${RDIR}.!Boot
        ${CP} ${RDIR}.!Boot $@ ${CPFLAGS}

debug.${APP}.!Help: ${LDIR}.!Help
        ${CP} ${LDIR}.!Help $@ ${CPFLAGS}

debug.${APP}.!Run: ${LDIR}.!Run
        ${CP} ${LDIR}.!Run $@ ${CPFLAGS}

debug.${APP}.Messages: ${LDIR}.Messages
        ${CP} ${LDIR}.Messages $@ ${CPFLAGS}

debug.${APP}.Sprites: ${LDIR}.Sprites
        ${CP} ${LDIR}.Sprites $@ ${CPFLAGS}

debug.${APP}.Templates: ${LDIR}.Templates
        ${CP} ${LDIR}.Templates $@ ${CPFLAGS}

#---------------------------------------------------------------------------
# Dynamic dependencies:
o.sprwindow:	c.sprwindow
o.sprwindow:	C:h.swis
o.sprwindow:	C:h.kernel
o.sprwindow:	C:h.akbd
o.sprwindow:	C:h.bbc
o.sprwindow:	C:h.os
o.sprwindow:	C:h.help
o.sprwindow:	C:h.wimp
o.sprwindow:	C:h.sprite
o.sprwindow:	C:h.event
o.sprwindow:	C:h.menu
o.sprwindow:	C:h.dbox
o.sprwindow:	C:h.xferrecv
o.sprwindow:	C:h.werr
o.sprwindow:	C:h.wimpt
o.sprwindow:	h.ftrace
o.sprwindow:	h.m
o.sprwindow:	h.ftrace
o.sprwindow:	h.main
o.sprwindow:	C:h.wimp
o.sprwindow:	C:h.sprite
o.sprwindow:	C:h.win
o.sprwindow:	C:h.msgs
o.sprwindow:	C:h.colourpick
o.sprwindow:	C:h.coords
o.sprwindow:	h.ftrace
o.sprwindow:	h.fixes
o.sprwindow:	h.menus
o.sprwindow:	C:h.menu
o.sprwindow:	C:h.print
o.sprwindow:	h.psprite
o.sprwindow:	h.sprwindow
o.sprwindow:	h.toolwindow
o.sprwindow:	h.tools
o.sprwindow:	h.colours
o.toolwindow:	c.toolwindow
o.toolwindow:	C:h.wimpt
o.toolwindow:	C:h.wimp
o.toolwindow:	C:h.os
o.toolwindow:	C:h.kernel
o.toolwindow:	C:h.sprite
o.toolwindow:	C:h.wimp
o.toolwindow:	C:h.template
o.toolwindow:	h.main
o.toolwindow:	C:h.wimp
o.toolwindow:	C:h.sprite
o.toolwindow:	C:h.win
o.toolwindow:	C:h.msgs
o.toolwindow:	C:h.colourpick
o.toolwindow:	C:h.coords
o.toolwindow:	h.ftrace
o.toolwindow:	h.fixes
o.toolwindow:	h.menus
o.toolwindow:	C:h.menu
o.toolwindow:	C:h.print
o.toolwindow:	h.psprite
o.toolwindow:	h.sprwindow
o.toolwindow:	h.toolwindow
o.toolwindow:	h.tools
o.toolwindow:	h.ftrace
o.toolwindow:	h.guard
od.ftrace:	c.ftrace
od.ftrace:	C:h.swis
od.ftrace:	C:h.kernel
od.ftrace:	h.ftrace
od.ftrace:	C:h.bbc
od.ftrace:	C:h.os
od.ftrace:	C:h.font
od.ftrace:	C:h.drawmod
od.ftrace:	C:h.wimp
od.ftrace:	C:h.sprite
od.ftrace:	C:h.os
od.ftrace:	C:h.werr
od.ftrace:	C:h.wimp
od.ftrace:	C:h.wimpt
od.guard:	c.guard
od.guard:	h.ftrace
od.guard:	h.guard
od.sprwindow:	c.sprwindow
od.sprwindow:	C:h.swis
od.sprwindow:	C:h.kernel
od.sprwindow:	C:h.akbd
od.sprwindow:	C:h.bbc
od.sprwindow:	C:h.os
od.sprwindow:	C:h.help
od.sprwindow:	C:h.wimp
od.sprwindow:	C:h.sprite
od.sprwindow:	C:h.event
od.sprwindow:	C:h.menu
od.sprwindow:	C:h.dbox
od.sprwindow:	C:h.xferrecv
od.sprwindow:	C:h.werr
od.sprwindow:	C:h.wimpt
od.sprwindow:	h.ftrace
od.sprwindow:	h.m
od.sprwindow:	h.ftrace
od.sprwindow:	h.main
od.sprwindow:	C:h.wimp
od.sprwindow:	C:h.sprite
od.sprwindow:	C:h.win
od.sprwindow:	C:h.msgs
od.sprwindow:	C:h.colourpick
od.sprwindow:	C:h.coords
od.sprwindow:	h.ftrace
od.sprwindow:	h.fixes
od.sprwindow:	h.menus
od.sprwindow:	C:h.menu
od.sprwindow:	C:h.print
od.sprwindow:	h.psprite
od.sprwindow:	h.sprwindow
od.sprwindow:	h.toolwindow
od.sprwindow:	h.tools
od.sprwindow:	h.colours
od.toolwindow:	c.toolwindow
od.toolwindow:	C:h.wimpt
od.toolwindow:	C:h.wimp
od.toolwindow:	C:h.os
od.toolwindow:	C:h.kernel
od.toolwindow:	C:h.sprite
od.toolwindow:	C:h.wimp
od.toolwindow:	C:h.template
od.toolwindow:	h.main
od.toolwindow:	C:h.wimp
od.toolwindow:	C:h.sprite
od.toolwindow:	C:h.win
od.toolwindow:	C:h.msgs
od.toolwindow:	C:h.colourpick
od.toolwindow:	C:h.coords
od.toolwindow:	h.ftrace
od.toolwindow:	h.fixes
od.toolwindow:	h.menus
od.toolwindow:	C:h.menu
od.toolwindow:	C:h.print
od.toolwindow:	h.psprite
od.toolwindow:	h.sprwindow
od.toolwindow:	h.toolwindow
od.toolwindow:	h.tools
od.toolwindow:	h.ftrace
od.toolwindow:	h.guard
o.m:	c.m
o.m:	C:h.os
o.m:	C:h.kernel
o.m:	C:h.wimp
o.m:	C:h.sprite
o.m:	h.m
o.m:	h.ftrace
o.m:	h.ftrace
o.main:	c.main
o.main:	C:h.kernel
o.main:	C:h.swis
o.main:	C:h.pointer
o.main:	C:h.sprite
o.main:	C:h.os
o.main:	C:h.wimp
o.main:	C:h.akbd
o.main:	C:h.alarm
o.main:	C:h.baricon
o.main:	C:h.bbc
o.main:	C:h.colourpick
o.main:	C:h.coords
o.main:	C:h.dboxquery
o.main:	C:h.heap
o.main:	C:h.help
o.main:	C:h.event
o.main:	C:h.menu
o.main:	C:h.dbox
o.main:	C:h.flex
o.main:	C:h.msgs
o.main:	C:h.msgtrans
o.main:	C:h.res
o.main:	C:h.resspr
o.main:	C:h.template
o.main:	C:h.visdelay
o.main:	C:h.werr
o.main:	C:h.wimp
o.main:	C:h.wimpt
o.main:	C:h.xferrecv
o.main:	h.ftrace
o.main:	h.m
o.main:	h.ftrace
o.main:	h.main
o.main:	C:h.wimp
o.main:	C:h.sprite
o.main:	C:h.win
o.main:	C:h.msgs
o.main:	C:h.colourpick
o.main:	h.ftrace
o.main:	h.fixes
o.main:	h.menus
o.main:	C:h.menu
o.main:	C:h.print
o.main:	h.MenuD
o.main:	h.psprite
o.main:	h.sprwindow
o.main:	h.toolwindow
o.main:	h.tools
o.main:	h.colours
o.main:	h.jpeg
o.main:	C:h.drawmod
o.menus:	c.menus
o.menus:	C:h.swis
o.menus:	C:h.kernel
o.menus:	C:h.bbc
o.menus:	C:h.os
o.menus:	C:h.colourmenu
o.menus:	C:h.menu
o.menus:	C:h.colourtran
o.menus:	C:h.wimp
o.menus:	C:h.sprite
o.menus:	C:h.font
o.menus:	C:h.drawmod
o.menus:	C:h.dboxquery
o.menus:	C:h.dboxtcol
o.menus:	C:h.flex
o.menus:	C:h.help
o.menus:	C:h.event
o.menus:	C:h.dbox
o.menus:	C:h.magnify
o.menus:	C:h.msgtrans
o.menus:	C:h.saveas
o.menus:	C:h.xfersend
o.menus:	C:h.visdelay
o.menus:	C:h.werr
o.menus:	C:h.wimpt
o.menus:	C:h.xfersend
o.menus:	h.m
o.menus:	h.ftrace
o.menus:	h.ftrace
o.menus:	h.main
o.menus:	C:h.wimp
o.menus:	C:h.sprite
o.menus:	C:h.win
o.menus:	C:h.msgs
o.menus:	C:h.colourpick
o.menus:	C:h.coords
o.menus:	h.ftrace
o.menus:	h.fixes
o.menus:	h.psprite
o.menus:	h.menus
o.menus:	C:h.menu
o.menus:	C:h.print
o.menus:	h.sprwindow
o.menus:	h.toolwindow
o.menus:	h.tools
o.menus:	h.colours
o.menus:	h.MenuD
o.menus:	C:h.trace
od.main:	c.main
od.main:	C:h.kernel
od.main:	C:h.swis
od.main:	C:h.pointer
od.main:	C:h.sprite
od.main:	C:h.os
od.main:	C:h.wimp
od.main:	C:h.akbd
od.main:	C:h.alarm
od.main:	C:h.baricon
od.main:	C:h.bbc
od.main:	C:h.colourpick
od.main:	C:h.coords
od.main:	C:h.dboxquery
od.main:	C:h.heap
od.main:	C:h.help
od.main:	C:h.event
od.main:	C:h.menu
od.main:	C:h.dbox
od.main:	C:h.flex
od.main:	C:h.msgs
od.main:	C:h.msgtrans
od.main:	C:h.res
od.main:	C:h.resspr
od.main:	C:h.template
od.main:	C:h.visdelay
od.main:	C:h.werr
od.main:	C:h.wimp
od.main:	C:h.wimpt
od.main:	C:h.xferrecv
od.main:	h.ftrace
od.main:	h.m
od.main:	h.ftrace
od.main:	h.main
od.main:	C:h.wimp
od.main:	C:h.sprite
od.main:	C:h.win
od.main:	C:h.msgs
od.main:	C:h.colourpick
od.main:	h.ftrace
od.main:	h.fixes
od.main:	h.menus
od.main:	C:h.menu
od.main:	C:h.print
od.main:	h.MenuD
od.main:	h.psprite
od.main:	h.sprwindow
od.main:	h.toolwindow
od.main:	h.tools
od.main:	h.colours
od.main:	h.jpeg
od.main:	C:h.drawmod
od.menus:	c.menus
od.menus:	C:h.swis
od.menus:	C:h.kernel
od.menus:	C:h.bbc
od.menus:	C:h.os
od.menus:	C:h.colourmenu
od.menus:	C:h.menu
od.menus:	C:h.colourtran
od.menus:	C:h.wimp
od.menus:	C:h.sprite
od.menus:	C:h.font
od.menus:	C:h.drawmod
od.menus:	C:h.dboxquery
od.menus:	C:h.dboxtcol
od.menus:	C:h.flex
od.menus:	C:h.help
od.menus:	C:h.event
od.menus:	C:h.dbox
od.menus:	C:h.magnify
od.menus:	C:h.msgtrans
od.menus:	C:h.saveas
od.menus:	C:h.xfersend
od.menus:	C:h.visdelay
od.menus:	C:h.werr
od.menus:	C:h.wimpt
od.menus:	C:h.xfersend
od.menus:	h.m
od.menus:	h.ftrace
od.menus:	h.ftrace
od.menus:	h.main
od.menus:	C:h.wimp
od.menus:	C:h.sprite
od.menus:	C:h.win
od.menus:	C:h.msgs
od.menus:	C:h.colourpick
od.menus:	C:h.coords
od.menus:	h.ftrace
od.menus:	h.fixes
od.menus:	h.psprite
od.menus:	h.menus
od.menus:	C:h.menu
od.menus:	C:h.print
od.menus:	h.sprwindow
od.menus:	h.toolwindow
od.menus:	h.tools
od.menus:	h.colours
od.menus:	h.MenuD
od.menus:	C:h.trace
o.colours:	c.colours
o.colours:	C:h.swis
o.colours:	C:h.kernel
o.colours:	C:h.bbc
o.colours:	C:h.os
o.colours:	C:h.wimpt
o.colours:	C:h.wimp
o.colours:	C:h.sprite
o.colours:	h.ftrace
o.colours:	h.m
o.colours:	h.ftrace
o.colours:	h.main
o.colours:	C:h.wimp
o.colours:	C:h.sprite
o.colours:	C:h.win
o.colours:	C:h.msgs
o.colours:	C:h.colourpick
o.colours:	C:h.coords
o.colours:	h.ftrace
o.colours:	h.fixes
o.colours:	h.menus
o.colours:	C:h.menu
o.colours:	C:h.print
o.colours:	h.psprite
o.colours:	h.sprwindow
o.colours:	h.toolwindow
o.colours:	h.colours
o.psprite:	c.psprite
o.psprite:	C:h.swis
o.psprite:	C:h.kernel
o.psprite:	C:h.bbc
o.psprite:	C:h.os
o.psprite:	C:h.colourtran
o.psprite:	C:h.wimp
o.psprite:	C:h.sprite
o.psprite:	C:h.font
o.psprite:	C:h.drawmod
o.psprite:	C:h.flex
o.psprite:	C:h.help
o.psprite:	C:h.event
o.psprite:	C:h.menu
o.psprite:	C:h.dbox
o.psprite:	C:h.resspr
o.psprite:	C:h.visdelay
o.psprite:	C:h.werr
o.psprite:	C:h.wimpt
o.psprite:	h.ftrace
o.psprite:	h.m
o.psprite:	h.ftrace
o.psprite:	h.main
o.psprite:	C:h.wimp
o.psprite:	C:h.sprite
o.psprite:	C:h.win
o.psprite:	C:h.msgs
o.psprite:	C:h.colourpick
o.psprite:	C:h.coords
o.psprite:	h.ftrace
o.psprite:	h.fixes
o.psprite:	h.sprwindow
o.psprite:	h.psprite
o.psprite:	h.toolwindow
o.psprite:	h.tools
o.psprite:	h.colours
o.psprite:	h.menus
o.psprite:	C:h.menu
o.psprite:	C:h.print
o.psprite:	h.menud
od.colours:	c.colours
od.colours:	C:h.swis
od.colours:	C:h.kernel
od.colours:	C:h.bbc
od.colours:	C:h.os
od.colours:	C:h.wimpt
od.colours:	C:h.wimp
od.colours:	C:h.sprite
od.colours:	h.ftrace
od.colours:	h.m
od.colours:	h.ftrace
od.colours:	h.main
od.colours:	C:h.wimp
od.colours:	C:h.sprite
od.colours:	C:h.win
od.colours:	C:h.msgs
od.colours:	C:h.colourpick
od.colours:	C:h.coords
od.colours:	h.ftrace
od.colours:	h.fixes
od.colours:	h.menus
od.colours:	C:h.menu
od.colours:	C:h.print
od.colours:	h.psprite
od.colours:	h.sprwindow
od.colours:	h.toolwindow
od.colours:	h.colours
od.psprite:	c.psprite
od.psprite:	C:h.swis
od.psprite:	C:h.kernel
od.psprite:	C:h.bbc
od.psprite:	C:h.os
od.psprite:	C:h.colourtran
od.psprite:	C:h.wimp
od.psprite:	C:h.sprite
od.psprite:	C:h.font
od.psprite:	C:h.drawmod
od.psprite:	C:h.flex
od.psprite:	C:h.help
od.psprite:	C:h.event
od.psprite:	C:h.menu
od.psprite:	C:h.dbox
od.psprite:	C:h.resspr
od.psprite:	C:h.visdelay
od.psprite:	C:h.werr
od.psprite:	C:h.wimpt
od.psprite:	h.ftrace
od.psprite:	h.m
od.psprite:	h.ftrace
od.psprite:	h.main
od.psprite:	C:h.wimp
od.psprite:	C:h.sprite
od.psprite:	C:h.win
od.psprite:	C:h.msgs
od.psprite:	C:h.colourpick
od.psprite:	C:h.coords
od.psprite:	h.ftrace
od.psprite:	h.fixes
od.psprite:	h.sprwindow
od.psprite:	h.psprite
od.psprite:	h.toolwindow
od.psprite:	h.tools
od.psprite:	h.colours
od.psprite:	h.menus
od.psprite:	C:h.menu
od.psprite:	C:h.print
od.psprite:	h.menud
o.tools:	c.tools
o.tools:	C:h.swis
o.tools:	C:h.kernel
o.tools:	C:h.bbc
o.tools:	C:h.os
o.tools:	C:h.flex
o.tools:	C:h.visdelay
o.tools:	C:h.werr
o.tools:	C:h.wimpt
o.tools:	C:h.wimp
o.tools:	C:h.sprite
o.tools:	h.ftrace
o.tools:	h.main
o.tools:	C:h.wimp
o.tools:	C:h.sprite
o.tools:	C:h.win
o.tools:	C:h.msgs
o.tools:	C:h.colourpick
o.tools:	C:h.coords
o.tools:	h.ftrace
o.tools:	h.fixes
o.tools:	h.psprite
o.tools:	h.sprwindow
o.tools:	h.toolwindow
o.tools:	h.tools
o.tools:	h.colours
o.tools:	h.menus
o.tools:	C:h.menu
o.tools:	C:h.print
o.tools:	h.guard
o.tools:	h.writepixel
od.tools:	c.tools
od.tools:	C:h.swis
od.tools:	C:h.kernel
od.tools:	C:h.bbc
od.tools:	C:h.os
od.tools:	C:h.flex
od.tools:	C:h.visdelay
od.tools:	C:h.werr
od.tools:	C:h.wimpt
od.tools:	C:h.wimp
od.tools:	C:h.sprite
od.tools:	h.ftrace
od.tools:	h.main
od.tools:	C:h.wimp
od.tools:	C:h.sprite
od.tools:	C:h.win
od.tools:	C:h.msgs
od.tools:	C:h.colourpick
od.tools:	C:h.coords
od.tools:	h.ftrace
od.tools:	h.fixes
od.tools:	h.psprite
od.tools:	h.sprwindow
od.tools:	h.toolwindow
od.tools:	h.tools
od.tools:	h.colours
od.tools:	h.menus
od.tools:	C:h.menu
od.tools:	C:h.print
od.tools:	h.guard
od.tools:	h.writepixel
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
oz.colours:	c.colours
oz.colours:	C:h.swis
oz.colours:	C:h.kernel
oz.colours:	C:h.bbc
oz.colours:	C:h.os
oz.colours:	C:h.wimpt
oz.colours:	C:h.wimp
oz.colours:	C:h.sprite
oz.colours:	h.ftrace
oz.colours:	h.m
oz.colours:	h.ftrace
oz.colours:	h.main
oz.colours:	C:h.wimp
oz.colours:	C:h.sprite
oz.colours:	C:h.win
oz.colours:	C:h.msgs
oz.colours:	C:h.colourpick
oz.colours:	C:h.coords
oz.colours:	h.ftrace
oz.colours:	h.fixes
oz.colours:	h.menus
oz.colours:	C:h.menu
oz.colours:	C:h.print
oz.colours:	h.psprite
oz.colours:	h.sprwindow
oz.colours:	h.toolwindow
oz.colours:	h.colours
oz.main:	c.main
oz.main:	C:h.kernel
oz.main:	C:h.swis
oz.main:	C:h.pointer
oz.main:	C:h.sprite
oz.main:	C:h.os
oz.main:	C:h.wimp
oz.main:	C:h.akbd
oz.main:	C:h.alarm
oz.main:	C:h.baricon
oz.main:	C:h.bbc
oz.main:	C:h.colourpick
oz.main:	C:h.coords
oz.main:	C:h.dboxquery
oz.main:	C:h.heap
oz.main:	C:h.help
oz.main:	C:h.event
oz.main:	C:h.menu
oz.main:	C:h.dbox
oz.main:	C:h.flex
oz.main:	C:h.msgs
oz.main:	C:h.msgtrans
oz.main:	C:h.res
oz.main:	C:h.resspr
oz.main:	C:h.template
oz.main:	C:h.visdelay
oz.main:	C:h.werr
oz.main:	C:h.wimp
oz.main:	C:h.wimpt
oz.main:	C:h.xferrecv
oz.main:	h.ftrace
oz.main:	h.m
oz.main:	h.ftrace
oz.main:	h.main
oz.main:	C:h.wimp
oz.main:	C:h.sprite
oz.main:	C:h.win
oz.main:	C:h.msgs
oz.main:	C:h.colourpick
oz.main:	h.ftrace
oz.main:	h.fixes
oz.main:	h.menus
oz.main:	C:h.menu
oz.main:	C:h.print
oz.main:	h.MenuD
oz.main:	h.psprite
oz.main:	h.sprwindow
oz.main:	h.toolwindow
oz.main:	h.tools
oz.main:	h.colours
oz.main:	h.jpeg
oz.main:	C:h.drawmod
oz.menus:	c.menus
oz.menus:	C:h.swis
oz.menus:	C:h.kernel
oz.menus:	C:h.bbc
oz.menus:	C:h.os
oz.menus:	C:h.colourmenu
oz.menus:	C:h.menu
oz.menus:	C:h.colourtran
oz.menus:	C:h.wimp
oz.menus:	C:h.sprite
oz.menus:	C:h.font
oz.menus:	C:h.drawmod
oz.menus:	C:h.dboxquery
oz.menus:	C:h.dboxtcol
oz.menus:	C:h.flex
oz.menus:	C:h.help
oz.menus:	C:h.event
oz.menus:	C:h.dbox
oz.menus:	C:h.magnify
oz.menus:	C:h.msgtrans
oz.menus:	C:h.saveas
oz.menus:	C:h.xfersend
oz.menus:	C:h.visdelay
oz.menus:	C:h.werr
oz.menus:	C:h.wimpt
oz.menus:	C:h.xfersend
oz.menus:	h.m
oz.menus:	h.ftrace
oz.menus:	h.ftrace
oz.menus:	h.main
oz.menus:	C:h.wimp
oz.menus:	C:h.sprite
oz.menus:	C:h.win
oz.menus:	C:h.msgs
oz.menus:	C:h.colourpick
oz.menus:	C:h.coords
oz.menus:	h.ftrace
oz.menus:	h.fixes
oz.menus:	h.psprite
oz.menus:	h.menus
oz.menus:	C:h.menu
oz.menus:	C:h.print
oz.menus:	h.sprwindow
oz.menus:	h.toolwindow
oz.menus:	h.tools
oz.menus:	h.colours
oz.menus:	h.MenuD
oz.menus:	C:h.trace
oz.psprite:	c.psprite
oz.psprite:	C:h.swis
oz.psprite:	C:h.kernel
oz.psprite:	C:h.bbc
oz.psprite:	C:h.os
oz.psprite:	C:h.colourtran
oz.psprite:	C:h.wimp
oz.psprite:	C:h.sprite
oz.psprite:	C:h.font
oz.psprite:	C:h.drawmod
oz.psprite:	C:h.flex
oz.psprite:	C:h.help
oz.psprite:	C:h.event
oz.psprite:	C:h.menu
oz.psprite:	C:h.dbox
oz.psprite:	C:h.resspr
oz.psprite:	C:h.visdelay
oz.psprite:	C:h.werr
oz.psprite:	C:h.wimpt
oz.psprite:	h.ftrace
oz.psprite:	h.m
oz.psprite:	h.ftrace
oz.psprite:	h.main
oz.psprite:	C:h.wimp
oz.psprite:	C:h.sprite
oz.psprite:	C:h.win
oz.psprite:	C:h.msgs
oz.psprite:	C:h.colourpick
oz.psprite:	C:h.coords
oz.psprite:	h.ftrace
oz.psprite:	h.fixes
oz.psprite:	h.sprwindow
oz.psprite:	h.psprite
oz.psprite:	h.toolwindow
oz.psprite:	h.tools
oz.psprite:	h.colours
oz.psprite:	h.menus
oz.psprite:	C:h.menu
oz.psprite:	C:h.print
oz.psprite:	h.menud
oz.sprwindow:	c.sprwindow
oz.sprwindow:	C:h.swis
oz.sprwindow:	C:h.kernel
oz.sprwindow:	C:h.akbd
oz.sprwindow:	C:h.bbc
oz.sprwindow:	C:h.os
oz.sprwindow:	C:h.help
oz.sprwindow:	C:h.wimp
oz.sprwindow:	C:h.sprite
oz.sprwindow:	C:h.event
oz.sprwindow:	C:h.menu
oz.sprwindow:	C:h.dbox
oz.sprwindow:	C:h.xferrecv
oz.sprwindow:	C:h.werr
oz.sprwindow:	C:h.wimpt
oz.sprwindow:	h.ftrace
oz.sprwindow:	h.m
oz.sprwindow:	h.ftrace
oz.sprwindow:	h.main
oz.sprwindow:	C:h.wimp
oz.sprwindow:	C:h.sprite
oz.sprwindow:	C:h.win
oz.sprwindow:	C:h.msgs
oz.sprwindow:	C:h.colourpick
oz.sprwindow:	C:h.coords
oz.sprwindow:	h.ftrace
oz.sprwindow:	h.fixes
oz.sprwindow:	h.menus
oz.sprwindow:	C:h.menu
oz.sprwindow:	C:h.print
oz.sprwindow:	h.psprite
oz.sprwindow:	h.sprwindow
oz.sprwindow:	h.toolwindow
oz.sprwindow:	h.tools
oz.sprwindow:	h.colours
oz.tools:	c.tools
oz.tools:	C:h.swis
oz.tools:	C:h.kernel
oz.tools:	C:h.bbc
oz.tools:	C:h.os
oz.tools:	C:h.flex
oz.tools:	C:h.visdelay
oz.tools:	C:h.werr
oz.tools:	C:h.wimpt
oz.tools:	C:h.wimp
oz.tools:	C:h.sprite
oz.tools:	h.ftrace
oz.tools:	h.main
oz.tools:	C:h.wimp
oz.tools:	C:h.sprite
oz.tools:	C:h.win
oz.tools:	C:h.msgs
oz.tools:	C:h.colourpick
oz.tools:	C:h.coords
oz.tools:	h.ftrace
oz.tools:	h.fixes
oz.tools:	h.psprite
oz.tools:	h.sprwindow
oz.tools:	h.toolwindow
oz.tools:	h.tools
oz.tools:	h.colours
oz.tools:	h.menus
oz.tools:	C:h.menu
oz.tools:	C:h.print
oz.tools:	h.guard
oz.tools:	h.writepixel
oz.toolwindow:	c.toolwindow
oz.toolwindow:	C:h.wimpt
oz.toolwindow:	C:h.wimp
oz.toolwindow:	C:h.os
oz.toolwindow:	C:h.kernel
oz.toolwindow:	C:h.sprite
oz.toolwindow:	C:h.wimp
oz.toolwindow:	C:h.template
oz.toolwindow:	h.main
oz.toolwindow:	C:h.wimp
oz.toolwindow:	C:h.sprite
oz.toolwindow:	C:h.win
oz.toolwindow:	C:h.msgs
oz.toolwindow:	C:h.colourpick
oz.toolwindow:	C:h.coords
oz.toolwindow:	h.ftrace
oz.toolwindow:	h.fixes
oz.toolwindow:	h.menus
oz.toolwindow:	C:h.menu
oz.toolwindow:	C:h.print
oz.toolwindow:	h.psprite
oz.toolwindow:	h.sprwindow
oz.toolwindow:	h.toolwindow
oz.toolwindow:	h.tools
oz.toolwindow:	h.ftrace
oz.toolwindow:	h.guard
o.jpeg: asm.jpeg
o.writepixel: asm.writepixel
