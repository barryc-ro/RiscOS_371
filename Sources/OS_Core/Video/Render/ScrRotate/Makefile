# Makefile for ...
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name         Description
# ----       ----         -----------
# 02-Oct-95  RCM          Created.
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
COMPONENT = ScrRotate
SOURCE    = s.GetAll
TARGET    = rm.${COMPONENT}
TARGETSA  = rm.${COMPONENT}SA
EXPORTS   = ${EXP_HDR}.${COMPONENT}
RESOURCES = Resources.${LOCALE}.Messages

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
        ${RM} ${TARGETSA}
        @echo ${COMPONENT}: cleaned

${TARGET}: ${SOURCE}
        ${AS} ${ASFLAGS} ${SOURCE}

${EXP_HDR}.${COMPONENT}: hdr.${COMPONENT}
        ${CP} hdr.${COMPONENT} $@ ${CPFLAGS}

#
# Makes a stand-alone version with messages bound in
#
standalone: ${TARGETSA}
        @echo ${COMPONENT}: standalone module built

${TARGETSA}: s.StandAlone ${RESOURCES}
        ${AS} ${ASFLAGS} s.StandAlone

# Dynamic dependencies:
rm.ScrRotate: Hdr:ListOpts
rm.ScrRotate: Hdr:Macros
rm.ScrRotate: Hdr:System
rm.ScrRotate: Hdr:SWIs
rm.ScrRotate: Hdr:CPU.Generic26
rm.ScrRotate: Hdr:IO.GenericIO
rm.ScrRotate: Hdr:RISCOS
rm.ScrRotate: Hdr:Machine.<Machine>
rm.ScrRotate: Hdr:IO.IOMDL
rm.ScrRotate: Hdr:ModHand
rm.ScrRotate: Hdr:Sprite
rm.ScrRotate: Hdr:Proc
rm.ScrRotate: Hdr:Services
rm.ScrRotate: Version
rm.ScrRotate: s.Front
rm.ScrRotate: s.ScrRotate
