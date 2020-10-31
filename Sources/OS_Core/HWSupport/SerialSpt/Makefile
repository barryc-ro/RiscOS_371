# Makefile for SerialSpt
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
COMPONENT = SerialSpt
SOURCE    = s.SerialSpt
TARGET    = rm.SerialSpt

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
rm.SerialSpt: Hdr:ListOpts
rm.SerialSpt: Hdr:Macros
rm.SerialSpt: Hdr:DDVMacros
rm.SerialSpt: Hdr:System
rm.SerialSpt: Hdr:SWIs
rm.SerialSpt: Hdr:CPU.Generic26
rm.SerialSpt: Hdr:IO.GenericIO
rm.SerialSpt: Hdr:RISCOS
rm.SerialSpt: Hdr:ModHand
rm.SerialSpt: Hdr:FSNumbers
rm.SerialSpt: Hdr:NewErrors
rm.SerialSpt: Hdr:CMOS
rm.SerialSpt: Hdr:Symbols
rm.SerialSpt: Hdr:Services
rm.SerialSpt: Hdr:DeviceFS
rm.SerialSpt: Hdr:Serial
rm.SerialSpt: Hdr:RS423
rm.SerialSpt: Hdr:HostFS
rm.SerialSpt: Hdr:NdrDebug
rm.SerialSpt: Hdr:MsgTrans
rm.SerialSpt: Hdr:UpCall
rm.SerialSpt: Hdr:Proc
rm.SerialSpt: Version
rm.SerialSpt: s.Macros
rm.SerialSpt: s.Errors
