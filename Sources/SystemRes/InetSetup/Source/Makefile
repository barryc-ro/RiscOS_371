# Makefile for !InetSetup
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name   Description
# ----       ----   -----------
# 08-Oct-96  KJB    Created
#

#
# Program specific options:
#
COMPONENT  = InetSetup
APP        = !${COMPONENT}
RDIR       = Resources
LDIR       = ${RDIR}.${LOCALE}
INSTDIR    = ${INSTDIR}.${APP}

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

AFLAGS  = ${THROWBACK} -depend !Depend -stamp -quit
CFLAGS  = ${THROWBACK} -c -depend !Depend -ff -Wp ${INCLUDES} ${DFLAGS}
CPFLAGS = ~cfr~v
WFLAGS  = ~c~v

#
# Libraries
#
CLIB = CLIB:o.stubs
OSLIB = OSLib:o.OSLib
ILIB = TCPIPLibs:o.inetlib

#
# Include files
#
INCLUDES = -IOS:,C:,TCPIPLibs:

DFLAGS   = 

FILES = \
 ${RDIR}.!Boot\
 ${LDIR}.!Help\
 ${LDIR}.!Run\
 aif.!RunImage\
 ${LDIR}.!Sprites\
 ${LDIR}.!Sprites22\
 ${LDIR}.Blanks.Routes\
 ${LDIR}.Blanks.SetUpNet\
 ${LDIR}.Blanks.User\
 ${LDIR}.Messages\
 ${LDIR}.Res\
 ${LDIR}.Sprites\
 ${LDIR}.Sprites22

OBJS = AUN.o Detect.o Diagnose.o event.o FileUtils.o IfsDbox.o Load.o\
       Main.o ModUtils.o Save.o SmallDrag.o swis.o tbevent.o wimpevent.o\
       wimpmsg.o x.o

#
# Rule patterns
#
.c.o:;      ${CC} ${CFLAGS} -o $@ $<
.s.o:;      ${AS} ${AFLAGS} -o $@ $<

#
# Main rules:
#
# Application
#
all: ${FILES}
        @echo ${COMPONENT}: Application built (Disc)

install: ${FILES}
        ${MKDIR} ${INSTDIR}
        ${MKDIR} ${INSTDIR}.AutoSense
        ${CP} ${RDIR}.!Boot      ${INSTDIR}.!Boot      ${CPFLAGS}
        ${CP} ${LDIR}.!Help      ${INSTDIR}.!Help      ${CPFLAGS}
        ${CP} ${LDIR}.!Run       ${INSTDIR}.!Run       ${CPFLAGS}
        ${CP} aif.!RunImage      ${INSTDIR}.!RunImage  ${CPFLAGS}
        ${CP} ${LDIR}.!Sprites   ${INSTDIR}.!Sprites   ${CPFLAGS}
        ${CP} ${LDIR}.!Sprites22 ${INSTDIR}.!Sprites22 ${CPFLAGS}
        ${CP} ${LDIR}.Blanks     ${INSTDIR}.Blanks     ${CPFLAGS}
        ${CP} ${LDIR}.Messages   ${INSTDIR}.Messages   ${CPFLAGS}
        ${CP} ${LDIR}.Res        ${INSTDIR}.Res        ${CPFLAGS}
        ${CP} ${LDIR}.Sprites    ${INSTDIR}.Sprites    ${CPFLAGS}
        ${CP} ${LDIR}.Sprites22  ${INSTDIR}.Sprites22  ${CPFLAGS}
        Access ${INSTDIR} /r
        Access ${INSTDIR}.* lr/r
        Access ${INSTDIR}.Blanks.* wr/r
        @echo ${COMPONENT}: Application installed (Disc)

clean:
        ${WIPE} o.* ${WFLAGS}
        ${RM} aif.!RunImage
        @echo ${COMPONENT}: cleaned

#
# Static dependencies:
#
aif.!RunImage: ${OBJS} ${CLIB} ${OSLIB} ${ILIB}
        ${LD} -o $@ ${OBJS} ${CLIB} ${OSLIB} ${ILIB}
        ${SQUEEZE} $@


