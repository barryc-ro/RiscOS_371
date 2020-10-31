# Makefile for Flasher
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name   Description
# ----       ----   -----------
# 06-Nov-94  AMcC   Updated for Black build
#

#
# Program specific options:
#
COMPONENT  = Flasher
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
SQUISH  = squish
WIPE    = -wipe

CPFLAGS = ~cfr~v
SQFLAGS = -nolist
WFLAGS  = ~c~v

FILES =\
 $(RDIR).!Boot\
 $(RDIR).!Help.!Help\
 $(RDIR).!Help.!Run\
 $(LDIR).!Help.Messages\
 $(LDIR).!Help.Templates\
 $(RDIR).!Run\
 $(RDIR).!RunImage\
 $(LDIR).!Sprites\
 $(LDIR).FlasherFrm\
 $(LDIR).HelpText\
 $(LDIR).Messages


#
# Main rules:
#
all: ${FILES}
        @echo ${COMPONENT}: Application built (Disc)

install: ${FILES}
        ${MKDIR} ${INSTDIR}
        ${MKDIR} ${INSTDIR}.!Help
        |
        ${CP} ${RDIR}.!Boot            ${INSTDIR}.!Boot           ${CPFLAGS}
        ${CP} ${RDIR}.!Help.!Help      ${INSTDIR}.!Help.!Help     ${CPFLAGS}
        ${CP} ${RDIR}.!Help.!Run       ${INSTDIR}.!Help.!Run      ${CPFLAGS}
        ${CP} ${LDIR}.!Help.Messages   ${INSTDIR}.!Help.Messages  ${CPFLAGS}
        ${CP} ${LDIR}.!Help.Templates  ${INSTDIR}.!Help.Templates ${CPFLAGS}
        ${CP} ${RDIR}.!Run             ${INSTDIR}.!Run            ${CPFLAGS}
        ${CP} ${RDIR}.!RunImage        ${INSTDIR}.!RunImage       ${CPFLAGS}
        ${CP} ${LDIR}.!Sprites         ${INSTDIR}.!Sprites        ${CPFLAGS}
        ${CP} ${LDIR}.FlasherFrm       ${INSTDIR}.FlasherFrm      ${CPFLAGS}
        ${CP} ${LDIR}.HelpText         ${INSTDIR}.HelpText        ${CPFLAGS}
        ${CP} ${LDIR}.Messages         ${INSTDIR}.Messages        ${CPFLAGS}
        |
        -attr -directories +wr ${INSTDIR}
        -attr -files +or +ow +wr -ww ${INSTDIR}
        |
        @echo ${COMPONENT}: Application installed (Disc)

clean:
        ${RM} ${RDIR}.!RunImage
        ${RM} ${RDIR}.!Help.!Help
        @echo ${COMPONENT}: cleaned

#
# Static dependencies:
#
${RDIR}.!RunImage: bas.!RunImage
        ${CP} bas.!RunImage $@ ${CPFLAGS}

${RDIR}.!Help.!Help: bas.!Help
        ${CP} bas.!Help $@ ${CPFLAGS}

#---------------------------------------------------------------------------
# Dynamic dependencies:
