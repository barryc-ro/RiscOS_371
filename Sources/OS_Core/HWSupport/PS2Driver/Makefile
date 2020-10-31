# Makefile for PS2 Driver
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name         Description
# ----       ----         -----------
# 30-Jun-94  AMcC         Created.
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
COMPONENT = PS2Driver
SOURCE    = s.GetAll
TARGET    = rm.${MACHINE}.PS2Driver

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
        ${MKDIR} rm.${MACHINE}
        ${AS} ${ASFLAGS} ${SOURCE}

# Dynamic dependencies:
rm.Jordan.PS2Driver: Hdr:ListOpts
rm.Jordan.PS2Driver: Hdr:Macros
rm.Jordan.PS2Driver: Hdr:System
rm.Jordan.PS2Driver: Hdr:SWIs
rm.Jordan.PS2Driver: Hdr:CPU.Generic26
rm.Jordan.PS2Driver: Hdr:IO.GenericIO
rm.Jordan.PS2Driver: Hdr:RISCOS
rm.Jordan.PS2Driver: Hdr:Machine.Morris
rm.Jordan.PS2Driver: Hdr:IO.IOMD
rm.Jordan.PS2Driver: Hdr:ModHand
rm.Jordan.PS2Driver: Hdr:Services
rm.Jordan.PS2Driver: Hdr:MsgTrans
rm.Jordan.PS2Driver: Hdr:ResourceFS
rm.Jordan.PS2Driver: Hdr:Buffer
rm.Jordan.PS2Driver: Hdr:FSNumbers
rm.Jordan.PS2Driver: Hdr:CMOS
rm.Jordan.PS2Driver: Hdr:HostFS
rm.Jordan.PS2Driver: Hdr:NdrDebug
rm.Jordan.PS2Driver: Hdr:DDVMacros
rm.Jordan.PS2Driver: Hdr:Proc
rm.Jordan.PS2Driver: Hdr:Pointer
rm.Jordan.PS2Driver: Hdr:Debug
rm.Jordan.PS2Driver: Version
rm.Jordan.PS2Driver: s.Front
rm.Jordan.PS2Driver: s.Macros
rm.Jordan.PS2Driver: s.ModHead
rm.Jordan.PS2Driver: s.PS2Driver
rm.Jordan.PS2Driver: s.Tail
rm.Morris.PS2Driver: Hdr:ListOpts
rm.Morris.PS2Driver: Hdr:Macros
rm.Morris.PS2Driver: Hdr:System
rm.Morris.PS2Driver: Hdr:SWIs
rm.Morris.PS2Driver: Hdr:CPU.Generic26
rm.Morris.PS2Driver: Hdr:IO.GenericIO
rm.Morris.PS2Driver: Hdr:RISCOS
rm.Morris.PS2Driver: Hdr:Machine.<Machine>
rm.Morris.PS2Driver: Hdr:IO.IOMDL
rm.Morris.PS2Driver: Hdr:DevNos
rm.Morris.PS2Driver: Hdr:KEYV
rm.Morris.PS2Driver: Hdr:ModHand
rm.Morris.PS2Driver: Hdr:Services
rm.Morris.PS2Driver: Hdr:MsgTrans
rm.Morris.PS2Driver: Hdr:ResourceFS
rm.Morris.PS2Driver: Hdr:Buffer
rm.Morris.PS2Driver: Hdr:FSNumbers
rm.Morris.PS2Driver: Hdr:CMOS
rm.Morris.PS2Driver: Hdr:HostFS
rm.Morris.PS2Driver: Hdr:NdrDebug
rm.Morris.PS2Driver: Hdr:DDVMacros
rm.Morris.PS2Driver: Hdr:Proc
rm.Morris.PS2Driver: Hdr:Pointer
rm.Morris.PS2Driver: Hdr:Debug
rm.Morris.PS2Driver: Hdr:Portable
rm.Morris.PS2Driver: Version
rm.Morris.PS2Driver: s.Front
rm.Morris.PS2Driver: s.Macros
rm.Morris.PS2Driver: s.ModHead
rm.Morris.PS2Driver: s.PS2Driver
rm.Morris.PS2Driver: s.Tail
