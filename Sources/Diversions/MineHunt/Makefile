# Makefile for MineHunt
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
COMPONENT  = MineHunt
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
 ${LDIR}.!Run\
 ${RDIR}.!RunImage\
 ${LDIR}.!Sprites\
 ${LDIR}.!Sprites22\
 ${LDIR}.Messages\
 ${RDIR}.Parts\
 ${RDIR}.Sounds.Applause\
 ${RDIR}.Sounds.RealMine\
 ${RDIR}.Sounds.Shame\
 ${RDIR}.Sounds.Spiffing\
 ${RDIR}.Sounds.TryAgain\
 ${RDIR}.Sounds.YouDidIt\
 ${RDIR}.Sprites\
 ${LDIR}.Templates

#
# Main rules:
#
all: ${FILES}
        @echo ${COMPONENT}: Application built (Disc)

install: ${FILES}
        ${MKDIR} ${INSTDIR}
        ${CP} ${LDIR}.!Help      ${INSTDIR}.!Help      ${CPFLAGS}
        ${CP} ${LDIR}.!Run       ${INSTDIR}.!Run       ${CPFLAGS}
        ${CP} ${RDIR}.!RunImage  ${INSTDIR}.!RunImage  ${CPFLAGS}
        ${CP} ${LDIR}.!Sprites   ${INSTDIR}.!Sprites   ${CPFLAGS}
        ${CP} ${LDIR}.!Sprites22 ${INSTDIR}.!Sprites22 ${CPFLAGS}
        ${CP} ${LDIR}.Messages   ${INSTDIR}.Messages   ${CPFLAGS}
        ${CP} ${RDIR}.Parts      ${INSTDIR}.Parts      ${CPFLAGS}
        ${CP} ${RDIR}.Sprites    ${INSTDIR}.Sprites    ${CPFLAGS}
        ${CP} ${LDIR}.Templates  ${INSTDIR}.Templates  ${CPFLAGS}
        |
        ${MKDIR} ${INSTDIR}.Sounds
        ${CP} ${RDIR}.Sounds.Applause  ${INSTDIR}.Sounds.Applause ${CPFLAGS}
        ${CP} ${RDIR}.Sounds.RealMine  ${INSTDIR}.Sounds.RealMine ${CPFLAGS}
        ${CP} ${RDIR}.Sounds.Shame     ${INSTDIR}.Sounds.Shame    ${CPFLAGS}
        ${CP} ${RDIR}.Sounds.Spiffing  ${INSTDIR}.Sounds.Spiffing ${CPFLAGS}
        ${CP} ${RDIR}.Sounds.TryAgain  ${INSTDIR}.Sounds.TryAgain ${CPFLAGS}
        ${CP} ${RDIR}.Sounds.YouDidIt  ${INSTDIR}.Sounds.YouDidIt ${CPFLAGS}
        |
        -attr -directories +wr ${INSTDIR}
        -attr -files +or +ow +wr -ww ${INSTDIR}
        |
        @echo ${COMPONENT}: Application installed (Disc)

clean:
        @echo ${COMPONENT}: cleaned

#---------------------------------------------------------------------------
# Dynamic dependencies:
