# Makefile for Draw
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
COMPONENT  = Draw
APP        = !Draw
MODULE     = rm.!Draw
ROM_MODULE = aof.Draw
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
CFLAGS  = ${THROWBACK} -depend !Depend -fah ${INCLUDES} -wp
CPFLAGS = ~cfr~v
SQFLAGS = -f
WFLAGS  = ~c~v

#
# Libraries
#
CLIB      = CLib:o.stubs
RLIB      = RISC_OSLib:o.risc_oslib
ROMSTUBS  = RISC_OSLib:o.romstubs
ABSSYM    = RISC_OSLib:o.abssym
WRAPPER   = RISC_OSLib:s.ModuleWrap

LIBSD     = ${RLIB} ${CLIB}

#
# Include files
#
INCLUDES  = -IC:

FILES =\
 ${RDIR}.!Boot\
 ${LDIR}.!Help\
 ${LDIR}.!Run\
 $(RDIR).!Sprites\
 ${LDIR}.Messages\
 $(RDIR).Sprites\
 ${LDIR}.Templates\
 abs.!RunImage

FILESD =\
 ${RDIR}.!Boot\
 ${LDIR}.!Help\
 ${LDIR}.!Run\
 $(RDIR).!Sprites\
 ${LDIR}.Messages\
 $(RDIR).Sprites\
 ${LDIR}.Templates\
 abs.!RunImageD

# Include these in the ROM module
RESFILES =\
 ${RDIR}.Sprites

DFILES =\
 Debug.${APP}.!Boot\
 Debug.${APP}.!Help\
 Debug.${APP}.!Run \
 Debug.${APP}.!RunImage\
 Debug.${APP}.!Sprites\
 Debug.${APP}.Messages\
 Debug.${APP}.Sprites\
 Debug.${APP}.Templates

OBJS =\
 o.Draw o.DrawAction o.DrawCheck o.DrawDispl o.DrawDXF\
 o.DrawEdit o.DrawEnter o.DrawFileIO o.DrawGrid o.DrawHelp\
 o.DrawMenu o.DrawObject o.DrawPrint o.DrawScan o.DrawSelect\
 o.DrawTextC o.DrawTrans o.DrawUndo o.bezierarc o.jpeg

OBJSZ =\
 oz.Draw oz.DrawAction oz.DrawCheck oz.DrawDispl oz.DrawDXF\
 oz.DrawEdit oz.DrawEnter oz.DrawFileIO oz.DrawGrid oz.DrawHelp\
 oz.DrawMenu oz.DrawObject oz.DrawPrint oz.DrawScan oz.DrawSelect\
 oz.DrawTextC oz.DrawTrans oz.DrawUndo oz.bezierarc o.jpeg

OBJSD =\
 od.Draw od.DrawAction od.DrawCheck od.DrawDispl\
 od.DrawDXF od.DrawEdit od.DrawEnter od.DrawFileIO od.DrawGrid\
 od.DrawHelp od.DrawMenu od.DrawObject od.DrawPrint od.DrawScan\
 od.DrawSelect od.DrawTextC od.DrawTrans od.DrawUndo\
 od.bezierarc od.ftrace od.guard od.flex o.jpeg

ASMS =\
 s.Draw s.DrawAction s.DrawCheck s.DrawDispl s.DrawDXF\
 s.DrawEdit s.DrawEnter s.DrawFileIO s.DrawGrid s.DrawHelp\
 s.DrawMenu s.DrawObject s.DrawPrint s.DrawScan s.DrawSelect\
 s.DrawTextC s.DrawTrans s.DrawUndo s.bezierarc

#
# Rule patterns
#
.SUFFIXES: .oz .od .asm
.c.o:;    ${CC} ${CFLAGS} -c -ff $<
.c.oz:;   ${CC} ${CFLAGS} -c -ff -zM -zps1 -o $@ $<
.c.od:;   ${CC} ${CFLAGS} -c -DTRACE=1 -g -o $@ $<
.asm.o:;  ${AS} ${AFLAGS} $< $@
.c.s:;    ${CC} ${CFLAGS} -s -ff $<

#
# Main rules:
#
all: ${FILES}
        @echo ${COMPONENT}: Application built (Disc)

rom: ${ROM_MODULE}
        @echo ${COMPONENT}: Module built (ROM)

install: ${FILES}
        $(CP) $(RDIR).!Boot     ${INSTDIR}.!Boot     ${CPFLAGS}
        $(CP) $(LDIR).!Help     ${INSTDIR}.!Help     ${CPFLAGS}
        $(CP) $(LDIR).!Run      ${INSTDIR}.!Run      ${CPFLAGS}
        $(CP) abs.!RunImage     ${INSTDIR}.!RunImage ${CPFLAGS}
        $(CP) $(RDIR).!Sprites  ${INSTDIR}.!Sprites  ${CPFLAGS}
        $(CP) $(LDIR).Messages  ${INSTDIR}.Messages  ${CPFLAGS}
        $(CP) $(RDIR).Sprites   ${INSTDIR}.Sprites   ${CPFLAGS}
        $(CP) $(LDIR).Templates ${INSTDIR}.Templates ${CPFLAGS}
        -Access ${INSTDIR}.!Boot     lr/r
        -Access ${INSTDIR}.!Help     lr/r
        -Access ${INSTDIR}.!Run      lr/r
        -Access ${INSTDIR}.!RunImage lr/r
        -Access ${INSTDIR}.!Sprites  lr/r
        -Access ${INSTDIR}.Messages  lr/r
        -Access ${INSTDIR}.Sprites   lr/r
        -Access ${INSTDIR}.Templates lr/r
        @echo ${COMPONENT}: Application installed (Disc)

install_rom: ${ROM_MODULE}
        ${CP} ${ROM_MODULE} ${INSTDIR}.${COMPONENT} ${CPFLAGS}
        @echo ${COMPONENT}: Module installed (ROM)

installd: ${FILESD}
        $(CP) $(RDIR).!Boot     ${INSTDIR}.!Boot     ${CPFLAGS}ln
        $(CP) $(LDIR).!Help     ${INSTDIR}.!Help     ${CPFLAGS}ln
        $(CP) $(LDIR).!Run      ${INSTDIR}.!Run      ${CPFLAGS}ln
        $(CP) abs.!RunImageD    ${INSTDIR}.!RunImage ${CPFLAGS}ln
        $(CP) $(RDIR).!Sprites  ${INSTDIR}.!Sprites  ${CPFLAGS}ln
        $(CP) $(LDIR).Messages  ${INSTDIR}.Messages  ${CPFLAGS}ln
        $(CP) $(RDIR).Sprites   ${INSTDIR}.Sprites   ${CPFLAGS}ln
        $(CP) $(LDIR).Templates ${INSTDIR}.Templates ${CPFLAGS}ln
        -Access ${INSTDIR}.!Boot     lr/r
        -Access ${INSTDIR}.!Help     lr/r
        -Access ${INSTDIR}.!Run      lr/r
        -Access ${INSTDIR}.!RunImage lr/r
        -Access ${INSTDIR}.!Sprites  lr/r
        -Access ${INSTDIR}.Messages  lr/r
        -Access ${INSTDIR}.Sprites   lr/r
        -Access ${INSTDIR}.Templates lr/r
        @echo ${COMPONENT}: Application installed (Disc)

resources:
        ${MKDIR} ${RESDIR}
        ${MKDIR} ${RESAPP}
        ${CP} ${RDIR}.ROM.!Boot ${RESAPP}.!Boot ${CPFLAGS}
        ${CP} ${LDIR}.!Help     ${RESAPP}.!Help ${CPFLAGS}
        ${CP} ${RDIR}.ROM.!Run  ${RESAPP}.!Run  ${CPFLAGS}
        |
        ${CP} ${LDIR}.Messages  ${RESDIR}.Messages ${CPFLAGS}
        ${CP} ${LDIR}.Templates ${RESDIR}.Templates ${CPFLAGS}
        @echo ${COMPONENT}: resource files copied to Messages module

clean:
        ${WIPE} o.* ${WFLAGS}
        ${WIPE} s.* ${WFLAGS}
        ${WIPE} oz.* ${WFLAGS}
        ${WIPE} od.* ${WFLAGS}
        ${WIPE} linked.* ${WFLAGS}
        ${WIPE} map.* ${WFLAGS}
        ${RM} abs.!RunImage
        ${RM} ${ROM_MODULE}
        ${RM} ${MODULE}
        @echo ${COMPONENT}: cleaned

#
# Development rules:
# 
app: ${FILES}
        @echo Made application ${APP}

appd: ${DFILES}
        @echo Made Debug.${APP}

mod: ${MODULE}
        @echo ${COMPONENT}: Module built (RAM)

asms: ${ASMS}

linkmap: ${OBJS} ${LIBS}
   ${LD} -map -o null:x ${OBJS} ${LIBS} > map.linked

map:
   ${LD} -map -bin -base 0 -o null: ${OBJS} ${LIBS} > map.base0

