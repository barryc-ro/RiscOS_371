# Makefile for Keyboard
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
COMPONENT = Keyboard
SOURCE    = s.GetAll
TARGET    = rm.${MACHINE}.Keyboard

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
        ${MKDIR} rm.${MACHINE}
        ${AS} ${ASFLAGS} ${SOURCE}

# Dynamic dependencies:
rm.Jordan.Keyboard: Hdr:ListOpts
rm.Jordan.Keyboard: Hdr:Macros
rm.Jordan.Keyboard: Hdr:System
rm.Jordan.Keyboard: Hdr:SWIs
rm.Jordan.Keyboard: Hdr:CPU.Generic26
rm.Jordan.Keyboard: Hdr:IO.GenericIO
rm.Jordan.Keyboard: Hdr:RISCOS
rm.Jordan.Keyboard: Hdr:Machine.<Machine>
rm.Jordan.Keyboard: Hdr:IO.IOMD
rm.Jordan.Keyboard: Hdr:ModHand
rm.Jordan.Keyboard: Hdr:Services
rm.Jordan.Keyboard: Hdr:NdrDebug
rm.Jordan.Keyboard: Hdr:DDVMacros
rm.Jordan.Keyboard: Hdr:Proc
rm.Jordan.Keyboard: Version
rm.Jordan.Keyboard: s.Front
rm.Jordan.Keyboard: s.Macros
rm.Jordan.Keyboard: s.ModHead
rm.Jordan.Keyboard: s.Key
rm.Jordan.Keyboard: s.Tail
