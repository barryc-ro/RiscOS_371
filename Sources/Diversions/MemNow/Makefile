# Makefile for MemNow
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name   Description
# ----       ----   -----------
# 05-Nov-94  AMcC   Updated for Black build
#

#
# Program specific options:
#
COMPONENT  = MemNow
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
 $(LDIR).!Help\
 $(RDIR).!Run\
 $(RDIR).!RunImage\
 $(LDIR).!Sprites\
 $(LDIR).Messages\
 $(LDIR).Templates

#
# Main rules:
#
all: ${FILES}
        @echo ${COMPONENT}: Application built (Disc}

install: ${FILES}
        ${MKDIR} ${INSTDIR}
        |
        ${CP} ${LDIR}.!Help      ${INSTDIR}.!Help      ${CPFLAGS}
        ${CP} ${RDIR}.!Run       ${INSTDIR}.!Run       ${CPFLAGS}
        ${CP} ${RDIR}.!RunImage  ${INSTDIR}.!RunImage  ${CPFLAGS}
        ${CP} ${LDIR}.!Sprites   ${INSTDIR}.!Sprites   ${CPFLAGS}
        ${CP} ${LDIR}.Messages   ${INSTDIR}.Messages   ${CPFLAGS}
        ${CP} ${LDIR}.Templates  ${INSTDIR}.Templates  ${CPFLAGS}
        |
        Access ${INSTDIR} /r
        Access ${INSTDIR}.* WR/r
        |
        @echo ${COMPONENT}: Application installed {Disc}

clean:
        ${RM} ${RDIR}.!RunImage
        @echo ${COMPONENT}: cleaned

#
# Static dependencies:
#
${RDIR}.!RunImage: bas.!RunImage
        ${SQUISH} ${SQFLAGS} -from bas.!RunImage -to $@

#---------------------------------------------------------------------------
# Dynamic dependencies:
