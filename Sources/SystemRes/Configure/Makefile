# Makefile for Configure
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name    Description
# ----       ----    -----------
# 02-Nov-94  AMcC    Updated for Black build
# 30-Jan-95  AMcC    Configure/FontMerge now have separate installation
#

#
# Program specific options:
#
#COMPONENT  = Set in Components/Installation file
RDIR       = Resources
LDIR       = ${RDIR}.${LOCALE}

#
# Generic options:
#
MKDIR   = cdir
AS      = objasm
CC      = cc #-DTRACE=1
CP      = copy
LD      = link
RM      = remove
SQUEEZE = squeeze
WIPE    = -wipe

AFLAGS   = ${THROWBACK} -depend !Depend -nocache -stamp -quit
CFLAGS   = ${THROWBACK} -depend !Depend -ffah ${INCLUDES} ${DFLAGS}
DFLAGS   = -DBLUEROM -DSTANDALONE
INCLUDES = -IC:
CPFLAGS  = ~cfr~v
WFLAGS   = ~cr~v

#
# Libraries
#
CLIB      = CLib:o.stubs
RLIB      = RISC_OSLib:o.risc_oslib

# Configure
FILES =\
 ${RDIR}.!Boot\
 ${LDIR}.!Help\
 ${LDIR}.!Run\
 ${LDIR}.Messages\
 ${RDIR}.Sprites\
 ${RDIR}.Sprites22\
 ${LDIR}.Templates\
 ${RDIR}.tile_1\
 abs.!RunImage

# FontMerge
FONTFILES =\
 ${RDIR}.FontMerge.!Run\
 ${LDIR}.FontMerge.Messages\
 abs.FontMerge

OBJS =\
 o.apps\
 o.cmos\
 o.configfile\
 o.configure\
 o.econet\
 o.inetsetup\
 o.filer\
 o.floppies\
 o.fonts\
 o.harddiscs\
 o.keyboard\
 o.lock\
 o.memory\
 o.mouse\
 o.printer\
 o.screen\
 o.sound\
 o.system\
 o.version\
 o.wimpflags #o.ftrace

ASMS =\
 s.apps\
 s.cmos\
 s.configfile\
 s.configure\
 s.econet\
 s.inetsetup\
 s.filer\
 s.floppies\
 s.fonts\
 s.harddiscs\
 s.keyboard\
 s.lock\
 s.memory\
 s.mouse\
 s.printer\
 s.screen\
 s.sound\
 s.system\
 s.version\
 s.wimpflags

#
# Rule patterns
#
.SUFFIXES: .c .o .s .asm
.c.o:;     ${CC} -c ${CFLAGS} $<
.asm.o:;   ${AS} ${AFLAGS} $< $@
.c.s:;     ${CC} -s ${CFLAGS} $<

#
# Main rules:
#
all: ${FONTFILES} ${FILES}
        @echo ${COMPONENT}: Application built (Disc)

install: install_${COMPONENT}; @

install_Configure: ${FILES}
        |
        ${MKDIR} ${INSTDIR}.!Configure
        |
        ${CP} ${RDIR}.!Boot      ${INSTDIR}.!Configure.!Boot      ${CPFLAGS}
        ${CP} ${LDIR}.!Help      ${INSTDIR}.!Configure.!Help      ${CPFLAGS}
        ${CP} ${LDIR}.!Run       ${INSTDIR}.!Configure.!Run       ${CPFLAGS}
        ${CP} abs.!RunImage      ${INSTDIR}.!Configure.!RunImage  ${CPFLAGS}
        ${CP} ${LDIR}.Messages   ${INSTDIR}.!Configure.Messages   ${CPFLAGS}
        ${CP} ${RDIR}.Sprites    ${INSTDIR}.!Configure.Sprites    ${CPFLAGS}
        ${CP} ${RDIR}.Sprites22  ${INSTDIR}.!Configure.Sprites22  ${CPFLAGS}
        ${CP} ${LDIR}.Templates  ${INSTDIR}.!Configure.Templates  ${CPFLAGS}
        ${CP} ${RDIR}.tile_1     ${INSTDIR}.!Configure.tile_1     ${CPFLAGS}
        |
        Access ${INSTDIR}.!Configure /r
        Access ${INSTDIR}.!Configure.* WR/r
        |
        @echo Configure: Application installed (Disc)

