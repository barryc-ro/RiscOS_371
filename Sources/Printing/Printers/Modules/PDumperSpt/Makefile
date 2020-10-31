# Makefile for PDumperSpt (PDumpers high level support)
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name         Description
# ----       ----         -----------
# 04-Jul-94  AMcC         Created.
# 20-Jun-95  MJS          revised for new file list
#

#
# Generic options:
#
MKDIR   = cdir
AS      = aasm
CP      = copy
RM      = remove
CCFLAGS = -c -depend !Depend -IC:
ASFLAGS = -depend !Depend -Stamp -quit -module
CPFLAGS = ~cfr~v

#
# Program specific options:
#
COMPONENT = PDumperSpt
SOURCE    = s.${COMPONENT}
TARGET    = rm.${COMPONENT}

#
# Generic rules:
#
all: ${TARGET}
        @echo ${COMPONENT}: all built (disc)

rom: ${TARGET}
        @echo ${COMPONENT}: all built (rom)

export: ${EXPORTS}
        @echo ${COMPONENT}: export complete

install: ${TARGET}
        ${CP} ${TARGET} ${INSTDIR}.${COMPONENT} ${CPFLAGS}
        Access ${INSTDIR}.${COMPONENT} lr/r
        @echo ${COMPONENT}: installed (disc)

install_rom: ${TARGET}
        ${CP} ${TARGET} ${INSTDIR}.${COMPONENT} ${CPFLAGS}
        @echo ${COMPONENT}: installed (rom)

clean:
        ${RM} ${TARGET}
        @echo ${COMPONENT}: cleaned

${TARGET}: ${SOURCE}
        ${AS} ${ASFLAGS} -To $@ -From ${SOURCE}

# Dynamic dependencies:
rm.PDumperSpt: hdr:ListOpts
rm.PDumperSpt: hdr:Macros
rm.PDumperSpt: hdr:System
rm.PDumperSpt: Hdr:SWIs
rm.PDumperSpt: Hdr:CPU.Generic26
rm.PDumperSpt: Hdr:IO.GenericIO
rm.PDumperSpt: Hdr:RISCOS
rm.PDumperSpt: hdr:ModHand
rm.PDumperSpt: hdr:Services
rm.PDumperSpt: hdr:FSNumbers
rm.PDumperSpt: hdr:HighFSI
rm.PDumperSpt: hdr:NewErrors
rm.PDumperSpt: hdr:PDriver
rm.PDumperSpt: hdr:PDumper
rm.PDumperSpt: hdr:MsgTrans
rm.PDumperSpt: hdr:HostFS
rm.PDumperSpt: hdr:NDRDebug
rm.PDumperSpt: hdr:DDVMacros
rm.PDumperSpt: hdr:Proc
rm.PDumperSpt: hdr:ColourTran
rm.PDumperSpt: Version
rm.PDumperSpt: s.Manipulate
rm.PDumperSpt: s.Calib32
rm.PDumperSpt: s.Calib8
rm.PDumperSpt: s.Colour
rm.PDumperSpt: s.Halftone
rm.PDumperSpt: s.Halftone32
rm.PDumperSpt: s.Halftone8
rm.PDumperSpt: s.Error
rm.PDumperSpt: s.Error32
rm.PDumperSpt: s.Error8
rm.PDumperSpt: s.FullRGB
rm.PDumperSpt: s.MsgCode
