# Makefile for UnSqzAIF

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
COMPONENT = UnSqzAIF
SOURCE    = s.Front
TARGET    = rm.UnSqzAIF

#
# Generic rules:
#
rom: ${TARGET}
        @echo ${COMPONENT}: rom module built

install_rom: ${TARGET}
        ${CP} ${TARGET} ${INSTDIR}.${COMPONENT} ${CPFLAGS}
        @echo ${COMPONENT}: rom module installed

clean:
        ${RM} ${TARGET}
        @echo ${COMPONENT}: cleaned

${TARGET}: ${SOURCE}
        ${AS} ${ASFLAGS} ${SOURCE}

# Dynamic dependencies:
rm.UnSqzAIF: Hdr:ListOpts
rm.UnSqzAIF: Hdr:Macros
rm.UnSqzAIF: Hdr:System
rm.UnSqzAIF: Hdr:SWIs
rm.UnSqzAIF: Hdr:CPU.Generic26
rm.UnSqzAIF: Hdr:IO.GenericIO
rm.UnSqzAIF: Hdr:RISCOS
rm.UnSqzAIF: Hdr:Services
rm.UnSqzAIF: Hdr:ModHand
rm.UnSqzAIF: Hdr:MsgTrans
rm.UnSqzAIF: Hdr:NdrDebug
rm.UnSqzAIF: Version
rm.UnSqzAIF: s.ModHead
