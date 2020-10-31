# Makefile for DMA
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
COMPONENT = DMA
SOURCE    = s.GetAll
TARGET    = rm.DMA
EXPORTS   = ${EXP_HDR}.DMA

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
        ${AS} ${ASFLAGS} ${SOURCE}

${EXP_HDR}.DMA: hdr.DMA
        ${CP} hdr.DMA $@ ${CPFLAGS}

# Dynamic dependencies:
rm.DMA: Hdr:ListOpts
rm.DMA: Hdr:Macros
rm.DMA: Hdr:System
rm.DMA: Hdr:SWIs
rm.DMA: Hdr:CPU.Generic26
rm.DMA: Hdr:IO.GenericIO
rm.DMA: Hdr:RISCOS
rm.DMA: Hdr:ModHand
rm.DMA: Hdr:IO.IOMD
rm.DMA: Hdr:Services
rm.DMA: Hdr:MsgTrans
rm.DMA: Hdr:ResourceFS
rm.DMA: Hdr:DevNos
rm.DMA: Hdr:Proc
rm.DMA: Hdr:FSNumbers
rm.DMA: Hdr:NewErrors
rm.DMA: Hdr:HostFS
rm.DMA: Hdr:NdrDebug
rm.DMA: Hdr:DDVMacros
rm.DMA: Version
rm.DMA: s.Front
rm.DMA: s.Macros
rm.DMA: s.Errors
rm.DMA: s.ModHead
rm.DMA: s.SWI
rm.DMA: s.DMA
rm.DMA: s.Tail