clean_all:
   -Access ${INSTDIR}.!Boot     rw/rw
   -Access ${INSTDIR}.!Help     rw/rw
   -Access ${INSTDIR}.!Run      rw/rw
   -Access ${INSTDIR}.!RunImage rw/rw
   -Access ${INSTDIR}.!Sprites  rw/rw
   -Access ${INSTDIR}.Messages  rw/rw
   -Access ${INSTDIR}.Sprites   rw/rw
   -Access ${INSTDIR}.Templates rw/rw
   Destroy ${OBJS} ${OBJSD} ${ASMS} ${ROM_MODULE} ${MODULE} abs.!RunImage \
         s.AppName s.ModuleWrap s.ResFiles \
         Debug.RM.!Draw ${INSTDIR}.!Boot ${INSTDIR}.!Help \
         ${INSTDIR}.!Run ${INSTDIR}.!RunImage ${INSTDIR}.!Sprites \
         ${INSTDIR}.Messages ${INSTDIR}.Sprites ${INSTDIR}.Templates
#
# Static dependencies:
#
abs.!RunImage: ${OBJS} ${RLIB} ${CLIB}
        ${LD} -o $@ ${OBJS} ${RLIB} ${CLIB}
        ${SQUEEZE} ${SQFLAGS} $@

abs.!RunImageD: ${OBJSD} ${RLIB} ${CLIB}
        ${LD} -debug -o $@ ${OBJSD} ${RLIB} ${CLIB}

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

s.ResFiles: asm.ResFiles
        ${CP} asm.ResFiles $@ ${CPFLAGS}

#---------------------------------------------------------------------------
# debugging version:
#
Debug.${APP}.!RunImage: ${OBJSD} ${LIBSD}
        ${LD} -o $@ ${OBJSD} ${LIBSD}
        SetType $@ Absolute
        Squeeze $@

Debug.${APP}.!Boot: $(RDIR).!Boot
        ${CP} $(RDIR).!Boot $@ ${CPFLAGS}

Debug.${APP}.!Help: $(LDIR).!Help
        ${CP} $(LDIR).!Help $@ ${CPFLAGS}

Debug.${APP}.!Run: $(LDIR).!Run
        ${CP} $(LDIR).!Run $@ ${CPFLAGS}

Debug.${APP}.!Sprites: $(RDIR).!Sprites
        ${CP} $(RDIR).!Sprites $@ ${CPFLAGS}

Debug.${APP}.Messages: $(LDIR).Messages
        ${CP} $(LDIR).Messages $@ ${CPFLAGS}

Debug.${APP}.Sprites: $(RDIR).Sprites
        ${CP} $(RDIR).Sprites $@ ${CPFLAGS}

Debug.${APP}.Templates: $(LDIR).Templates
        ${CP} $(LDIR).Templates $@ ${CPFLAGS}
