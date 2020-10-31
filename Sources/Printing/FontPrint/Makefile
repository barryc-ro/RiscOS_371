# Makefile for FontPrint 
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name         Description
# ----       ----         -----------
# 07-Nov-94  AMcC         Updated for Black build system
#

#
# Component specific options:
#
COMPONENT = FontPrint
APP       = !${COMPONENT}
RDIR      = Resources
LDIR      = ${RDIR}.${LOCALE}
INSTDIR   = ${INSTDIR}.${APP}

#
# Generic options:
#
CC      = cc
LD      = link
CP      = copy
RM      = remove 
MKDIR   = cdir
SQUEEZE = squeeze
OBJASM  = objasm
WIPE    = -wipe

AFLAGS  = -depend !Depend -stamp -quit -closeexec
CFLAGS  = -depend !Depend -c -ffah -wp ${INCLUDES} ${DFLAGS} ${THROWBACK}
CPFLAGS = ~cfr~v
WFLAGS  = ~c~v

#
# Include files:
#
INCLUDES = -IC:

#
# Libraries:
#
CLIB = CLib:o.Stubs

OBJS =\
 fonts.o\
 icons.o\
 main.o\
 menu.o\
 menuwrap.o\
 message.o\
 panes.o\
 swicall.o\
 debug.o

FILES =\
 ${LDIR}.!Help\
 ${LDIR}.!Run\
 ${RDIR}.!RunImage\
 ${LDIR}.!Sprites\
 ${LDIR}.!Sprites22\
 ${LDIR}.Messages\
 ${LDIR}.Templates

#
# Rule patterns:
#
.c.o:;  ${CC} ${CFLAGS} -o $@ $<
.s.o:;  ${OBJASM} ${AFLAGS} -from $< -to $@

#
# Build rules:
#
all: ${FILES}
        @echo ${COMPONENT}: all build complete

install: ${FILES}
        ${MKDIR} ${INSTDIR}
        ${CP} ${LDIR}.!Help       ${INSTDIR}.!Help      ${CPFLAGS}
        ${CP} ${LDIR}.!Run        ${INSTDIR}.!Run       ${CPFLAGS}
        ${CP} ${RDIR}.!RunImage   ${INSTDIR}.!RunImage  ${CPFLAGS}
        ${CP} ${LDIR}.!Sprites    ${INSTDIR}.!Sprites   ${CPFLAGS}
        ${CP} ${LDIR}.!Sprites22  ${INSTDIR}.!Sprites22 ${CPFLAGS}
        ${CP} ${LDIR}.Messages    ${INSTDIR}.Messages   ${CPFLAGS}
        ${CP} ${LDIR}.Templates   ${INSTDIR}.Templates  ${CPFLAGS}
        Access ${INSTDIR} /r
        Access ${INSTDIR}.* lr/r
        @echo ${COMPONENT}: installed

clean:
       ${WIPE} o.* ${WFLAGS}
       ${RM} ${RDIR}.!RunImage
       @echo ${COMPONENT}: cleaned

${RDIR}.!RunImage: ${OBJS} ${CLIB}
        ${LD} -o $@ ${OBJS} ${CLIB}
        SetType $@ Absolute
        ${SQUEEZE} $@

# Dynamic dependencies:
o.fonts:	c.fonts
o.fonts:	h.main
o.fonts:	h.swicall
o.fonts:	C:h.kernel
o.fonts:	C:h.swis
o.fonts:	h.menuwrap
o.fonts:	h.message
o.fonts:	C:h.kernel
o.fonts:	h.fonts
o.fonts:	h.icons
o.icons:	c.icons
o.icons:	h.main
o.icons:	h.swicall
o.icons:	C:h.kernel
o.icons:	C:h.swis
o.icons:	h.menuwrap
o.icons:	h.message
o.icons:	C:h.kernel
o.icons:	h.fonts
o.icons:	h.icons
o.icons:	h.panes
o.icons:	h.debug
o.main:	c.main
o.main:	h.main
o.main:	h.swicall
o.main:	C:h.kernel
o.main:	C:h.swis
o.main:	h.menuwrap
o.main:	h.message
o.main:	C:h.kernel
o.main:	h.menu
o.main:	h.panes
o.main:	h.fonts
o.main:	h.icons
o.menu:	c.menu
o.menu:	h.main
o.menu:	h.swicall
o.menu:	C:h.kernel
o.menu:	C:h.swis
o.menu:	h.menuwrap
o.menu:	h.message
o.menu:	C:h.kernel
o.menu:	h.menu
o.menu:	h.fonts
o.menu:	h.panes
o.menu:	h.icons
o.menuwrap:	c.menuwrap
o.menuwrap:	h.menuwrap
o.message:	c.message
o.message:	h.message
o.message:	C:h.kernel
o.message:	h.swicall
o.message:	C:h.kernel
o.message:	C:h.swis
o.panes:	c.panes
o.panes:	h.main
o.panes:	h.swicall
o.panes:	C:h.kernel
o.panes:	C:h.swis
o.panes:	h.menuwrap
o.panes:	h.message
o.panes:	C:h.kernel
o.panes:	h.panes
o.panes:	h.fonts
o.panes:	h.icons
o.swicall: s.swicall
o.debug:	c.debug
o.debug:	h.debug
o.debug:	h.swicall
o.debug:	C:h.kernel
o.debug:	C:h.swis
