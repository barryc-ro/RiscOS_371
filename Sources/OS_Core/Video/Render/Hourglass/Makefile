# Makefile for Hourglass
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
ASFLAGS = -depend !Depend -Stamp -quit -module
CPFLAGS = ~cfr~v

#
# Program specific options:
#
COMPONENT = Hourglass
SOURCE    = NewOS
TARGET    = rm.Hourglass
EXPORTS   = ${EXP_HDR}.${COMPONENT}

SOURCE200 = OldOS
TARGET200 = rm.Hourgls200

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
        ${RM} ${TARGET200}
        @echo ${COMPONENT}: cleaned

${TARGET}: ${SOURCE}
        ${AS} ${ASFLAGS} -From ${SOURCE} -To $@

${EXP_HDR}.${COMPONENT}: hdr.${COMPONENT}
        ${CP} hdr.${COMPONENT} $@ ${CPFLAGS}

#
# Extra Development rules:
#
install: ${TARGET}
        Access ${TARGET200} R/r
        Access ${TARGET} R/r
        ${CP} ${TARGET} ${INSTDIR}.${COMPONENT} ${CPFLAGS}
        @echo ${COMPONENT}: ${TARGET} installed

${TARGET200}: ${SOURCE200}
        ${AS} ${ASFLAGS} -From ${SOURCE200} -To $@

maketime:
        MakeTime

version:
        Version

# Dynamic dependencies:
rm.Hourglass: s.Module
rm.Hourglass: Hdr:ListOpts
rm.Hourglass: Hdr:Macros
rm.Hourglass: Hdr:System
rm.Hourglass: Hdr:SWIs
rm.Hourglass: Hdr:CPU.Generic26
rm.Hourglass: Hdr:IO.GenericIO
rm.Hourglass: Hdr:RISCOS
rm.Hourglass: Hdr:ModHand
rm.Hourglass: Hdr:Services
rm.Hourglass: Hdr:Hourglass
rm.Hourglass: Hdr:MsgTrans
rm.Hourglass: Hdr:FSNumbers
rm.Hourglass: Hdr:NewErrors
rm.Hourglass: Time+Date