#---------------------------------------------------------------------------
# Dynamic dependencies:
o.Draw:	c.Draw
o.Draw:	C:h.kernel
o.Draw:	C:h.swis
o.Draw:	C:h.os
o.Draw:	C:h.akbd
o.Draw:	C:h.bbc
o.Draw:	C:h.flex
o.Draw:	C:h.heap
o.Draw:	C:h.menu
o.Draw:	C:h.pointer
o.Draw:	C:h.sprite
o.Draw:	C:h.wimp
o.Draw:	C:h.res
o.Draw:	C:h.resspr
o.Draw:	C:h.wimp
o.Draw:	C:h.wimpt
o.Draw:	C:h.win
o.Draw:	C:h.werr
o.Draw:	C:h.baricon
o.Draw:	C:h.template
o.Draw:	C:h.visdelay
o.Draw:	C:h.msgs
o.Draw:	C:h.msgtrans
o.Draw:	C:h.dboxquery
o.Draw:	C:h.xferrecv
o.Draw:	C:h.saveas
o.Draw:	C:h.xfersend
o.Draw:	h.bezierarc
o.Draw:	C:h.help
o.Draw:	C:h.event
o.Draw:	C:h.dbox
o.Draw:	h.ftrace
o.Draw:	h.guard
o.Draw:	h.Draw
o.Draw:	C:h.drawmod
o.Draw:	h.jpeg
o.Draw:	h.DrawAction
o.Draw:	h.DrawDispl
o.Draw:	C:h.font
o.Draw:	h.DrawDXF
o.Draw:	h.DrawEdit
o.Draw:	h.DrawEnter
o.Draw:	h.DrawFileIO
o.Draw:	h.DrawGrid
o.Draw:	h.DrawHelp
o.Draw:	h.DrawMenu
o.Draw:	h.DrawObject
o.Draw:	h.DrawPrint
o.Draw:	h.DrawSelect
o.Draw:	h.DrawTrans
o.Draw:	h.DrawUndo
o.DrawAction:	c.DrawAction
o.DrawAction:	C:h.os
o.DrawAction:	C:h.kernel
o.DrawAction:	C:h.bbc
o.DrawAction:	C:h.wimp
o.DrawAction:	C:h.sprite
o.DrawAction:	C:h.wimpt
o.DrawAction:	h.ftrace
o.DrawAction:	h.guard
o.DrawAction:	h.Draw
o.DrawAction:	C:h.drawmod
o.DrawAction:	C:h.dbox
o.DrawAction:	h.jpeg
o.DrawAction:	h.DrawAction
o.DrawAction:	h.DrawDispl
o.DrawAction:	C:h.font
o.DrawAction:	h.DrawGrid
o.DrawAction:	h.DrawPrint
o.DrawAction:	h.DrawMenu
o.DrawAction:	C:h.menu
o.DrawCheck:	c.DrawCheck
o.DrawCheck:	C:h.os
o.DrawCheck:	C:h.kernel
o.DrawCheck:	C:h.wimp
o.DrawCheck:	C:h.sprite
o.DrawCheck:	C:h.sprite
o.DrawCheck:	C:h.werr
o.DrawCheck:	C:h.xferrecv
o.DrawCheck:	C:h.msgs
o.DrawCheck:	h.ftrace
o.DrawCheck:	h.guard
o.DrawCheck:	h.Draw
o.DrawCheck:	C:h.drawmod
o.DrawCheck:	C:h.dbox
o.DrawCheck:	h.jpeg
o.DrawCheck:	h.DrawCheck
o.DrawCheck:	h.DrawObject
o.DrawCheck:	h.DrawTextC
o.DrawCheck:	h.DrawTrans
o.DrawCheck:	h.DrawFileIO
o.DrawCheck:	h.DrawDispl
o.DrawCheck:	C:h.font
o.DrawDXF:	c.DrawDXF
o.DrawDXF:	C:h.os
o.DrawDXF:	C:h.kernel
o.DrawDXF:	C:h.wimp
o.DrawDXF:	C:h.sprite
o.DrawDXF:	C:h.flex
o.DrawDXF:	C:h.heap
o.DrawDXF:	C:h.werr
o.DrawDXF:	C:h.xferrecv
o.DrawDXF:	C:h.visdelay
o.DrawDXF:	C:h.msgs
o.DrawDXF:	h.bezierarc
o.DrawDXF:	C:h.dbox
o.DrawDXF:	C:h.help
o.DrawDXF:	C:h.event
o.DrawDXF:	C:h.menu
o.DrawDXF:	h.ftrace
o.DrawDXF:	h.guard
o.DrawDXF:	h.Draw
o.DrawDXF:	C:h.drawmod
o.DrawDXF:	h.jpeg
o.DrawDXF:	h.DrawCheck
o.DrawDXF:	h.DrawFileIO
o.DrawDXF:	h.DrawObject
o.DrawDXF:	h.DrawDXF
o.DrawEnter:	c.DrawEnter
o.DrawEnter:	C:h.swis
o.DrawEnter:	C:h.kernel
o.DrawEnter:	C:h.os
o.DrawEnter:	C:h.bbc
o.DrawEnter:	C:h.wimp
o.DrawEnter:	C:h.sprite
o.DrawEnter:	C:h.wimpt
o.DrawEnter:	C:h.win
o.DrawEnter:	C:h.event
o.DrawEnter:	C:h.menu
o.DrawEnter:	h.ftrace
o.DrawEnter:	h.guard
o.DrawEnter:	h.Draw
o.DrawEnter:	C:h.drawmod
o.DrawEnter:	C:h.dbox
o.DrawEnter:	h.jpeg
o.DrawEnter:	h.DrawDispl
o.DrawEnter:	C:h.font
o.DrawEnter:	h.DrawEdit
o.DrawEnter:	h.DrawEnter
o.DrawEnter:	h.DrawObject
o.DrawGrid:	c.DrawGrid
o.DrawGrid:	C:h.os
o.DrawGrid:	C:h.kernel
o.DrawGrid:	C:h.bbc
o.DrawGrid:	C:h.wimp
o.DrawGrid:	C:h.sprite
o.DrawGrid:	h.ftrace
o.DrawGrid:	h.guard
o.DrawGrid:	h.Draw
o.DrawGrid:	C:h.drawmod
o.DrawGrid:	C:h.dbox
o.DrawGrid:	h.jpeg
o.DrawGrid:	h.DrawDispl
o.DrawGrid:	C:h.font
o.DrawGrid:	h.DrawGrid
o.DrawHelp:	c.DrawHelp
o.DrawHelp:	C:h.os
o.DrawHelp:	C:h.kernel
o.DrawHelp:	C:h.wimp
o.DrawHelp:	C:h.sprite
o.DrawHelp:	C:h.wimpt
o.DrawHelp:	C:h.msgs
o.DrawHelp:	h.ftrace
o.DrawHelp:	h.guard
o.DrawHelp:	h.Draw
o.DrawHelp:	C:h.drawmod
o.DrawHelp:	C:h.dbox
o.DrawHelp:	h.jpeg
o.DrawHelp:	h.DrawHelp
o.DrawScan:	c.DrawScan
o.DrawScan:	C:h.os
o.DrawScan:	C:h.kernel
o.DrawScan:	C:h.wimp
o.DrawScan:	C:h.sprite
o.DrawScan:	C:h.werr
o.DrawScan:	h.ftrace
o.DrawScan:	h.guard
o.DrawScan:	h.Draw
o.DrawScan:	C:h.drawmod
o.DrawScan:	C:h.dbox
o.DrawScan:	h.jpeg
o.DrawScan:	h.DrawDispl
o.DrawScan:	C:h.font
o.DrawScan:	h.DrawObject
o.DrawScan:	h.DrawScan
o.DrawScan:	h.DrawSelect
o.DrawScan:	h.DrawUndo
o.DrawTextC:	c.DrawTextC
o.DrawTextC:	C:h.swis
o.DrawTextC:	C:h.kernel
o.DrawTextC:	C:h.os
o.DrawTextC:	C:h.bbc
o.DrawTextC:	C:h.flex
o.DrawTextC:	C:h.font
o.DrawTextC:	C:h.drawmod
o.DrawTextC:	C:h.wimp
o.DrawTextC:	C:h.sprite
o.DrawTextC:	C:h.wimp
o.DrawTextC:	C:h.wimpt
o.DrawTextC:	C:h.werr
o.DrawTextC:	C:h.colourtran
o.DrawTextC:	C:h.msgs
o.DrawTextC:	C:h.xferrecv
o.DrawTextC:	h.ftrace
o.DrawTextC:	h.guard
o.DrawTextC:	h.Draw
o.DrawTextC:	C:h.dbox
o.DrawTextC:	h.jpeg
o.DrawTextC:	h.DrawAction
o.DrawTextC:	h.DrawDispl
o.DrawTextC:	h.DrawObject
o.DrawTextC:	h.DrawFileIO
o.DrawTextC:	h.DrawMenu
o.DrawTextC:	C:h.menu
o.DrawTextC:	h.DrawSelect
o.DrawTextC:	h.DrawTextC
o.DrawTrans:	c.DrawTrans
o.DrawTrans:	C:h.os
o.DrawTrans:	C:h.kernel
o.DrawTrans:	C:h.msgs
o.DrawTrans:	C:h.wimp
o.DrawTrans:	C:h.sprite
o.DrawTrans:	C:h.sprite
o.DrawTrans:	C:h.werr
o.DrawTrans:	C:h.visdelay
o.DrawTrans:	h.ftrace
o.DrawTrans:	h.guard
o.DrawTrans:	h.Draw
o.DrawTrans:	C:h.drawmod
o.DrawTrans:	C:h.dbox
o.DrawTrans:	h.jpeg
o.DrawTrans:	h.DrawDispl
o.DrawTrans:	C:h.font
o.DrawTrans:	h.DrawGrid
o.DrawTrans:	h.DrawObject
o.DrawTrans:	h.DrawScan
o.DrawTrans:	h.DrawTextC
o.DrawTrans:	h.DrawTrans
o.DrawTrans:	h.DrawUndo
o.DrawUndo:	c.DrawUndo
o.DrawUndo:	C:h.os
o.DrawUndo:	C:h.kernel
o.DrawUndo:	C:h.wimp
o.DrawUndo:	C:h.sprite
o.DrawUndo:	C:h.flex
o.DrawUndo:	C:h.heap
o.DrawUndo:	C:h.werr
o.DrawUndo:	h.ftrace
o.DrawUndo:	h.guard
o.DrawUndo:	h.Draw
o.DrawUndo:	C:h.drawmod
o.DrawUndo:	C:h.dbox
o.DrawUndo:	h.jpeg
o.DrawUndo:	h.DrawDispl
o.DrawUndo:	C:h.font
o.DrawUndo:	h.DrawObject
o.DrawUndo:	h.DrawSelect
o.DrawUndo:	h.DrawTrans
o.DrawUndo:	h.DrawUndo
o.bezierarc:	c.bezierarc
o.bezierarc:	C:h.os
o.bezierarc:	C:h.kernel
o.bezierarc:	h.bezierarc
o.DrawDispl:	c.DrawDispl
o.DrawDispl:	C:h.swis
o.DrawDispl:	C:h.kernel
o.DrawDispl:	C:h.os
o.DrawDispl:	C:h.bbc
o.DrawDispl:	C:h.colourtran
o.DrawDispl:	C:h.wimp
o.DrawDispl:	C:h.sprite
o.DrawDispl:	C:h.font
o.DrawDispl:	C:h.drawmod
o.DrawDispl:	C:h.drawmod
o.DrawDispl:	C:h.font
o.DrawDispl:	C:h.msgs
o.DrawDispl:	C:h.werr
o.DrawDispl:	C:h.wimp
o.DrawDispl:	C:h.wimpt
o.DrawDispl:	h.ftrace
o.DrawDispl:	h.guard
o.DrawDispl:	h.Draw
o.DrawDispl:	C:h.dbox
o.DrawDispl:	h.jpeg
o.DrawDispl:	h.DrawAction
o.DrawDispl:	h.DrawDispl
o.DrawDispl:	h.DrawEdit
o.DrawDispl:	h.DrawEnter
o.DrawDispl:	h.DrawGrid
o.DrawDispl:	h.DrawObject
o.DrawDispl:	h.DrawPrint
o.DrawDispl:	h.DrawSelect
o.DrawDispl:	h.DrawTextC
o.DrawEdit:	c.DrawEdit
o.DrawEdit:	C:h.os
o.DrawEdit:	C:h.kernel
o.DrawEdit:	C:h.wimp
o.DrawEdit:	C:h.sprite
o.DrawEdit:	C:h.werr
o.DrawEdit:	C:h.dbox
o.DrawEdit:	C:h.msgs
o.DrawEdit:	C:h.help
o.DrawEdit:	C:h.event
o.DrawEdit:	C:h.menu
o.DrawEdit:	h.ftrace
o.DrawEdit:	h.guard
o.DrawEdit:	h.Draw
o.DrawEdit:	C:h.drawmod
o.DrawEdit:	h.jpeg
o.DrawEdit:	h.DrawAction
o.DrawEdit:	h.DrawDispl
o.DrawEdit:	C:h.font
o.DrawEdit:	h.DrawEdit
o.DrawEdit:	h.DrawEnter
o.DrawEdit:	h.DrawGrid
o.DrawEdit:	h.DrawMenu
o.DrawEdit:	h.DrawMenuD
o.DrawEdit:	h.DrawObject
o.DrawEdit:	h.DrawSelect
o.DrawEdit:	h.DrawUndo
o.DrawMenu:	c.DrawMenu
o.DrawMenu:	C:h.akbd
o.DrawMenu:	C:h.colourmenu
o.DrawMenu:	C:h.menu
o.DrawMenu:	C:h.dbox
o.DrawMenu:	C:h.dboxtcol
o.DrawMenu:	C:h.event
o.DrawMenu:	C:h.wimp
o.DrawMenu:	C:h.os
o.DrawMenu:	C:h.kernel
o.DrawMenu:	C:h.sprite
o.DrawMenu:	C:h.magnify
o.DrawMenu:	C:h.msgs
o.DrawMenu:	C:h.os
o.DrawMenu:	C:h.saveas
o.DrawMenu:	C:h.xfersend
o.DrawMenu:	C:h.werr
o.DrawMenu:	C:h.wimp
o.DrawMenu:	C:h.wimpt
o.DrawMenu:	C:h.xferrecv
o.DrawMenu:	C:h.help
o.DrawMenu:	h.ftrace
o.DrawMenu:	h.guard
o.DrawMenu:	h.Draw
o.DrawMenu:	C:h.drawmod
o.DrawMenu:	h.jpeg
o.DrawMenu:	h.DrawAction
o.DrawMenu:	h.DrawDispl
o.DrawMenu:	C:h.font
o.DrawMenu:	h.DrawEdit
o.DrawMenu:	h.DrawEnter
o.DrawMenu:	h.DrawFileIO
o.DrawMenu:	h.DrawGrid
o.DrawMenu:	h.DrawMenu
o.DrawMenu:	h.DrawMenuD
o.DrawMenu:	h.DrawObject
o.DrawMenu:	h.DrawPrint
o.DrawMenu:	h.DrawScan
o.DrawMenu:	h.DrawSelect
o.DrawMenu:	h.DrawTextC
o.DrawMenu:	h.DrawTrans
o.DrawMenu:	h.DrawUndo
o.DrawSelect:	c.DrawSelect
o.DrawSelect:	C:h.bbc
o.DrawSelect:	C:h.os
o.DrawSelect:	C:h.kernel
o.DrawSelect:	C:h.flex
o.DrawSelect:	C:h.font
o.DrawSelect:	C:h.drawmod
o.DrawSelect:	C:h.wimp
o.DrawSelect:	C:h.sprite
o.DrawSelect:	C:h.msgs
o.DrawSelect:	C:h.os
o.DrawSelect:	C:h.sprite
o.DrawSelect:	C:h.visdelay
o.DrawSelect:	C:h.werr
o.DrawSelect:	C:h.wimp
o.DrawSelect:	C:h.wimpt
o.DrawSelect:	h.ftrace
o.DrawSelect:	h.guard
o.DrawSelect:	h.Draw
o.DrawSelect:	C:h.dbox
o.DrawSelect:	h.jpeg
o.DrawSelect:	h.DrawAction
o.DrawSelect:	h.DrawDispl
o.DrawSelect:	h.DrawEnter
o.DrawSelect:	h.DrawGrid
o.DrawSelect:	h.DrawObject
o.DrawSelect:	h.DrawScan
o.DrawSelect:	h.DrawSelect
o.DrawSelect:	h.DrawTextC
o.DrawSelect:	h.DrawTrans
o.DrawSelect:	h.DrawUndo
od.Draw:	c.Draw
od.Draw:	C:h.kernel
od.Draw:	C:h.swis
od.Draw:	C:h.os
od.Draw:	C:h.akbd
od.Draw:	C:h.bbc
od.Draw:	C:h.flex
od.Draw:	C:h.heap
od.Draw:	C:h.menu
od.Draw:	C:h.pointer
od.Draw:	C:h.sprite
od.Draw:	C:h.wimp
od.Draw:	C:h.res
od.Draw:	C:h.resspr
od.Draw:	C:h.wimp
od.Draw:	C:h.wimpt
od.Draw:	C:h.win
od.Draw:	C:h.werr
od.Draw:	C:h.baricon
od.Draw:	C:h.template
od.Draw:	C:h.visdelay
od.Draw:	C:h.msgs
od.Draw:	C:h.msgtrans
od.Draw:	C:h.dboxquery
od.Draw:	C:h.xferrecv
od.Draw:	C:h.saveas
od.Draw:	C:h.xfersend
od.Draw:	h.bezierarc
od.Draw:	C:h.help
od.Draw:	C:h.event
od.Draw:	C:h.dbox
od.Draw:	h.ftrace
od.Draw:	h.guard
od.Draw:	h.Draw
od.Draw:	C:h.drawmod
od.Draw:	h.jpeg
od.Draw:	h.DrawAction
od.Draw:	h.DrawDispl
od.Draw:	C:h.font
od.Draw:	h.DrawDXF
od.Draw:	h.DrawEdit
od.Draw:	h.DrawEnter
od.Draw:	h.DrawFileIO
od.Draw:	h.DrawGrid
od.Draw:	h.DrawHelp
od.Draw:	h.DrawMenu
od.Draw:	h.DrawObject
od.Draw:	h.DrawPrint
od.Draw:	h.DrawSelect
od.Draw:	h.DrawTrans
od.Draw:	h.DrawUndo
od.DrawAction:	c.DrawAction
od.DrawAction:	C:h.os
od.DrawAction:	C:h.kernel
od.DrawAction:	C:h.bbc
od.DrawAction:	C:h.wimp
od.DrawAction:	C:h.sprite
od.DrawAction:	C:h.wimpt
od.DrawAction:	h.ftrace
od.DrawAction:	h.guard
od.DrawAction:	h.Draw
od.DrawAction:	C:h.drawmod
od.DrawAction:	C:h.dbox
od.DrawAction:	h.jpeg
od.DrawAction:	h.DrawAction
od.DrawAction:	h.DrawDispl
od.DrawAction:	C:h.font
od.DrawAction:	h.DrawGrid
od.DrawAction:	h.DrawPrint
od.DrawAction:	h.DrawMenu
od.DrawAction:	C:h.menu
od.DrawCheck:	c.DrawCheck
od.DrawCheck:	C:h.os
od.DrawCheck:	C:h.kernel
od.DrawCheck:	C:h.wimp
od.DrawCheck:	C:h.sprite
od.DrawCheck:	C:h.sprite
od.DrawCheck:	C:h.werr
od.DrawCheck:	C:h.xferrecv
od.DrawCheck:	C:h.msgs
od.DrawCheck:	h.ftrace
od.DrawCheck:	h.guard
od.DrawCheck:	h.Draw
od.DrawCheck:	C:h.drawmod
od.DrawCheck:	C:h.dbox
od.DrawCheck:	h.jpeg
od.DrawCheck:	h.DrawCheck
od.DrawCheck:	h.DrawObject
od.DrawCheck:	h.DrawTextC
od.DrawCheck:	h.DrawTrans
od.DrawCheck:	h.DrawFileIO
od.DrawCheck:	h.DrawDispl
od.DrawCheck:	C:h.font
od.DrawDispl:	c.DrawDispl
od.DrawDispl:	C:h.swis
od.DrawDispl:	C:h.kernel
od.DrawDispl:	C:h.os
od.DrawDispl:	C:h.bbc
od.DrawDispl:	C:h.colourtran
od.DrawDispl:	C:h.wimp
od.DrawDispl:	C:h.sprite
od.DrawDispl:	C:h.font
od.DrawDispl:	C:h.drawmod
od.DrawDispl:	C:h.drawmod
od.DrawDispl:	C:h.font
od.DrawDispl:	C:h.msgs
od.DrawDispl:	C:h.werr
od.DrawDispl:	C:h.wimp
od.DrawDispl:	C:h.wimpt
od.DrawDispl:	h.ftrace
od.DrawDispl:	h.guard
od.DrawDispl:	h.Draw
od.DrawDispl:	C:h.dbox
od.DrawDispl:	h.jpeg
od.DrawDispl:	h.DrawAction
od.DrawDispl:	h.DrawDispl
od.DrawDispl:	h.DrawEdit
od.DrawDispl:	h.DrawEnter
od.DrawDispl:	h.DrawGrid
od.DrawDispl:	h.DrawObject
od.DrawDispl:	h.DrawPrint
od.DrawDispl:	h.DrawSelect
od.DrawDispl:	h.DrawTextC
od.DrawDXF:	c.DrawDXF
od.DrawDXF:	C:h.os
od.DrawDXF:	C:h.kernel
od.DrawDXF:	C:h.wimp
od.DrawDXF:	C:h.sprite
od.DrawDXF:	C:h.flex
od.DrawDXF:	C:h.heap
od.DrawDXF:	C:h.werr
od.DrawDXF:	C:h.xferrecv
od.DrawDXF:	C:h.visdelay
od.DrawDXF:	C:h.msgs
od.DrawDXF:	h.bezierarc
od.DrawDXF:	C:h.dbox
od.DrawDXF:	C:h.help
od.DrawDXF:	C:h.event
od.DrawDXF:	C:h.menu
od.DrawDXF:	h.ftrace
od.DrawDXF:	h.guard
od.DrawDXF:	h.Draw
od.DrawDXF:	C:h.drawmod
od.DrawDXF:	h.jpeg
od.DrawDXF:	h.DrawCheck
od.DrawDXF:	h.DrawFileIO
od.DrawDXF:	h.DrawObject
od.DrawDXF:	h.DrawDXF
od.DrawEdit:	c.DrawEdit
od.DrawEdit:	C:h.os
od.DrawEdit:	C:h.kernel
od.DrawEdit:	C:h.wimp
od.DrawEdit:	C:h.sprite
od.DrawEdit:	C:h.werr
od.DrawEdit:	C:h.dbox
od.DrawEdit:	C:h.msgs
od.DrawEdit:	C:h.help
od.DrawEdit:	C:h.event
od.DrawEdit:	C:h.menu
od.DrawEdit:	h.ftrace
od.DrawEdit:	h.guard
od.DrawEdit:	h.Draw
od.DrawEdit:	C:h.drawmod
od.DrawEdit:	h.jpeg
od.DrawEdit:	h.DrawAction
od.DrawEdit:	h.DrawDispl
od.DrawEdit:	C:h.font
od.DrawEdit:	h.DrawEdit
od.DrawEdit:	h.DrawEnter
od.DrawEdit:	h.DrawGrid
od.DrawEdit:	h.DrawMenu
od.DrawEdit:	h.DrawMenuD
od.DrawEdit:	h.DrawObject
od.DrawEdit:	h.DrawSelect
od.DrawEdit:	h.DrawUndo
od.DrawEnter:	c.DrawEnter
od.DrawEnter:	C:h.swis
od.DrawEnter:	C:h.kernel
od.DrawEnter:	C:h.os
od.DrawEnter:	C:h.bbc
od.DrawEnter:	C:h.wimp
od.DrawEnter:	C:h.sprite
od.DrawEnter:	C:h.wimpt
od.DrawEnter:	C:h.win
od.DrawEnter:	C:h.event
od.DrawEnter:	C:h.menu
od.DrawEnter:	h.ftrace
od.DrawEnter:	h.guard
od.DrawEnter:	h.Draw
od.DrawEnter:	C:h.drawmod
od.DrawEnter:	C:h.dbox
od.DrawEnter:	h.jpeg
od.DrawEnter:	h.DrawDispl
od.DrawEnter:	C:h.font
od.DrawEnter:	h.DrawEdit
od.DrawEnter:	h.DrawEnter
od.DrawEnter:	h.DrawObject
od.DrawGrid:	c.DrawGrid
od.DrawGrid:	C:h.os
od.DrawGrid:	C:h.kernel
od.DrawGrid:	C:h.bbc
od.DrawGrid:	C:h.wimp
od.DrawGrid:	C:h.sprite
od.DrawGrid:	h.ftrace
od.DrawGrid:	h.guard
od.DrawGrid:	h.Draw
od.DrawGrid:	C:h.drawmod
od.DrawGrid:	C:h.dbox
od.DrawGrid:	h.jpeg
od.DrawGrid:	h.DrawDispl
od.DrawGrid:	C:h.font
od.DrawGrid:	h.DrawGrid
od.DrawHelp:	c.DrawHelp
od.DrawHelp:	C:h.os
od.DrawHelp:	C:h.kernel
od.DrawHelp:	C:h.wimp
od.DrawHelp:	C:h.sprite
od.DrawHelp:	C:h.wimpt
od.DrawHelp:	C:h.msgs
od.DrawHelp:	h.ftrace
od.DrawHelp:	h.guard
od.DrawHelp:	h.Draw
od.DrawHelp:	C:h.drawmod
od.DrawHelp:	C:h.dbox
od.DrawHelp:	h.jpeg
od.DrawHelp:	h.DrawHelp
od.DrawMenu:	c.DrawMenu
od.DrawMenu:	C:h.akbd
od.DrawMenu:	C:h.colourmenu
od.DrawMenu:	C:h.menu
od.DrawMenu:	C:h.dbox
od.DrawMenu:	C:h.dboxtcol
od.DrawMenu:	C:h.event
od.DrawMenu:	C:h.wimp
od.DrawMenu:	C:h.os
od.DrawMenu:	C:h.kernel
od.DrawMenu:	C:h.sprite
od.DrawMenu:	C:h.magnify
od.DrawMenu:	C:h.msgs
od.DrawMenu:	C:h.os
od.DrawMenu:	C:h.saveas
od.DrawMenu:	C:h.xfersend
od.DrawMenu:	C:h.werr
od.DrawMenu:	C:h.wimp
od.DrawMenu:	C:h.wimpt
od.DrawMenu:	C:h.xferrecv
od.DrawMenu:	C:h.help
od.DrawMenu:	h.ftrace
od.DrawMenu:	h.guard
od.DrawMenu:	h.Draw
od.DrawMenu:	C:h.drawmod
od.DrawMenu:	h.jpeg
od.DrawMenu:	h.DrawAction
od.DrawMenu:	h.DrawDispl
od.DrawMenu:	C:h.font
od.DrawMenu:	h.DrawEdit
od.DrawMenu:	h.DrawEnter
od.DrawMenu:	h.DrawFileIO
od.DrawMenu:	h.DrawGrid
od.DrawMenu:	h.DrawMenu
od.DrawMenu:	h.DrawMenuD
od.DrawMenu:	h.DrawObject
od.DrawMenu:	h.DrawPrint
od.DrawMenu:	h.DrawScan
od.DrawMenu:	h.DrawSelect
od.DrawMenu:	h.DrawTextC
od.DrawMenu:	h.DrawTrans
od.DrawMenu:	h.DrawUndo
od.DrawScan:	c.DrawScan
od.DrawScan:	C:h.os
od.DrawScan:	C:h.kernel
od.DrawScan:	C:h.wimp
od.DrawScan:	C:h.sprite
od.DrawScan:	C:h.werr
od.DrawScan:	h.ftrace
od.DrawScan:	h.guard
od.DrawScan:	h.Draw
od.DrawScan:	C:h.drawmod
od.DrawScan:	C:h.dbox
od.DrawScan:	h.jpeg
od.DrawScan:	h.DrawDispl
od.DrawScan:	C:h.font
od.DrawScan:	h.DrawObject
od.DrawScan:	h.DrawScan
od.DrawScan:	h.DrawSelect
od.DrawScan:	h.DrawUndo
od.DrawSelect:	c.DrawSelect
od.DrawSelect:	C:h.bbc
od.DrawSelect:	C:h.os
od.DrawSelect:	C:h.kernel
od.DrawSelect:	C:h.flex
od.DrawSelect:	C:h.font
od.DrawSelect:	C:h.drawmod
od.DrawSelect:	C:h.wimp
od.DrawSelect:	C:h.sprite
od.DrawSelect:	C:h.msgs
od.DrawSelect:	C:h.os
od.DrawSelect:	C:h.sprite
od.DrawSelect:	C:h.visdelay
od.DrawSelect:	C:h.werr
od.DrawSelect:	C:h.wimp
od.DrawSelect:	C:h.wimpt
od.DrawSelect:	h.ftrace
od.DrawSelect:	h.guard
od.DrawSelect:	h.Draw
od.DrawSelect:	C:h.dbox
od.DrawSelect:	h.jpeg
od.DrawSelect:	h.DrawAction
od.DrawSelect:	h.DrawDispl
od.DrawSelect:	h.DrawEnter
od.DrawSelect:	h.DrawGrid
od.DrawSelect:	h.DrawObject
od.DrawSelect:	h.DrawScan
od.DrawSelect:	h.DrawSelect
od.DrawSelect:	h.DrawTextC
od.DrawSelect:	h.DrawTrans
od.DrawSelect:	h.DrawUndo
od.DrawTextC:	c.DrawTextC
od.DrawTextC:	C:h.swis
od.DrawTextC:	C:h.kernel
od.DrawTextC:	C:h.os
od.DrawTextC:	C:h.bbc
od.DrawTextC:	C:h.flex
od.DrawTextC:	C:h.font
od.DrawTextC:	C:h.drawmod
od.DrawTextC:	C:h.wimp
od.DrawTextC:	C:h.sprite
od.DrawTextC:	C:h.wimp
od.DrawTextC:	C:h.wimpt
od.DrawTextC:	C:h.werr
od.DrawTextC:	C:h.colourtran
od.DrawTextC:	C:h.msgs
od.DrawTextC:	C:h.xferrecv
od.DrawTextC:	h.ftrace
od.DrawTextC:	h.guard
od.DrawTextC:	h.Draw
od.DrawTextC:	C:h.dbox
od.DrawTextC:	h.jpeg
od.DrawTextC:	h.DrawAction
od.DrawTextC:	h.DrawDispl
od.DrawTextC:	h.DrawObject
od.DrawTextC:	h.DrawFileIO
od.DrawTextC:	h.DrawMenu
od.DrawTextC:	C:h.menu
od.DrawTextC:	h.DrawSelect
od.DrawTextC:	h.DrawTextC
od.DrawTrans:	c.DrawTrans
od.DrawTrans:	C:h.os
od.DrawTrans:	C:h.kernel
od.DrawTrans:	C:h.msgs
od.DrawTrans:	C:h.wimp
od.DrawTrans:	C:h.sprite
od.DrawTrans:	C:h.sprite
od.DrawTrans:	C:h.werr
od.DrawTrans:	C:h.visdelay
od.DrawTrans:	h.ftrace
od.DrawTrans:	h.guard
od.DrawTrans:	h.Draw
od.DrawTrans:	C:h.drawmod
od.DrawTrans:	C:h.dbox
od.DrawTrans:	h.jpeg
od.DrawTrans:	h.DrawDispl
od.DrawTrans:	C:h.font
od.DrawTrans:	h.DrawGrid
od.DrawTrans:	h.DrawObject
od.DrawTrans:	h.DrawScan
od.DrawTrans:	h.DrawTextC
od.DrawTrans:	h.DrawTrans
od.DrawTrans:	h.DrawUndo
od.DrawUndo:	c.DrawUndo
od.DrawUndo:	C:h.os
od.DrawUndo:	C:h.kernel
od.DrawUndo:	C:h.wimp
od.DrawUndo:	C:h.sprite
od.DrawUndo:	C:h.flex
od.DrawUndo:	C:h.heap
od.DrawUndo:	C:h.werr
od.DrawUndo:	h.ftrace
od.DrawUndo:	h.guard
od.DrawUndo:	h.Draw
od.DrawUndo:	C:h.drawmod
od.DrawUndo:	C:h.dbox
od.DrawUndo:	h.jpeg
od.DrawUndo:	h.DrawDispl
od.DrawUndo:	C:h.font
od.DrawUndo:	h.DrawObject
od.DrawUndo:	h.DrawSelect
od.DrawUndo:	h.DrawTrans
od.DrawUndo:	h.DrawUndo
od.bezierarc:	c.bezierarc
od.bezierarc:	C:h.os
od.bezierarc:	C:h.kernel
od.bezierarc:	h.bezierarc
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
od.flex:	c.flex
od.flex:	C:h.kernel
od.flex:	C:h.swis
od.flex:	C:h.os
od.flex:	C:h.werr
od.flex:	C:h.flex
od.flex:	h.ftrace
od.flex:	C:h.wimp
od.flex:	C:h.sprite
od.flex:	C:h.wimpt
od.flex:	C:h.msgs
od.flex:	C:h.verintern.messages
o.DrawFileIO:	c.DrawFileIO
o.DrawFileIO:	C:h.os
o.DrawFileIO:	C:h.kernel
o.DrawFileIO:	C:h.bbc
o.DrawFileIO:	C:h.flex
o.DrawFileIO:	C:h.wimp
o.DrawFileIO:	C:h.sprite
o.DrawFileIO:	C:h.wimpt
o.DrawFileIO:	C:h.werr
o.DrawFileIO:	C:h.msgs
o.DrawFileIO:	C:h.visdelay
o.DrawFileIO:	C:h.xferrecv
o.DrawFileIO:	C:h.xfersend
o.DrawFileIO:	h.ftrace
o.DrawFileIO:	h.guard
o.DrawFileIO:	h.Draw
o.DrawFileIO:	C:h.drawmod
o.DrawFileIO:	C:h.dbox
o.DrawFileIO:	h.jpeg
o.DrawFileIO:	h.DrawAction
o.DrawFileIO:	h.DrawCheck
o.DrawFileIO:	h.DrawDispl
o.DrawFileIO:	C:h.font
o.DrawFileIO:	h.DrawDXF
o.DrawFileIO:	h.DrawEnter
o.DrawFileIO:	h.DrawFileIO
o.DrawFileIO:	h.DrawMenu
o.DrawFileIO:	C:h.menu
o.DrawFileIO:	h.DrawObject
o.DrawFileIO:	h.DrawPrint
o.DrawFileIO:	h.DrawSelect
o.DrawFileIO:	h.DrawTextC
o.DrawFileIO:	h.DrawUndo
od.DrawFileIO:	c.DrawFileIO
od.DrawFileIO:	C:h.os
od.DrawFileIO:	C:h.kernel
od.DrawFileIO:	C:h.bbc
od.DrawFileIO:	C:h.flex
od.DrawFileIO:	C:h.wimp
od.DrawFileIO:	C:h.sprite
od.DrawFileIO:	C:h.wimpt
od.DrawFileIO:	C:h.werr
od.DrawFileIO:	C:h.msgs
od.DrawFileIO:	C:h.visdelay
od.DrawFileIO:	C:h.xferrecv
od.DrawFileIO:	C:h.xfersend
od.DrawFileIO:	h.ftrace
od.DrawFileIO:	h.guard
od.DrawFileIO:	h.Draw
od.DrawFileIO:	C:h.drawmod
od.DrawFileIO:	C:h.dbox
od.DrawFileIO:	h.jpeg
od.DrawFileIO:	h.DrawAction
od.DrawFileIO:	h.DrawCheck
od.DrawFileIO:	h.DrawDispl
od.DrawFileIO:	C:h.font
od.DrawFileIO:	h.DrawDXF
od.DrawFileIO:	h.DrawEnter
od.DrawFileIO:	h.DrawFileIO
od.DrawFileIO:	h.DrawMenu
od.DrawFileIO:	C:h.menu
od.DrawFileIO:	h.DrawObject
od.DrawFileIO:	h.DrawPrint
od.DrawFileIO:	h.DrawSelect
od.DrawFileIO:	h.DrawTextC
od.DrawFileIO:	h.DrawUndo
o.DrawObject:	c.DrawObject
o.DrawObject:	C:h.swis
o.DrawObject:	C:h.kernel
o.DrawObject:	C:h.bbc
o.DrawObject:	C:h.os
o.DrawObject:	h.bezierarc
o.DrawObject:	C:h.flex
o.DrawObject:	C:h.font
o.DrawObject:	C:h.drawmod
o.DrawObject:	C:h.wimp
o.DrawObject:	C:h.sprite
o.DrawObject:	C:h.msgs
o.DrawObject:	C:h.os
o.DrawObject:	C:h.sprite
o.DrawObject:	C:h.werr
o.DrawObject:	C:h.wimp
o.DrawObject:	C:h.wimpt
o.DrawObject:	h.ftrace
o.DrawObject:	h.guard
o.DrawObject:	h.Draw
o.DrawObject:	C:h.dbox
o.DrawObject:	h.jpeg
o.DrawObject:	h.DrawAction
o.DrawObject:	h.DrawDispl
o.DrawObject:	h.DrawEnter
o.DrawObject:	h.DrawObject
o.DrawObject:	h.DrawSelect
o.DrawObject:	h.DrawTextC
o.DrawObject:	h.DrawTrans
o.DrawObject:	h.DrawUndo
od.DrawObject:	c.DrawObject
od.DrawObject:	C:h.swis
od.DrawObject:	C:h.kernel
od.DrawObject:	C:h.bbc
od.DrawObject:	C:h.os
od.DrawObject:	h.bezierarc
od.DrawObject:	C:h.flex
od.DrawObject:	C:h.font
od.DrawObject:	C:h.drawmod
od.DrawObject:	C:h.wimp
od.DrawObject:	C:h.sprite
od.DrawObject:	C:h.msgs
od.DrawObject:	C:h.os
od.DrawObject:	C:h.sprite
od.DrawObject:	C:h.werr
od.DrawObject:	C:h.wimp
od.DrawObject:	C:h.wimpt
od.DrawObject:	h.ftrace
od.DrawObject:	h.guard
od.DrawObject:	h.Draw
od.DrawObject:	C:h.dbox
od.DrawObject:	h.jpeg
od.DrawObject:	h.DrawAction
od.DrawObject:	h.DrawDispl
od.DrawObject:	h.DrawEnter
od.DrawObject:	h.DrawObject
od.DrawObject:	h.DrawSelect
od.DrawObject:	h.DrawTextC
od.DrawObject:	h.DrawTrans
od.DrawObject:	h.DrawUndo
od.DrawPrint:	c.DrawPrint
od.DrawPrint:	C:h.swis
od.DrawPrint:	C:h.kernel
od.DrawPrint:	C:h.os
od.DrawPrint:	C:h.wimp
od.DrawPrint:	C:h.sprite
od.DrawPrint:	C:h.wimpt
od.DrawPrint:	C:h.visdelay
od.DrawPrint:	C:h.msgs
od.DrawPrint:	C:h.werr
od.DrawPrint:	C:h.print
od.DrawPrint:	C:h.xferrecv
od.DrawPrint:	C:h.xfersend
od.DrawPrint:	h.ftrace
od.DrawPrint:	h.guard
od.DrawPrint:	h.Draw
od.DrawPrint:	C:h.drawmod
od.DrawPrint:	C:h.dbox
od.DrawPrint:	h.jpeg
od.DrawPrint:	h.DrawAction
od.DrawPrint:	h.DrawDispl
od.DrawPrint:	C:h.font
od.DrawPrint:	h.DrawFileIO
od.DrawPrint:	h.DrawObject
od.DrawPrint:	h.DrawPrint
o.DrawPrint:	c.DrawPrint
o.DrawPrint:	C:h.swis
o.DrawPrint:	C:h.kernel
o.DrawPrint:	C:h.os
o.DrawPrint:	C:h.wimp
o.DrawPrint:	C:h.sprite
o.DrawPrint:	C:h.wimpt
o.DrawPrint:	C:h.visdelay
o.DrawPrint:	C:h.msgs
o.DrawPrint:	C:h.werr
o.DrawPrint:	C:h.print
o.DrawPrint:	C:h.xferrecv
o.DrawPrint:	C:h.xfersend
o.DrawPrint:	h.ftrace
o.DrawPrint:	h.guard
o.DrawPrint:	h.Draw
o.DrawPrint:	C:h.drawmod
o.DrawPrint:	C:h.dbox
o.DrawPrint:	h.jpeg
o.DrawPrint:	h.DrawAction
o.DrawPrint:	h.DrawDispl
o.DrawPrint:	C:h.font
o.DrawPrint:	h.DrawFileIO
o.DrawPrint:	h.DrawObject
o.DrawPrint:	h.DrawPrint
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
oz.Draw:	c.Draw
oz.Draw:	C:h.kernel
oz.Draw:	C:h.swis
oz.Draw:	C:h.os
oz.Draw:	C:h.akbd
oz.Draw:	C:h.bbc
oz.Draw:	C:h.flex
oz.Draw:	C:h.heap
oz.Draw:	C:h.menu
oz.Draw:	C:h.pointer
oz.Draw:	C:h.sprite
oz.Draw:	C:h.wimp
oz.Draw:	C:h.res
oz.Draw:	C:h.resspr
oz.Draw:	C:h.wimp
oz.Draw:	C:h.wimpt
oz.Draw:	C:h.win
oz.Draw:	C:h.werr
oz.Draw:	C:h.baricon
oz.Draw:	C:h.template
oz.Draw:	C:h.visdelay
oz.Draw:	C:h.msgs
oz.Draw:	C:h.msgtrans
oz.Draw:	C:h.dboxquery
oz.Draw:	C:h.xferrecv
oz.Draw:	C:h.saveas
oz.Draw:	C:h.xfersend
oz.Draw:	h.bezierarc
oz.Draw:	C:h.help
oz.Draw:	C:h.event
oz.Draw:	C:h.dbox
oz.Draw:	h.ftrace
oz.Draw:	h.guard
oz.Draw:	h.Draw
oz.Draw:	C:h.drawmod
oz.Draw:	h.jpeg
oz.Draw:	h.DrawAction
oz.Draw:	h.DrawDispl
oz.Draw:	C:h.font
oz.Draw:	h.DrawDXF
oz.Draw:	h.DrawEdit
oz.Draw:	h.DrawEnter
oz.Draw:	h.DrawFileIO
oz.Draw:	h.DrawGrid
oz.Draw:	h.DrawHelp
oz.Draw:	h.DrawMenu
oz.Draw:	h.DrawObject
oz.Draw:	h.DrawPrint
oz.Draw:	h.DrawSelect
oz.Draw:	h.DrawTrans
oz.Draw:	h.DrawUndo
oz.DrawAction:	c.DrawAction
oz.DrawAction:	C:h.os
oz.DrawAction:	C:h.kernel
oz.DrawAction:	C:h.bbc
oz.DrawAction:	C:h.wimp
oz.DrawAction:	C:h.sprite
oz.DrawAction:	C:h.wimpt
oz.DrawAction:	h.ftrace
oz.DrawAction:	h.guard
oz.DrawAction:	h.Draw
oz.DrawAction:	C:h.drawmod
oz.DrawAction:	C:h.dbox
oz.DrawAction:	h.jpeg
oz.DrawAction:	h.DrawAction
oz.DrawAction:	h.DrawDispl
oz.DrawAction:	C:h.font
oz.DrawAction:	h.DrawGrid
oz.DrawAction:	h.DrawPrint
oz.DrawAction:	h.DrawMenu
oz.DrawAction:	C:h.menu
oz.DrawCheck:	c.DrawCheck
oz.DrawCheck:	C:h.os
oz.DrawCheck:	C:h.kernel
oz.DrawCheck:	C:h.wimp
oz.DrawCheck:	C:h.sprite
oz.DrawCheck:	C:h.sprite
oz.DrawCheck:	C:h.werr
oz.DrawCheck:	C:h.xferrecv
oz.DrawCheck:	C:h.msgs
oz.DrawCheck:	h.ftrace
oz.DrawCheck:	h.guard
oz.DrawCheck:	h.Draw
oz.DrawCheck:	C:h.drawmod
oz.DrawCheck:	C:h.dbox
oz.DrawCheck:	h.jpeg
oz.DrawCheck:	h.DrawCheck
oz.DrawCheck:	h.DrawObject
oz.DrawCheck:	h.DrawTextC
oz.DrawCheck:	h.DrawTrans
oz.DrawCheck:	h.DrawFileIO
oz.DrawCheck:	h.DrawDispl
oz.DrawCheck:	C:h.font
oz.DrawDispl:	c.DrawDispl
oz.DrawDispl:	C:h.swis
oz.DrawDispl:	C:h.kernel
oz.DrawDispl:	C:h.os
oz.DrawDispl:	C:h.bbc
oz.DrawDispl:	C:h.colourtran
oz.DrawDispl:	C:h.wimp
oz.DrawDispl:	C:h.sprite
oz.DrawDispl:	C:h.font
oz.DrawDispl:	C:h.drawmod
oz.DrawDispl:	C:h.drawmod
oz.DrawDispl:	C:h.font
oz.DrawDispl:	C:h.msgs
oz.DrawDispl:	C:h.werr
oz.DrawDispl:	C:h.wimp
oz.DrawDispl:	C:h.wimpt
oz.DrawDispl:	h.ftrace
oz.DrawDispl:	h.guard
oz.DrawDispl:	h.Draw
oz.DrawDispl:	C:h.dbox
oz.DrawDispl:	h.jpeg
oz.DrawDispl:	h.DrawAction
oz.DrawDispl:	h.DrawDispl
oz.DrawDispl:	h.DrawEdit
oz.DrawDispl:	h.DrawEnter
oz.DrawDispl:	h.DrawGrid
oz.DrawDispl:	h.DrawObject
oz.DrawDispl:	h.DrawPrint
oz.DrawDispl:	h.DrawSelect
oz.DrawDispl:	h.DrawTextC
oz.DrawDXF:	c.DrawDXF
oz.DrawDXF:	C:h.os
oz.DrawDXF:	C:h.kernel
oz.DrawDXF:	C:h.wimp
oz.DrawDXF:	C:h.sprite
oz.DrawDXF:	C:h.flex
oz.DrawDXF:	C:h.heap
oz.DrawDXF:	C:h.werr
oz.DrawDXF:	C:h.xferrecv
oz.DrawDXF:	C:h.visdelay
oz.DrawDXF:	C:h.msgs
oz.DrawDXF:	h.bezierarc
oz.DrawDXF:	C:h.dbox
oz.DrawDXF:	C:h.help
oz.DrawDXF:	C:h.event
oz.DrawDXF:	C:h.menu
oz.DrawDXF:	h.ftrace
oz.DrawDXF:	h.guard
oz.DrawDXF:	h.Draw
oz.DrawDXF:	C:h.drawmod
oz.DrawDXF:	h.jpeg
oz.DrawDXF:	h.DrawCheck
oz.DrawDXF:	h.DrawFileIO
oz.DrawDXF:	h.DrawObject
oz.DrawDXF:	h.DrawDXF
oz.DrawEdit:	c.DrawEdit
oz.DrawEdit:	C:h.os
oz.DrawEdit:	C:h.kernel
oz.DrawEdit:	C:h.wimp
oz.DrawEdit:	C:h.sprite
oz.DrawEdit:	C:h.werr
oz.DrawEdit:	C:h.dbox
oz.DrawEdit:	C:h.msgs
oz.DrawEdit:	C:h.help
oz.DrawEdit:	C:h.event
oz.DrawEdit:	C:h.menu
oz.DrawEdit:	h.ftrace
oz.DrawEdit:	h.guard
oz.DrawEdit:	h.Draw
oz.DrawEdit:	C:h.drawmod
oz.DrawEdit:	h.jpeg
oz.DrawEdit:	h.DrawAction
oz.DrawEdit:	h.DrawDispl
oz.DrawEdit:	C:h.font
oz.DrawEdit:	h.DrawEdit
oz.DrawEdit:	h.DrawEnter
oz.DrawEdit:	h.DrawGrid
oz.DrawEdit:	h.DrawMenu
oz.DrawEdit:	h.DrawMenuD
oz.DrawEdit:	h.DrawObject
oz.DrawEdit:	h.DrawSelect
oz.DrawEdit:	h.DrawUndo
oz.DrawEnter:	c.DrawEnter
oz.DrawEnter:	C:h.swis
oz.DrawEnter:	C:h.kernel
oz.DrawEnter:	C:h.os
oz.DrawEnter:	C:h.bbc
oz.DrawEnter:	C:h.wimp
oz.DrawEnter:	C:h.sprite
oz.DrawEnter:	C:h.wimpt
oz.DrawEnter:	C:h.win
oz.DrawEnter:	C:h.event
oz.DrawEnter:	C:h.menu
oz.DrawEnter:	h.ftrace
oz.DrawEnter:	h.guard
oz.DrawEnter:	h.Draw
oz.DrawEnter:	C:h.drawmod
oz.DrawEnter:	C:h.dbox
oz.DrawEnter:	h.jpeg
oz.DrawEnter:	h.DrawDispl
oz.DrawEnter:	C:h.font
oz.DrawEnter:	h.DrawEdit
oz.DrawEnter:	h.DrawEnter
oz.DrawEnter:	h.DrawObject
oz.DrawFileIO:	c.DrawFileIO
oz.DrawFileIO:	C:h.os
oz.DrawFileIO:	C:h.kernel
oz.DrawFileIO:	C:h.bbc
oz.DrawFileIO:	C:h.flex
oz.DrawFileIO:	C:h.wimp
oz.DrawFileIO:	C:h.sprite
oz.DrawFileIO:	C:h.wimpt
oz.DrawFileIO:	C:h.werr
oz.DrawFileIO:	C:h.msgs
oz.DrawFileIO:	C:h.visdelay
oz.DrawFileIO:	C:h.xferrecv
oz.DrawFileIO:	C:h.xfersend
oz.DrawFileIO:	h.ftrace
oz.DrawFileIO:	h.guard
oz.DrawFileIO:	h.Draw
oz.DrawFileIO:	C:h.drawmod
oz.DrawFileIO:	C:h.dbox
oz.DrawFileIO:	h.jpeg
oz.DrawFileIO:	h.DrawAction
oz.DrawFileIO:	h.DrawCheck
oz.DrawFileIO:	h.DrawDispl
oz.DrawFileIO:	C:h.font
oz.DrawFileIO:	h.DrawDXF
oz.DrawFileIO:	h.DrawEnter
oz.DrawFileIO:	h.DrawFileIO
oz.DrawFileIO:	h.DrawMenu
oz.DrawFileIO:	C:h.menu
oz.DrawFileIO:	h.DrawObject
oz.DrawFileIO:	h.DrawPrint
oz.DrawFileIO:	h.DrawSelect
oz.DrawFileIO:	h.DrawTextC
oz.DrawFileIO:	h.DrawUndo
oz.DrawGrid:	c.DrawGrid
oz.DrawGrid:	C:h.os
oz.DrawGrid:	C:h.kernel
oz.DrawGrid:	C:h.bbc
oz.DrawGrid:	C:h.wimp
oz.DrawGrid:	C:h.sprite
oz.DrawGrid:	h.ftrace
oz.DrawGrid:	h.guard
oz.DrawGrid:	h.Draw
oz.DrawGrid:	C:h.drawmod
oz.DrawGrid:	C:h.dbox
oz.DrawGrid:	h.jpeg
oz.DrawGrid:	h.DrawDispl
oz.DrawGrid:	C:h.font
oz.DrawGrid:	h.DrawGrid
oz.DrawHelp:	c.DrawHelp
oz.DrawHelp:	C:h.os
oz.DrawHelp:	C:h.kernel
oz.DrawHelp:	C:h.wimp
oz.DrawHelp:	C:h.sprite
oz.DrawHelp:	C:h.wimpt
oz.DrawHelp:	C:h.msgs
oz.DrawHelp:	h.ftrace
oz.DrawHelp:	h.guard
oz.DrawHelp:	h.Draw
oz.DrawHelp:	C:h.drawmod
oz.DrawHelp:	C:h.dbox
oz.DrawHelp:	h.jpeg
oz.DrawHelp:	h.DrawHelp
oz.DrawMenu:	c.DrawMenu
oz.DrawMenu:	C:h.akbd
oz.DrawMenu:	C:h.colourmenu
oz.DrawMenu:	C:h.menu
oz.DrawMenu:	C:h.dbox
oz.DrawMenu:	C:h.dboxtcol
oz.DrawMenu:	C:h.event
oz.DrawMenu:	C:h.wimp
oz.DrawMenu:	C:h.os
oz.DrawMenu:	C:h.kernel
oz.DrawMenu:	C:h.sprite
oz.DrawMenu:	C:h.magnify
oz.DrawMenu:	C:h.msgs
oz.DrawMenu:	C:h.os
oz.DrawMenu:	C:h.saveas
oz.DrawMenu:	C:h.xfersend
oz.DrawMenu:	C:h.werr
oz.DrawMenu:	C:h.wimp
oz.DrawMenu:	C:h.wimpt
oz.DrawMenu:	C:h.xferrecv
oz.DrawMenu:	C:h.help
oz.DrawMenu:	h.ftrace
oz.DrawMenu:	h.guard
oz.DrawMenu:	h.Draw
oz.DrawMenu:	C:h.drawmod
oz.DrawMenu:	h.jpeg
oz.DrawMenu:	h.DrawAction
oz.DrawMenu:	h.DrawDispl
oz.DrawMenu:	C:h.font
oz.DrawMenu:	h.DrawEdit
oz.DrawMenu:	h.DrawEnter
oz.DrawMenu:	h.DrawFileIO
oz.DrawMenu:	h.DrawGrid
oz.DrawMenu:	h.DrawMenu
oz.DrawMenu:	h.DrawMenuD
oz.DrawMenu:	h.DrawObject
oz.DrawMenu:	h.DrawPrint
oz.DrawMenu:	h.DrawScan
oz.DrawMenu:	h.DrawSelect
oz.DrawMenu:	h.DrawTextC
oz.DrawMenu:	h.DrawTrans
oz.DrawMenu:	h.DrawUndo
oz.DrawObject:	c.DrawObject
oz.DrawObject:	C:h.swis
oz.DrawObject:	C:h.kernel
oz.DrawObject:	C:h.bbc
oz.DrawObject:	C:h.os
oz.DrawObject:	h.bezierarc
oz.DrawObject:	C:h.flex
oz.DrawObject:	C:h.font
oz.DrawObject:	C:h.drawmod
oz.DrawObject:	C:h.wimp
oz.DrawObject:	C:h.sprite
oz.DrawObject:	C:h.msgs
oz.DrawObject:	C:h.os
oz.DrawObject:	C:h.sprite
oz.DrawObject:	C:h.werr
oz.DrawObject:	C:h.wimp
oz.DrawObject:	C:h.wimpt
oz.DrawObject:	h.ftrace
oz.DrawObject:	h.guard
oz.DrawObject:	h.Draw
oz.DrawObject:	C:h.dbox
oz.DrawObject:	h.jpeg
oz.DrawObject:	h.DrawAction
oz.DrawObject:	h.DrawDispl
oz.DrawObject:	h.DrawEnter
oz.DrawObject:	h.DrawObject
oz.DrawObject:	h.DrawSelect
oz.DrawObject:	h.DrawTextC
oz.DrawObject:	h.DrawTrans
oz.DrawObject:	h.DrawUndo
oz.DrawPrint:	c.DrawPrint
oz.DrawPrint:	C:h.swis
oz.DrawPrint:	C:h.kernel
oz.DrawPrint:	C:h.os
oz.DrawPrint:	C:h.wimp
oz.DrawPrint:	C:h.sprite
oz.DrawPrint:	C:h.wimpt
oz.DrawPrint:	C:h.visdelay
oz.DrawPrint:	C:h.msgs
oz.DrawPrint:	C:h.werr
oz.DrawPrint:	C:h.print
oz.DrawPrint:	C:h.xferrecv
oz.DrawPrint:	C:h.xfersend
oz.DrawPrint:	h.ftrace
oz.DrawPrint:	h.guard
oz.DrawPrint:	h.Draw
oz.DrawPrint:	C:h.drawmod
oz.DrawPrint:	C:h.dbox
oz.DrawPrint:	h.jpeg
oz.DrawPrint:	h.DrawAction
oz.DrawPrint:	h.DrawDispl
oz.DrawPrint:	C:h.font
oz.DrawPrint:	h.DrawFileIO
oz.DrawPrint:	h.DrawObject
oz.DrawPrint:	h.DrawPrint
oz.DrawScan:	c.DrawScan
oz.DrawScan:	C:h.os
oz.DrawScan:	C:h.kernel
oz.DrawScan:	C:h.wimp
oz.DrawScan:	C:h.sprite
oz.DrawScan:	C:h.werr
oz.DrawScan:	h.ftrace
oz.DrawScan:	h.guard
oz.DrawScan:	h.Draw
oz.DrawScan:	C:h.drawmod
oz.DrawScan:	C:h.dbox
oz.DrawScan:	h.jpeg
oz.DrawScan:	h.DrawDispl
oz.DrawScan:	C:h.font
oz.DrawScan:	h.DrawObject
oz.DrawScan:	h.DrawScan
oz.DrawScan:	h.DrawSelect
oz.DrawScan:	h.DrawUndo
oz.DrawSelect:	c.DrawSelect
oz.DrawSelect:	C:h.bbc
oz.DrawSelect:	C:h.os
oz.DrawSelect:	C:h.kernel
oz.DrawSelect:	C:h.flex
oz.DrawSelect:	C:h.font
oz.DrawSelect:	C:h.drawmod
oz.DrawSelect:	C:h.wimp
oz.DrawSelect:	C:h.sprite
oz.DrawSelect:	C:h.msgs
oz.DrawSelect:	C:h.os
oz.DrawSelect:	C:h.sprite
oz.DrawSelect:	C:h.visdelay
oz.DrawSelect:	C:h.werr
oz.DrawSelect:	C:h.wimp
oz.DrawSelect:	C:h.wimpt
oz.DrawSelect:	h.ftrace
oz.DrawSelect:	h.guard
oz.DrawSelect:	h.Draw
oz.DrawSelect:	C:h.dbox
oz.DrawSelect:	h.jpeg
oz.DrawSelect:	h.DrawAction
oz.DrawSelect:	h.DrawDispl
oz.DrawSelect:	h.DrawEnter
oz.DrawSelect:	h.DrawGrid
oz.DrawSelect:	h.DrawObject
oz.DrawSelect:	h.DrawScan
oz.DrawSelect:	h.DrawSelect
oz.DrawSelect:	h.DrawTextC
oz.DrawSelect:	h.DrawTrans
oz.DrawSelect:	h.DrawUndo
oz.DrawTextC:	c.DrawTextC
oz.DrawTextC:	C:h.swis
oz.DrawTextC:	C:h.kernel
oz.DrawTextC:	C:h.os
oz.DrawTextC:	C:h.bbc
oz.DrawTextC:	C:h.flex
oz.DrawTextC:	C:h.font
oz.DrawTextC:	C:h.drawmod
oz.DrawTextC:	C:h.wimp
oz.DrawTextC:	C:h.sprite
oz.DrawTextC:	C:h.wimp
oz.DrawTextC:	C:h.wimpt
oz.DrawTextC:	C:h.werr
oz.DrawTextC:	C:h.colourtran
oz.DrawTextC:	C:h.msgs
oz.DrawTextC:	C:h.xferrecv
oz.DrawTextC:	h.ftrace
oz.DrawTextC:	h.guard
oz.DrawTextC:	h.Draw
oz.DrawTextC:	C:h.dbox
oz.DrawTextC:	h.jpeg
oz.DrawTextC:	h.DrawAction
oz.DrawTextC:	h.DrawDispl
oz.DrawTextC:	h.DrawObject
oz.DrawTextC:	h.DrawFileIO
oz.DrawTextC:	h.DrawMenu
oz.DrawTextC:	C:h.menu
oz.DrawTextC:	h.DrawSelect
oz.DrawTextC:	h.DrawTextC
oz.DrawTrans:	c.DrawTrans
oz.DrawTrans:	C:h.os
oz.DrawTrans:	C:h.kernel
oz.DrawTrans:	C:h.msgs
oz.DrawTrans:	C:h.wimp
oz.DrawTrans:	C:h.sprite
oz.DrawTrans:	C:h.sprite
oz.DrawTrans:	C:h.werr
oz.DrawTrans:	C:h.visdelay
oz.DrawTrans:	h.ftrace
oz.DrawTrans:	h.guard
oz.DrawTrans:	h.Draw
oz.DrawTrans:	C:h.drawmod
oz.DrawTrans:	C:h.dbox
oz.DrawTrans:	h.jpeg
oz.DrawTrans:	h.DrawDispl
oz.DrawTrans:	C:h.font
oz.DrawTrans:	h.DrawGrid
oz.DrawTrans:	h.DrawObject
oz.DrawTrans:	h.DrawScan
oz.DrawTrans:	h.DrawTextC
oz.DrawTrans:	h.DrawTrans
oz.DrawTrans:	h.DrawUndo
oz.DrawUndo:	c.DrawUndo
oz.DrawUndo:	C:h.os
oz.DrawUndo:	C:h.kernel
oz.DrawUndo:	C:h.wimp
oz.DrawUndo:	C:h.sprite
oz.DrawUndo:	C:h.flex
oz.DrawUndo:	C:h.heap
oz.DrawUndo:	C:h.werr
oz.DrawUndo:	h.ftrace
oz.DrawUndo:	h.guard
oz.DrawUndo:	h.Draw
oz.DrawUndo:	C:h.drawmod
oz.DrawUndo:	C:h.dbox
oz.DrawUndo:	h.jpeg
oz.DrawUndo:	h.DrawDispl
oz.DrawUndo:	C:h.font
oz.DrawUndo:	h.DrawObject
oz.DrawUndo:	h.DrawSelect
oz.DrawUndo:	h.DrawTrans
oz.DrawUndo:	h.DrawUndo
oz.bezierarc:	c.bezierarc
oz.bezierarc:	C:h.os
oz.bezierarc:	C:h.kernel
oz.bezierarc:	h.bezierarc
o.jpeg: asm.jpeg