install_FontMerge: ${FONTFILES}
        |
        ${MKDIR} ${INSTDIR}.FontMerge
        |
        ${CP} ${RDIR}.FontMerge.!Run      ${INSTDIR}.FontMerge.!Run      ${CPFLAGS}
        ${CP} abs.FontMerge               ${INSTDIR}.FontMerge.FontMerge ${CPFLAGS}
        ${CP} ${LDIR}.FontMerge.Messages  ${INSTDIR}.FontMerge.Messages  ${CPFLAGS}
        |
        Access ${INSTDIR}.FontMerge /r
        Access ${INSTDIR}.FontMerge.* WR/r
        |
        @echo FontMerge: Application installed (Disc)

clean:
        ${WIPE} o.* ${WFLAGS}
        ${RM} abs.!RunImage
        ${RM} abs.FontMerge
        ${WIPE} Test.Configure.* ${WFLAGS}
        ${WIPE} Test.FontMerge ${WFLAGS}
        @echo ${COMPONENT}: cleaned

clean_all:
   -Destroy ${OBJS} abs.!RunImage ${INSTDIR}.!Configure.!Boot \
         ${INSTDIR}.!Configure.!Help ${INSTDIR}.!Configure.!Run \
         ${INSTDIR}.!Configure.!RunImage ${INSTDIR}.!Configure.Messages \
         ${INSTDIR}.!Configure.Sprites ${INSTDIR}.!Configure.Sprites22 \
         ${INSTDIR}.!Configure.Templates \
         ${INSTDIR}.!Configure.tile_1

asms: ${ASMS}

#
# Static dependencies:
#
abs.!RunImage: ${OBJS} ${RLIB} ${CLIB}
        ${LD} -o $@ ${OBJS} ${RLIB} ${CLIB}
        ${SQUEEZE} $@

abs.FontMerge: o.FontMerge ${CLIB}
        ${LD} -o $@ o.FontMerge ${CLIB}
        ${SQUEEZE} $@

