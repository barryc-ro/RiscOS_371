# Makefile for Scrap
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date           Name   Description
# ----           ----   -----------
# 03-Jul-96      KJB    Derived from Scrap makefile
#

#
# Program specific options:
#
COMPONENT  = InetSetup
APP        = !${COMPONENT}
RDIR       = Resources
LDIR       = ${RDIR}.${LOCALE}
INSTDIR    = ${INSTDIR}.${APP}

# Generic options:
#
MKDIR   = cdir
ATTR    = -attr
CP      = copy
RM      = remove
WIPE    = -wipe

CPFLAGS = ~cfr~v
WFLAGS  = ~c~v

FILES=\
 ${LDIR}.!Help\
 ${RDIR}.!Boot\
 ${RDIR}.!Run\
 ${RDIR}.!RunImage\
 ${RDIR}.!Sprites\
 ${RDIR}.!Sprites22\
 ${LDIR}.Blanks.Routes\
 ${LDIR}.Blanks.SetUpNet\
 ${LDIR}.Blanks.User\
 ${LDIR}.Messages\
 ${LDIR}.Res\
 ${RDIR}.Sprites\
 ${RDIR}.Sprites22

#
# Main rules:
#
all: ${FILES}
        @echo ${COMPONENT}: All built (Disc)

install: ${FILES}
        ${MKDIR} ${INSTDIR}
        |
        ${CP} ${LDIR}.!Help      ${INSTDIR}.!Help      ${CPFLAGS}
        ${CP} ${RDIR}.!Boot       ${INSTDIR}.!Boot     ${CPFLAGS}
        ${CP} ${RDIR}.!Run       ${INSTDIR}.!Run       ${CPFLAGS}
        ${CP} ${RDIR}.!RunImage  ${INSTDIR}.!RunImage  ${CPFLAGS}
        ${CP} ${RDIR}.!Sprites   ${INSTDIR}.!Sprites   ${CPFLAGS}
        ${CP} ${RDIR}.!Sprites22 ${INSTDIR}.!Sprites22 ${CPFLAGS}
        ${CP} ${RDIR}.AutoSense  ${INSTDIR}.AutoSense  ${CPFLAGS}
        ${CP} ${LDIR}.Blanks     ${INSTDIR}.Blanks     ${CPFLAGS}
        ${CP} ${LDIR}.Messages   ${INSTDIR}.Messages   ${CPFLAGS}
        ${CP} ${LDIR}.Res        ${INSTDIR}.Res        ${CPFLAGS}
        ${CP} ${RDIR}.Sprites    ${INSTDIR}.Sprites    ${CPFLAGS}
        ${CP} ${RDIR}.Sprites22  ${INSTDIR}.Sprites22  ${CPFLAGS}
        |
        ${ATTR} -directories +wr -ww ${INSTDIR}
        ${ATTR} -files +or +ow +wr -ww ${INSTDIR}
        |
        @echo ${COMPONENT}: All installed (Disc)

clean:
        @echo ${COMPONENT}: cleaned

#---------------------------------------------------------------------------
# Dynamic dependencies:
