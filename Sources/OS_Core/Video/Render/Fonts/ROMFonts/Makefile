# Makefile for ROMFonts
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name         Description
# ----       ----         -----------
# 25-May-94  AMcC         Created.
#

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
COMPONENT = ROMFonts
SOURCE    = s.ROMFonts
TARGET    = rm.ROMFonts

#
# Generic rules:
#
rom: ${TARGET}
        @echo ${COMPONENT}: rom module built

export: 
        @echo ${COMPONENT}: export complete

install_rom: ${TARGET}
        ${CP} ${TARGET} ${INSTDIR}.${COMPONENT} ${CPFLAGS}
        @echo ${COMPONENT}: rom module installed

clean:
        ${RM} ${TARGET}
        @echo ${COMPONENT}: cleaned

${TARGET}: ${SOURCE}
        ${AS} ${ASFLAGS} ${SOURCE}

# Dynamic dependencies:
rm.ROMFonts: Hdr:ListOpts
rm.ROMFonts: Hdr:Macros
rm.ROMFonts: Hdr:System
rm.ROMFonts: Hdr:SWIs
rm.ROMFonts: Hdr:CPU.Generic26
rm.ROMFonts: Hdr:IO.GenericIO
rm.ROMFonts: Hdr:RISCOS
rm.ROMFonts: Hdr:ModHand
rm.ROMFonts: Hdr:Services
rm.ROMFonts: Hdr:Proc
rm.ROMFonts: Hdr:FSNumbers
rm.ROMFonts: Hdr:NewErrors
rm.ROMFonts: Hdr:Variables
rm.ROMFonts: Hdr:ResourceFS
rm.ROMFonts: Version
rm.ROMFonts: Hdr:NDRDebug