#---------------------------------------------------------------------------
# Dynamic dependencies:
o.event:	c.event
o.event:	OS:h.wimp
o.event:	OS:h.types
o.event:	OS:h.os
o.event:	OS:h.osspriteop
o.event:	OS:h.font
o.event:	OS:h.toolbox
o.event:	OS:h.messagetrans
o.event:	OS:h.tbevent
o.event:	OS:h.event
o.event:	OS:h.wimpevent
o.event:	OS:h.wimpmsg
o.ModUtils:	c.ModUtils
o.ModUtils:	C:h.kernel
o.ModUtils:	OS:h.osbyte
o.ModUtils:	OS:h.types
o.ModUtils:	OS:h.os
o.ModUtils:	OS:h.osmodule
o.ModUtils:	OS:h.osfile
o.ModUtils:	OS:h.fileswitch
o.ModUtils:	OS:h.osfind
o.ModUtils:	OS:h.osgbpb
o.ModUtils:	OS:h.osargs
o.ModUtils:	h.ModUtils
o.SmallDrag:	c.SmallDrag
o.SmallDrag:	OS:h.os
o.SmallDrag:	OS:h.types
o.SmallDrag:	OS:h.osbyte
o.SmallDrag:	OS:h.wimp
o.SmallDrag:	OS:h.osspriteop
o.SmallDrag:	OS:h.font
o.SmallDrag:	OS:h.draganobject
o.SmallDrag:	OS:h.toolbox
o.SmallDrag:	OS:h.messagetrans
o.SmallDrag:	OS:h.window
o.SmallDrag:	OS:h.keyboardshortcut
o.SmallDrag:	OS:h.gadget
o.SmallDrag:	OS:h.gadget
o.SmallDrag:	OS:h.draggable
o.SmallDrag:	h.ModUtils
o.SmallDrag:	OS:h.osmodule
o.SmallDrag:	h.Gadgets
o.swis: s.swis
o.tbevent:	c.tbevent
o.tbevent:	OS:h.messagetrans
o.tbevent:	OS:h.types
o.tbevent:	OS:h.os
o.tbevent:	OS:h.tbevent
o.tbevent:	OS:h.wimp
o.tbevent:	OS:h.osspriteop
o.tbevent:	OS:h.font
o.tbevent:	OS:h.toolbox
o.tbevent:	OS:h.event
o.tbevent:	OS:h.x
o.wimpevent:	c.wimpevent
o.wimpevent:	OS:h.os
o.wimpevent:	OS:h.types
o.wimpevent:	OS:h.wimpevent
o.wimpevent:	OS:h.wimp
o.wimpevent:	OS:h.osspriteop
o.wimpevent:	OS:h.font
o.wimpevent:	OS:h.toolbox
o.wimpevent:	OS:h.messagetrans
o.wimpevent:	OS:h.event
o.wimpevent:	OS:h.x
o.wimpmsg:	c.wimpmsg
o.wimpmsg:	OS:h.os
o.wimpmsg:	OS:h.types
o.wimpmsg:	OS:h.wimpmsg
o.wimpmsg:	OS:h.wimp
o.wimpmsg:	OS:h.osspriteop
o.wimpmsg:	OS:h.font
o.wimpmsg:	OS:h.toolbox
o.wimpmsg:	OS:h.messagetrans
o.wimpmsg:	OS:h.event
o.wimpmsg:	OS:h.x
o.x:	c.x
o.x:	C:h.kernel
o.x:	OS:h.macros
o.x:	OS:h.messagetrans
o.x:	OS:h.types
o.x:	OS:h.os
o.x:	OS:h.os
o.x:	OS:h.x
o.AUN:	c.AUN
o.AUN:	OS:h.osbyte
o.AUN:	OS:h.types
o.AUN:	OS:h.os
o.AUN:	OS:h.econet
o.AUN:	OS:h.hourglass
o.AUN:	OS:h.netfs
o.AUN:	OS:h.fileswitch
o.AUN:	OS:h.netprint
o.AUN:	OS:h.displayfield
o.AUN:	OS:h.toolbox
o.AUN:	OS:h.wimp
o.AUN:	OS:h.osspriteop
o.AUN:	OS:h.font
o.AUN:	OS:h.messagetrans
o.AUN:	OS:h.gadget
o.AUN:	OS:h.stringset
o.AUN:	h.event
o.AUN:	OS:h.writablefield
o.AUN:	h.AUN
o.AUN:	OS:h.toolbox
o.AUN:	h.ModUtils
o.AUN:	OS:h.osmodule
o.AUN:	h.Gadgets
o.AUN:	h.Main
o.Detect:	c.Detect
o.Detect:	C:h.kernel
o.Detect:	OS:h.osbyte
o.Detect:	OS:h.types
o.Detect:	OS:h.os
o.Detect:	OS:h.podule
o.Detect:	h.ModUtils
o.Detect:	OS:h.osmodule
o.Detect:	h.Load
o.Detect:	h.Main
o.Diagnose:	c.Diagnose
o.Diagnose:	OS:h.os
o.Diagnose:	OS:h.types
o.Diagnose:	OS:h.wimpspriteop
o.Diagnose:	OS:h.osspriteop
o.Diagnose:	OS:h.wimp
o.Diagnose:	OS:h.font
o.Diagnose:	OS:h.toolbox
o.Diagnose:	OS:h.messagetrans
o.Diagnose:	TCPIPLibs:h.netdb
o.Diagnose:	TCPIPLibs:sys.h.cdefs
o.Diagnose:	TCPIPLibs:h.inetlib
o.Diagnose:	TCPIPLibs:sys.h.types
o.Diagnose:	TCPIPLibs:sys.h.cdefs
o.Diagnose:	TCPIPLibs:machine.h.endian
o.Diagnose:	TCPIPLibs:machine.h.ansi
o.Diagnose:	TCPIPLibs:machine.h.types
o.Diagnose:	TCPIPLibs:netinet.h.in
o.Diagnose:	h.Main
o.Diagnose:	h.Load
o.Diagnose:	h.Diagnose
o.Diagnose:	h.Gadgets
o.FileUtils:	c.FileUtils
o.FileUtils:	OS:h.osfile
o.FileUtils:	OS:h.types
o.FileUtils:	OS:h.os
o.FileUtils:	OS:h.fileswitch
o.FileUtils:	OS:h.osfscontrol
o.FileUtils:	OS:h.wimp
o.FileUtils:	OS:h.osspriteop
o.FileUtils:	OS:h.font
o.FileUtils:	OS:h.taskmanager
o.FileUtils:	OS:h.toolbox
o.FileUtils:	OS:h.messagetrans
o.FileUtils:	OS:h.draggable
o.FileUtils:	OS:h.window
o.FileUtils:	OS:h.keyboardshortcut
o.FileUtils:	OS:h.gadget
o.FileUtils:	h.event
o.FileUtils:	h.FileUtils
o.FileUtils:	h.Main
o.IfsDbox:	c.IfsDbox
o.IfsDbox:	OS:h.window
o.IfsDbox:	OS:h.types
o.IfsDbox:	OS:h.toolbox
o.IfsDbox:	OS:h.os
o.IfsDbox:	OS:h.wimp
o.IfsDbox:	OS:h.osspriteop
o.IfsDbox:	OS:h.font
o.IfsDbox:	OS:h.messagetrans
o.IfsDbox:	OS:h.keyboardshortcut
o.IfsDbox:	OS:h.gadget
o.IfsDbox:	OS:h.gadget
o.IfsDbox:	OS:h.label
o.IfsDbox:	OS:h.optionbutton
o.IfsDbox:	OS:h.actionbutton
o.IfsDbox:	OS:h.writablefield
o.IfsDbox:	OS:h.radiobutton
o.IfsDbox:	h.event
o.IfsDbox:	h.Load
o.IfsDbox:	h.Gadgets
o.IfsDbox:	h.IfsDbox
o.IfsDbox:	h.Main
o.IfsDbox:	h.ModUtils
o.IfsDbox:	OS:h.osmodule
o.IfsDbox:	TCPIPLibs:sys.h.types
o.IfsDbox:	TCPIPLibs:sys.h.cdefs
o.IfsDbox:	TCPIPLibs:machine.h.endian
o.IfsDbox:	TCPIPLibs:machine.h.ansi
o.IfsDbox:	TCPIPLibs:machine.h.types
o.IfsDbox:	TCPIPLibs:netinet.h.in
o.IfsDbox:	TCPIPLibs:arpa.h.inet
o.IfsDbox:	TCPIPLibs:sys.h.cdefs
o.Load:	c.Load
o.Load:	OS:h.os
o.Load:	OS:h.types
o.Load:	OS:h.toolbox
o.Load:	OS:h.wimp
o.Load:	OS:h.osspriteop
o.Load:	OS:h.font
o.Load:	OS:h.messagetrans
o.Load:	h.ModUtils
o.Load:	OS:h.osmodule
o.Load:	h.Main
o.Load:	h.Load
o.Load:	h.Versions
o.Load:	h.IfsDbox
o.Load:	h.Gadgets
o.Load:	TCPIPLibs:sys.h.types
o.Load:	TCPIPLibs:sys.h.cdefs
o.Load:	TCPIPLibs:machine.h.endian
o.Load:	TCPIPLibs:machine.h.ansi
o.Load:	TCPIPLibs:machine.h.types
o.Load:	TCPIPLibs:netinet.h.in
o.Load:	TCPIPLibs:arpa.h.inet
o.Load:	TCPIPLibs:sys.h.cdefs
o.Main:	c.Main
o.Main:	C:h.kernel
o.Main:	C:h.swis
o.Main:	OS:h.osfile
o.Main:	OS:h.types
o.Main:	OS:h.os
o.Main:	OS:h.fileswitch
o.Main:	OS:h.osfscontrol
o.Main:	OS:h.toolbox
o.Main:	OS:h.wimp
o.Main:	OS:h.osspriteop
o.Main:	OS:h.font
o.Main:	OS:h.messagetrans
o.Main:	OS:h.window
o.Main:	OS:h.keyboardshortcut
o.Main:	OS:h.gadget
o.Main:	OS:h.actionbutton
o.Main:	OS:h.optionbutton
o.Main:	OS:h.stringset
o.Main:	OS:h.writablefield
o.Main:	OS:h.radiobutton
o.Main:	OS:h.button
o.Main:	OS:h.draggable
o.Main:	OS:h.wimpspriteop
o.Main:	OS:h.proginfo
o.Main:	OS:h.menu
o.Main:	h.event
o.Main:	h.Detect
o.Main:	h.Gadgets
o.Main:	h.Main
o.Main:	h.Load
o.Main:	h.Save
o.Main:	h.ModUtils
o.Main:	OS:h.osmodule
o.Main:	h.IfsDbox
o.Main:	h.FileUtils
o.Main:	h.AUN
o.Main:	OS:h.toolbox
o.Main:	h.SmallDrag
o.Main:	h.Versions
o.Save:	c.Save
o.Save:	C:h.kernel
o.Save:	OS:h.osbyte
o.Save:	OS:h.types
o.Save:	OS:h.os
o.Save:	OS:h.osfile
o.Save:	OS:h.fileswitch
o.Save:	OS:h.osfscontrol
o.Save:	OS:h.wimp
o.Save:	OS:h.osspriteop
o.Save:	OS:h.font
o.Save:	OS:h.hourglass
o.Save:	h.ModUtils
o.Save:	OS:h.osmodule
o.Save:	h.Save
o.Save:	h.Main
o.Save:	h.Load
o.Save:	h.AUN
o.Save:	OS:h.toolbox
o.Save:	OS:h.messagetrans
o.Save:	h.Versions
o.Save:	h.Gadgets
o.Save:	h.IfsDbox
o.Save:	h.Diagnose
o.Save:	TCPIPLibs:h.netdb
o.Save:	TCPIPLibs:sys.h.cdefs
