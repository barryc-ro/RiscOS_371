# Makefile for Screen Blanker
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
COMPONENT = ScrBlank
SOURCE    = s.ScrBlank
TARGET    = rm.ScrBlank
EXPORTS   = ${EXP_HDR}.${COMPONENT}

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
        ${MKDIR} ${RESDIR}.ScrBlanker
        ${CP} Resources.${LOCALE}.Messages  ${RESDIR}.ScrBlanker.Messages  ${CPFLAGS}
        @echo ${COMPONENT}: resource files copied

${TARGET}: ${SOURCE}
        ${AS} ${ASFLAGS} ${SOURCE}

${EXP_HDR}.${COMPONENT}: hdr.${COMPONENT}
        ${CP} hdr.${COMPONENT} $@ ${CPFLAGS}

# Dynamic dependencies:
rm.ScrBlank: Hdr:ListOpts
rm.ScrBlank: Hdr:Macros
rm.ScrBlank: Hdr:System
rm.ScrBlank: Hdr:SWIs
rm.ScrBlank: Hdr:CPU.Generic26
rm.ScrBlank: Hdr:IO.GenericIO
rm.ScrBlank: Hdr:RISCOS
rm.ScrBlank: Hdr:ModHand
rm.ScrBlank: Hdr:FSNumbers
rm.ScrBlank: Hdr:NewErrors
rm.ScrBlank: Hdr:Services
rm.ScrBlank: Hdr:CMOS
rm.ScrBlank: Hdr:MsgTrans
rm.ScrBlank: Hdr:Portable
rm.ScrBlank: Hdr:Proc
rm.ScrBlank: Hdr:ColourTran
rm.ScrBlank: Hdr:ScrBlank
rm.ScrBlank: Hdr:PaletteV
rm.ScrBlank: Hdr:HostFS
rm.ScrBlank: Hdr:Debug
rm.ScrBlank: Version
