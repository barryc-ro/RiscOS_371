# Makefile for Patience
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name   Description
# ----       ----   -----------
# 07-Nov-94  AMcC   Updated for Black build
#

#
# Program specific options:
#
COMPONENT  = Patience
APP        = !${COMPONENT}
RDIR       = Resources
LDIR       = ${RDIR}.${LOCALE}
INSTDIR    = ${INSTDIR}.${APP}

#
# Generic options:
#
MKDIR   = cdir
CP      = copy
RM      = remove
WIPE    = -wipe

CPFLAGS = ~cfr~v
WFLAGS  = ~c~v

FILES =\
 ${LDIR}.!Help\
 ${RDIR}.!Run\
 ${RDIR}.!RunImage\
 ${RDIR}.!Sprites\
 ${RDIR}.!Sprites22\
 ${LDIR}.Messages\
 ${RDIR}.Sprites\
 ${RDIR}.Sprites22

#
# Main rules:
#
all: ${FILES}
        @echo ${COMPONENT}: Application built (Disc)

install: ${FILES}
        ${MKDIR} ${INSTDIR}
        |
        ${CP} ${LDIR}.!Help      ${INSTDIR}.!Help      ${CPFLAGS}
        ${CP} ${RDIR}.!Run       ${INSTDIR}.!Run       ${CPFLAGS}
        ${CP} ${RDIR}.!RunImage  ${INSTDIR}.!RunImage  ${CPFLAGS}
        ${CP} ${RDIR}.!Sprites   ${INSTDIR}.!Sprites   ${CPFLAGS}
        ${CP} ${RDIR}.!Sprites22 ${INSTDIR}.!Sprites22 ${CPFLAGS}
        ${CP} ${LDIR}.Messages   ${INSTDIR}.Messages   ${CPFLAGS}
        ${CP} ${RDIR}.Sprites    ${INSTDIR}.Sprites    ${CPFLAGS}
        ${CP} ${RDIR}.Sprites22  ${INSTDIR}.Sprites22  ${CPFLAGS}
        |
        Access ${INSTDIR} /r
        Access ${INSTDIR}.* WR/r
        |
        @echo ${COMPONENT}: Application installed (Disc)

clean:
        @echo ${COMPONENT}: cleaned

#---------------------------------------------------------------------------
# Dynamic dependencies:
