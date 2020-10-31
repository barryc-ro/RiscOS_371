# Makefile for Meteors
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
COMPONENT  = Meteors
APP        = !${COMPONENT}
RDIR       = Resources
LDIR       = ${RDIR}.${LOCALE}
INSTDIR    = ${INSTDIR}.${APP}

# Generic options:
#
AS      = aasm
MKDIR   = cdir
CP      = copy
RM      = remove
SQUISH  = squish
WIPE    = -wipe

AFLAGS  = ${THROWBACK} -depend !Depend -nocache -stamp -quit -module
CPFLAGS = ~cfr~v
SQFLAGS = -nolist
WFLAGS  = ~c~v

FILES =\
 ${LDIR}.!Help\
 ${LDIR}.!Run\
 ${LDIR}.!Sprites\
 ${RDIR}.Sprites\
 ${LDIR}.Templates\
 rm.!RunImage

#
# Main rules:
#
all: ${FILES}
        @echo ${COMPONENT}: Application built (Disc}

install: ${FILES}
        ${MKDIR} ${INSTDIR}
        |
        ${CP} ${LDIR}.!Help      ${INSTDIR}.!Help      ${CPFLAGS}
        ${CP} ${LDIR}.!Run       ${INSTDIR}.!Run       ${CPFLAGS}
        ${CP} rm.!RunImage       ${INSTDIR}.!RunImage  ${CPFLAGS}
        ${CP} ${LDIR}.!Sprites   ${INSTDIR}.!Sprites   ${CPFLAGS}
        ${CP} ${RDIR}.Sprites    ${INSTDIR}.Sprites    ${CPFLAGS}
        ${CP} ${LDIR}.Templates  ${INSTDIR}.Templates  ${CPFLAGS}
        |
        Access ${INSTDIR} /r
        Access ${INSTDIR}.* WR/r
        |
        @echo ${COMPONENT}: Application installed {Disc}

clean:
        ${RM} rm.!RunImage
        @echo ${COMPONENT}: cleaned

#
# Static dependencies:
#
rm.!RunImage: s.Meteors
        ${AS} ${AFLAGS} -from s.Meteors -to $@

#
# Following rule may be used if required to regenerate the shapes -
# it requires user intervention...
#
s.MetShapes:
         bas.GenSrc
         SetType $@ FFF

#---------------------------------------------------------------------------
# Dynamic dependencies:
rm.!RunImage: Hdr:ListOpts
rm.!RunImage: Hdr:Macros
rm.!RunImage: Hdr:System
rm.!RunImage: Hdr:SWIs
rm.!RunImage: Hdr:CPU.Generic26
rm.!RunImage: Hdr:IO.GenericIO
rm.!RunImage: Hdr:RISCOS
rm.!RunImage: Hdr:ModHand
rm.!RunImage: Hdr:Services
rm.!RunImage: Hdr:FSNumbers
rm.!RunImage: Hdr:NewErrors
rm.!RunImage: Hdr:Wimp
rm.!RunImage: Hdr:Messages
rm.!RunImage: Hdr:VduExt
rm.!RunImage: Hdr:ColourTran
rm.!RunImage: Hdr:Sprite
rm.!RunImage: Hdr:Font
rm.!RunImage: Hdr:PublicWS
rm.!RunImage: Hdr:NDRDebug
rm.!RunImage: s.Constants
rm.!RunImage: s.Macros
rm.!RunImage: s.MetShapes
