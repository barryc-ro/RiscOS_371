# Makefile for Font Manager
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name         Description
# ----       ----         -----------
# 25-May-94  AMcC         Created.
#

#
# Paths
#
EXP_HDR = <export$dir>

#
# Generic options:
#
MKDIR   = cdir
AS      = aasm
CP      = copy
RM      = remove
CCFLAGS = -c -depend !Depend -IC:
ASFLAGS = -depend !Depend -Stamp -quit -module -To $@ -From
CPFLAGS = ~cfr~v

#
# Program specific options:
#
COMPONENT = Fonts
SOURCE    = s.Fonts
TARGET    = rm.Fonts
EXPORTS   = ${EXP_HDR}.Font

#
# Generic rules:
#
rom: ${TARGET}
        @echo ${COMPONENT}: rom module built

export: ${EXPORTS}
        @echo ${COMPONENT}: export complete

install_rom: ${TARGET}
        ${CP} ${TARGET} ${INSTDIR}.${COMPONENT} ${CPFLAGS}
        @echo ${COMPONENT}: rom module installed

clean:
        ${RM} ${TARGET}
        @echo ${COMPONENT}: cleaned

resources:
        ${MKDIR} ${RESDIR}.${COMPONENT}
        ${CP} Resources.${LOCALE}.Messages  ${RESDIR}.${COMPONENT}.Messages  ${CPFLAGS}
        @echo ${COMPONENT}: resource files copied

${TARGET}: ${SOURCE}
        ${AS} ${ASFLAGS} ${SOURCE}

${EXP_HDR}.Font: hdr.Font
        ${CP} hdr.Font $@ ${CPFLAGS}

# Dynamic dependencies:
rm.Fonts: hdr:ListOpts
rm.Fonts: hdr:Macros
rm.Fonts: hdr:System
rm.Fonts: Hdr:SWIs
rm.Fonts: Hdr:CPU.Generic26
rm.Fonts: Hdr:IO.GenericIO
rm.Fonts: Hdr:RISCOS
rm.Fonts: hdr:CMOS
rm.Fonts: hdr:ModHand
rm.Fonts: hdr:Proc
rm.Fonts: hdr:Services
rm.Fonts: hdr:FSNumbers
rm.Fonts: Hdr:HighFSI
rm.Fonts: hdr:NewErrors
rm.Fonts: hdr:Variables
rm.Fonts: hdr:VduExt
rm.Fonts: hdr:Debug
rm.Fonts: hdr:PDriver
rm.Fonts: hdr:Font
rm.Fonts: hdr:Super
rm.Fonts: hdr:MsgTrans
rm.Fonts: hdr:Sprite
rm.Fonts: hdr:Draw
rm.Fonts: hdr:ColourTran
rm.Fonts: hdr:Wimp
rm.Fonts: hdr:WimpSpace
rm.Fonts: hdr:Hourglass
rm.Fonts: hdr:FileTypes
rm.Fonts: hdr:Territory
rm.Fonts: hdr:NDRDebug
rm.Fonts: hdr:PublicWS
rm.Fonts: hdr:hostfs
rm.Fonts: s.Errors
rm.Fonts: s.Fonts01
rm.Fonts: Version
rm.Fonts: s.FontsM
rm.Fonts: s.ListFonts
rm.Fonts: s.Fonts02
rm.Fonts: s.Fonts03
rm.Fonts: s.Font_Arith
rm.Fonts: s.Font_BasFP
rm.Fonts: s.Funcache
rm.Fonts: s.Fonts04
rm.Fonts: s.Encoding
rm.Fonts: s.Blending
rm.Fonts: hdr:ITable
