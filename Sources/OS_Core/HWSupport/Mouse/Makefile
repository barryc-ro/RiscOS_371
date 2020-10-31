# Makefile for Mouse
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
COMPONENT = Mouse
SOURCE    = s.GetAll
TARGET    = rm.${MACHINE}.Mouse

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

resources:
        ${MKDIR} ${RESDIR}.${COMPONENT}
        ${CP} Resources.${LOCALE}.Messages  ${RESDIR}.${COMPONENT}.Messages  ${CPFLAGS}
        @echo ${COMPONENT}: resource files copied

${TARGET}: ${SOURCE}
        ${MKDIR} rm.${MACHINE}
        ${AS} ${ASFLAGS} ${SOURCE}

# Dynamic dependencies:
rm.Jordan.Mouse: Hdr:ListOpts
rm.Jordan.Mouse: Hdr:Macros
rm.Jordan.Mouse: Hdr:System
rm.Jordan.Mouse: Hdr:SWIs
rm.Jordan.Mouse: Hdr:CPU.Generic26
rm.Jordan.Mouse: Hdr:IO.GenericIO
rm.Jordan.Mouse: Hdr:RISCOS
rm.Jordan.Mouse: Hdr:Machine.<Machine>
rm.Jordan.Mouse: Hdr:IO.IOMD
rm.Jordan.Mouse: Hdr:ModHand
rm.Jordan.Mouse: Hdr:Services
rm.Jordan.Mouse: Hdr:MsgTrans
rm.Jordan.Mouse: Hdr:ResourceFS
rm.Jordan.Mouse: Hdr:NdrDebug
rm.Jordan.Mouse: Hdr:DDVMacros
rm.Jordan.Mouse: Hdr:Proc
rm.Jordan.Mouse: Hdr:CMOS
rm.Jordan.Mouse: Hdr:Pointer
rm.Jordan.Mouse: Version
rm.Jordan.Mouse: s.Front
rm.Jordan.Mouse: s.Macros
rm.Jordan.Mouse: s.ModHead
rm.Jordan.Mouse: s.Mouse
rm.Jordan.Mouse: s.Tail
rm.Morris.Mouse: Hdr:ListOpts
rm.Morris.Mouse: Hdr:Macros
rm.Morris.Mouse: Hdr:System
rm.Morris.Mouse: Hdr:SWIs
rm.Morris.Mouse: Hdr:CPU.Generic26
rm.Morris.Mouse: Hdr:IO.GenericIO
rm.Morris.Mouse: Hdr:RISCOS
rm.Morris.Mouse: Hdr:Machine.<Machine>
rm.Morris.Mouse: Hdr:IO.IOMDL
rm.Morris.Mouse: Hdr:ModHand
rm.Morris.Mouse: Hdr:FSNumbers
rm.Morris.Mouse: Hdr:NewErrors
rm.Morris.Mouse: Hdr:Services
rm.Morris.Mouse: Hdr:MsgTrans
rm.Morris.Mouse: Hdr:ResourceFS
rm.Morris.Mouse: Hdr:NdrDebug
rm.Morris.Mouse: Hdr:DDVMacros
rm.Morris.Mouse: Hdr:Proc
rm.Morris.Mouse: Hdr:CMOS
rm.Morris.Mouse: Hdr:Pointer
rm.Morris.Mouse: Version
rm.Morris.Mouse: s.Front
rm.Morris.Mouse: s.Macros
rm.Morris.Mouse: s.ModHead
rm.Morris.Mouse: s.Mouse
rm.Morris.Mouse: s.Tail
