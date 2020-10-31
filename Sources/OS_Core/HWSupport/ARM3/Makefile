# Makefile for ARM3
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
ASFLAGS = -depend !Depend -Stamp -quit -module -To $@ -From
CPFLAGS = ~cfr~v

#
# Program specific options:
#
COMPONENT = ARM3
SOURCE    = s.Support2
TARGET    = rm.ARM3
EXPORTS   = ${EXP_HDR}.ARM3Cache

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

${TARGET}: ${SOURCE}
        ${AS} ${ASFLAGS} ${SOURCE} \

${EXP_HDR}.ARM3Cache: hdr.ARM3Cache
        ${CP} hdr.ARM3Cache $@ ${CPFLAGS}

# Dynamic dependencies:
rm.ARM3: Hdr:ListOpts
rm.ARM3: Hdr:Macros
rm.ARM3: Hdr:System
rm.ARM3: Hdr:SWIs
rm.ARM3: Hdr:CPU.Generic26
rm.ARM3: Hdr:IO.GenericIO
rm.ARM3: Hdr:RISCOS
rm.ARM3: Hdr:CMOS
rm.ARM3: Hdr:ModHand
rm.ARM3: Hdr:Services
rm.ARM3: Hdr:Proc
rm.ARM3: Hdr:FSNumbers
rm.ARM3: Hdr:NewErrors
rm.ARM3: Hdr:MsgTrans
