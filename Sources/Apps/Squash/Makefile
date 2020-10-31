# Makefile for !Squash
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name   Description
# ----       ----   -----------
# 25-Oct-94  AMcC   Updated for Black build
#

#
# Program specific options:
#
COMPONENT  = Squash
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

AFLAGS  = ${THROWBACK} -depend !Depend -nocache -stamp -quit
CFLAGS  = ${THROWBACK} -c -depend !Depend -fah ${INCLUDES} ${DFLAGS}
CPFLAGS = ~cfr~v
WFLAGS  = ~c~v

#
# Libraries
#
CLIB = CLIB:o.stubs
RLIB = RISC_OSLib:o.risc_oslib

#
# Include files
#
INCLUDES = -IC:

DFLAGS   = 

FILES = \
 ${RDIR}.!Boot\
 ${LDIR}.!Help\
 ${LDIR}.!Run\
 ${LDIR}.!Sprites\
 ${LDIR}.!Sprites22\
 ${LDIR}.Messages\
 ${LDIR}.Templates\
 abs.!RunImage\
 abs.Squash

OBJS = squash.o main.o debug.o

#
# Rule patterns
#
.c.o:;      ${CC} ${CFLAGS} -o $@ $<

#
# Main rules:
#
# Application
#
all: ${FILES}
        @echo ${COMPONENT}: Application built (Disc)

install: ${FILES}
        ${MKDIR} ${INSTDIR}
        ${CP} ${RDIR}.!Boot      ${INSTDIR}.!Boot      ${CPFLAGS}
        ${CP} ${LDIR}.!Help      ${INSTDIR}.!Help      ${CPFLAGS}
        ${CP} ${LDIR}.!Run       ${INSTDIR}.!Run       ${CPFLAGS}
        ${CP} abs.!RunImage      ${INSTDIR}.!RunImage  ${CPFLAGS}
        ${CP} ${LDIR}.!Sprites   ${INSTDIR}.!Sprites   ${CPFLAGS}
        ${CP} ${LDIR}.!Sprites22 ${INSTDIR}.!Sprites22 ${CPFLAGS}
        ${CP} ${LDIR}.Messages   ${INSTDIR}.Messages   ${CPFLAGS}
        ${CP} abs.Squash         ${INSTDIR}.Squash     ${CPFLAGS}
        ${CP} ${LDIR}.Templates  ${INSTDIR}.Templates  ${CPFLAGS}
        Access ${INSTDIR} /r
        Access ${INSTDIR}.* lr/r
        @echo ${COMPONENT}: Application installed (Disc)

clean:
        ${WIPE} o.* ${WFLAGS}
        ${RM} abs.!RunImage
        ${RM} abs.Squash
        @echo ${COMPONENT}: cleaned

#
# Static dependencies:
#
abs.!RunImage: ${OBJS} ${RLIB} ${CLIB}
        ${LD} -o $@ ${OBJS} ${RLIB} ${CLIB}
        ${SQUEEZE} $@

abs.Squash: util.o
        ${LD} -o $@ util.o ${CLIB}
        ${SQUEEZE} $@

util.o: squash.c squash.h
        ${CC} ${CFLAGS} -o $@ -DUTILITY squash.c

#---------------------------------------------------------------------------
# Dynamic dependencies:
o.squash:	c.squash
o.squash:	C:h.kernel
o.squash:	C:h.swis
o.squash:	C:h.visdelay
o.squash:	h.squash
o.squash:	h.debug
o.squash:	C:h.flex
o.main:	c.main
o.main:	C:h.wimpt
o.main:	C:h.wimp
o.main:	C:h.os
o.main:	C:h.kernel
o.main:	C:h.sprite
o.main:	C:h.res
o.main:	C:h.resspr
o.main:	C:h.dbox
o.main:	C:h.menu
o.main:	C:h.baricon
o.main:	C:h.event
o.main:	C:h.win
o.main:	C:h.werr
o.main:	C:h.template
o.main:	C:h.xferrecv
o.main:	C:h.xfersend
o.main:	C:h.swis
o.main:	C:h.msgs
o.main:	C:h.flex
o.main:	C:h.saveas
o.main:	C:h.visdelay
o.main:	C:h.kernel
o.main:	h.squash
o.main:	h.debug
o.debug:	c.debug
o.debug:	C:h.kernel
o.debug:	h.debug
o.util:	c.squash
o.util:	C:h.kernel
o.util:	C:h.swis
o.util:	h.squash
o.util:	h.debug