#---------------------------------------------------------------------------
# Dynamic dependencies:
o.FontMerge:	c.FontMerge
o.FontMerge:	h.kernel
o.FontMerge:	C:h.swis
o.apps:	c.apps
o.apps:	h.kernel
o.apps:	C:h.swis
o.apps:	C:h.wimp
o.apps:	C:h.os
o.apps:	C:h.sprite
o.apps:	C:h.wimpt
o.apps:	C:h.werr
o.apps:	C:h.win
o.apps:	C:h.event
o.apps:	C:h.menu
o.apps:	C:h.baricon
o.apps:	C:h.template
o.apps:	C:h.msgs
o.apps:	C:h.menu
o.apps:	C:h.res
o.apps:	C:h.resspr
o.apps:	C:h.dbox
o.apps:	h.configure
o.apps:	h.apps
o.apps:	h.cmos
o.cmos:	c.cmos
o.cmos:	h.kernel
o.cmos:	C:h.swis
o.cmos:	h.cmos
o.configfile:	c.configfile
o.configfile:	C:h.swis
o.configfile:	C:h.kernel
o.configfile:	C:h.wimpt
o.configfile:	C:h.wimp
o.configfile:	C:h.os
o.configfile:	C:h.sprite
o.configfile:	h.ConfigFile
o.configure:	c.configure
o.configure:	h.kernel
o.configure:	C:h.swis
o.configure:	C:h.wimp
o.configure:	C:h.os
o.configure:	C:h.sprite
o.configure:	C:h.wimpt
o.configure:	C:h.werr
o.configure:	C:h.win
o.configure:	C:h.event
o.configure:	C:h.menu
o.configure:	C:h.baricon
o.configure:	C:h.template
o.configure:	C:h.msgs
o.configure:	C:h.menu
o.configure:	C:h.res
o.configure:	C:h.resspr
o.configure:	C:h.dbox
o.configure:	C:h.alarm
o.configure:	C:h.saveas
o.configure:	C:h.xfersend
o.configure:	C:h.help
o.configure:	h.ftrace
o.configure:	h.configure
o.configure:	h.cmos
o.configure:	h.harddiscs
o.configure:	h.floppies
o.configure:	h.inetsetup
o.configure:	h.econet
o.configure:	h.printer
o.configure:	h.screen
o.configure:	h.wimpflags
o.configure:	h.apps
o.configure:	h.sound
o.configure:	h.mouse
o.configure:	h.keyboard
o.configure:	h.memory
o.configure:	h.fonts
o.configure:	h.system
o.configure:	h.lock
o.configure:	h.filer
o.econet:	c.econet
o.econet:	h.inetsetup
o.inetsetup:	c.inetsetup
o.inetsetup:	C:h.swis
o.inetsetup:	C:h.kernel
o.inetsetup:	h.inetsetup
o.inetsetup:	C:h.msgs
o.filer:	c.filer
o.filer:	h.kernel
o.filer:	C:h.swis
o.filer:	C:h.wimp
o.filer:	C:h.os
o.filer:	C:h.sprite
o.filer:	C:h.wimpt
o.filer:	C:h.werr
o.filer:	C:h.win
o.filer:	C:h.event
o.filer:	C:h.menu
o.filer:	C:h.baricon
o.filer:	C:h.template
o.filer:	C:h.msgs
o.filer:	C:h.menu
o.filer:	C:h.res
o.filer:	C:h.resspr
o.filer:	C:h.dbox
o.filer:	h.configure
o.filer:	h.filer
o.filer:	h.cmos
o.floppies:	c.floppies
o.floppies:	h.kernel
o.floppies:	C:h.swis
o.floppies:	C:h.wimp
o.floppies:	C:h.os
o.floppies:	C:h.sprite
o.floppies:	C:h.wimpt
o.floppies:	C:h.werr
o.floppies:	C:h.win
o.floppies:	C:h.event
o.floppies:	C:h.menu
o.floppies:	C:h.baricon
o.floppies:	C:h.template
o.floppies:	C:h.msgs
o.floppies:	C:h.menu
o.floppies:	C:h.res
o.floppies:	C:h.resspr
o.floppies:	C:h.dbox
o.floppies:	C:h.visdelay
o.floppies:	h.configure
o.floppies:	h.floppies
o.floppies:	h.cmos
o.floppies:	h.filer
o.fonts:	c.fonts
o.fonts:	h.kernel
o.fonts:	C:h.swis
o.fonts:	C:h.wimp
o.fonts:	C:h.os
o.fonts:	C:h.sprite
o.fonts:	C:h.wimpt
o.fonts:	C:h.werr
o.fonts:	C:h.win
o.fonts:	C:h.event
o.fonts:	C:h.menu
o.fonts:	C:h.baricon
o.fonts:	C:h.template
o.fonts:	C:h.msgs
o.fonts:	C:h.menu
o.fonts:	C:h.res
o.fonts:	C:h.resspr
o.fonts:	C:h.dbox
o.fonts:	h.configure
o.fonts:	h.ConfigFile
o.fonts:	h.fonts
o.fonts:	h.cmos
o.harddiscs:	c.harddiscs
o.harddiscs:	h.kernel
o.harddiscs:	C:h.swis
o.harddiscs:	C:h.wimp
o.harddiscs:	C:h.os
o.harddiscs:	C:h.sprite
o.harddiscs:	C:h.wimpt
o.harddiscs:	C:h.werr
o.harddiscs:	C:h.win
o.harddiscs:	C:h.event
o.harddiscs:	C:h.menu
o.harddiscs:	C:h.baricon
o.harddiscs:	C:h.template
o.harddiscs:	C:h.msgs
o.harddiscs:	C:h.menu
o.harddiscs:	C:h.res
o.harddiscs:	C:h.resspr
o.harddiscs:	C:h.dbox
o.harddiscs:	C:h.visdelay
o.harddiscs:	h.configure
o.harddiscs:	h.HardDiscs
o.harddiscs:	h.cmos
o.harddiscs:	h.filer
o.keyboard:	c.keyboard
o.keyboard:	h.kernel
o.keyboard:	C:h.swis
o.keyboard:	C:h.wimp
o.keyboard:	C:h.os
o.keyboard:	C:h.sprite
o.keyboard:	C:h.wimpt
o.keyboard:	C:h.werr
o.keyboard:	C:h.win
o.keyboard:	C:h.event
o.keyboard:	C:h.menu
o.keyboard:	C:h.baricon
o.keyboard:	C:h.template
o.keyboard:	C:h.msgs
o.keyboard:	C:h.menu
o.keyboard:	C:h.res
o.keyboard:	C:h.resspr
o.keyboard:	C:h.dbox
o.keyboard:	h.configure
o.keyboard:	h.keyboard
o.keyboard:	h.cmos
o.lock:	c.lock
o.lock:	h.kernel
o.lock:	C:h.swis
o.lock:	C:h.wimp
o.lock:	C:h.os
o.lock:	C:h.sprite
o.lock:	C:h.wimpt
o.lock:	C:h.werr
o.lock:	C:h.win
o.lock:	C:h.event
o.lock:	C:h.menu
o.lock:	C:h.baricon
o.lock:	C:h.template
o.lock:	C:h.msgs
o.lock:	C:h.msgtrans
o.lock:	C:h.menu
o.lock:	C:h.res
o.lock:	C:h.resspr
o.lock:	C:h.dbox
o.lock:	C:h.alarm
o.lock:	h.configure
o.lock:	h.lock
o.lock:	h.cmos
o.memory:	c.memory
o.memory:	h.kernel
o.memory:	C:h.swis
o.memory:	C:h.wimp
o.memory:	C:h.os
o.memory:	C:h.sprite
o.memory:	C:h.wimpt
o.memory:	C:h.werr
o.memory:	C:h.win
o.memory:	C:h.event
o.memory:	C:h.menu
o.memory:	C:h.baricon
o.memory:	C:h.template
o.memory:	C:h.msgs
o.memory:	C:h.menu
o.memory:	C:h.res
o.memory:	C:h.resspr
o.memory:	C:h.dbox
o.memory:	h.configure
o.memory:	h.configfile
o.memory:	h.memory
o.memory:	h.cmos
o.mouse:	c.mouse
o.mouse:	h.kernel
o.mouse:	C:h.swis
o.mouse:	C:h.wimp
o.mouse:	C:h.os
o.mouse:	C:h.sprite
o.mouse:	C:h.wimpt
o.mouse:	C:h.werr
o.mouse:	C:h.win
o.mouse:	C:h.event
o.mouse:	C:h.menu
o.mouse:	C:h.baricon
o.mouse:	C:h.template
o.mouse:	C:h.msgs
o.mouse:	C:h.menu
o.mouse:	C:h.res
o.mouse:	C:h.resspr
o.mouse:	C:h.dbox
o.mouse:	C:h.alarm
o.mouse:	C:h.visdelay
o.mouse:	C:h.help
o.mouse:	h.configure
o.mouse:	h.mouse
o.mouse:	h.cmos
o.printer:	c.printer
o.printer:	h.kernel
o.printer:	C:h.swis
o.printer:	C:h.wimp
o.printer:	C:h.os
o.printer:	C:h.sprite
o.printer:	C:h.wimpt
o.printer:	C:h.werr
o.printer:	C:h.win
o.printer:	C:h.event
o.printer:	C:h.menu
o.printer:	C:h.baricon
o.printer:	C:h.template
o.printer:	C:h.msgs
o.printer:	C:h.menu
o.printer:	C:h.res
o.printer:	C:h.resspr
o.printer:	C:h.dbox
o.printer:	h.configure
o.printer:	h.printer
o.printer:	h.cmos
o.screen:	c.screen
o.screen:	h.kernel
o.screen:	C:h.swis
o.screen:	C:h.wimp
o.screen:	C:h.os
o.screen:	C:h.sprite
o.screen:	C:h.wimpt
o.screen:	C:h.werr
o.screen:	C:h.win
o.screen:	C:h.event
o.screen:	C:h.menu
o.screen:	C:h.baricon
o.screen:	C:h.template
o.screen:	C:h.msgs
o.screen:	C:h.menu
o.screen:	C:h.res
o.screen:	C:h.resspr
o.screen:	C:h.dbox
o.screen:	C:h.help
o.screen:	C:h.werr
o.screen:	C:h.visdelay
o.screen:	h.configure
o.screen:	h.ConfigFile
o.screen:	h.screen
o.screen:	h.cmos
o.sound:	c.sound
o.sound:	h.kernel
o.sound:	C:h.swis
o.sound:	C:h.wimp
o.sound:	C:h.os
o.sound:	C:h.sprite
o.sound:	C:h.wimpt
o.sound:	C:h.werr
o.sound:	C:h.win
o.sound:	C:h.event
o.sound:	C:h.menu
o.sound:	C:h.baricon
o.sound:	C:h.template
o.sound:	C:h.msgs
o.sound:	C:h.menu
o.sound:	C:h.res
o.sound:	C:h.resspr
o.sound:	C:h.dbox
o.sound:	C:h.help
o.sound:	C:h.visdelay
o.sound:	h.configure
o.sound:	h.sound
o.sound:	h.cmos
o.system:	c.system
o.system:	h.kernel
o.system:	C:h.swis
o.system:	C:h.wimp
o.system:	C:h.os
o.system:	C:h.sprite
o.system:	C:h.wimpt
o.system:	C:h.werr
o.system:	C:h.win
o.system:	C:h.event
o.system:	C:h.menu
o.system:	C:h.baricon
o.system:	C:h.template
o.system:	C:h.msgs
o.system:	C:h.menu
o.system:	C:h.res
o.system:	C:h.resspr
o.system:	C:h.dbox
o.system:	C:h.visdelay
o.system:	h.ftrace
o.system:	h.configure
o.system:	h.system
o.system:	h.version
o.version:	c.version
o.version:	h.kernel
o.version:	C:h.msgs
o.version:	C:h.os
o.version:	C:h.swis
o.version:	C:h.werr
o.version:	h.version
o.wimpflags:	c.wimpflags
o.wimpflags:	h.kernel
o.wimpflags:	C:h.swis
o.wimpflags:	C:h.wimp
o.wimpflags:	C:h.os
o.wimpflags:	C:h.sprite
o.wimpflags:	C:h.wimpt
o.wimpflags:	C:h.werr
o.wimpflags:	C:h.win
o.wimpflags:	C:h.event
o.wimpflags:	C:h.menu
o.wimpflags:	C:h.baricon
o.wimpflags:	C:h.template
o.wimpflags:	C:h.msgs
o.wimpflags:	C:h.menu
o.wimpflags:	C:h.res
o.wimpflags:	C:h.resspr
o.wimpflags:	C:h.dbox
o.wimpflags:	h.configure
o.wimpflags:	h.ConfigFile
o.wimpflags:	h.wimpflags
o.wimpflags:	h.cmos
