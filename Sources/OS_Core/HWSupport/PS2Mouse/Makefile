# Makefile for PS2 Mouse Driver
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name         Description
# ----       ----         -----------
# 23-Jun-94  AMcC         Created.
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
COMPONENT = PS2Mouse
SOURCE    = s.GetAll
TARGET    = rm.${MACHINE}.PS2Mouse

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
rm.Morris.PS2Mouse: Hdr:ListOpts
rm.Morris.PS2Mouse: Hdr:Macros
rm.Morris.PS2Mouse: Hdr:System
rm.Morris.PS2Mouse: Hdr:SWIs
rm.Morris.PS2Mouse: Hdr:CPU.Generic26
rm.Morris.PS2Mouse: Hdr:IO.GenericIO
rm.Morris.PS2Mouse: Hdr:RISCOS
rm.Morris.PS2Mouse: Hdr:Machine.<Machine>
rm.Morris.PS2Mouse: Hdr:IO.IOMD
rm.Morris.PS2Mouse: Hdr:ModHand
rm.Morris.PS2Mouse: Hdr:Services
rm.Morris.PS2Mouse: Hdr:MsgTrans
rm.Morris.PS2Mouse: Hdr:ResourceFS
rm.Morris.PS2Mouse: Hdr:Buffer
rm.Morris.PS2Mouse: Hdr:FSNumbers
rm.Morris.PS2Mouse: Hdr:CMOS
rm.Morris.PS2Mouse: Hdr:HostFS
rm.Morris.PS2Mouse: Hdr:NdrDebug
rm.Morris.PS2Mouse: Hdr:DDVMacros
rm.Morris.PS2Mouse: Hdr:Proc
rm.Morris.PS2Mouse: Hdr:Pointer
rm.Morris.PS2Mouse: Hdr:Debug
rm.Morris.PS2Mouse: Version
rm.Morris.PS2Mouse: s.Front
rm.Morris.PS2Mouse: s.Macros
rm.Morris.PS2Mouse: s.ModHead
rm.Morris.PS2Mouse: s.PS2Mouse
rm.Morris.PS2Mouse: s.Tail
