# Makefile for Percussion
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
COMPONENT = Percussion
SOURCE    = s.Percussion
TARGET    = rm.Percussion

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
        ${AS} ${ASFLAGS} ${SOURCE}

# Dynamic dependencies:
rm.Percussion: Hdr:ListOpts
rm.Percussion: Hdr:Macros
rm.Percussion: Hdr:System
rm.Percussion: Hdr:SWIs
rm.Percussion: Hdr:CPU.Generic26
rm.Percussion: Hdr:IO.GenericIO
rm.Percussion: Hdr:RISCOS
rm.Percussion: Hdr:ModHand
rm.Percussion: Hdr:PublicWS
rm.Percussion: Hdr:Sound
rm.Percussion: Hdr:Proc
rm.Percussion: Hdr:MsgTrans
rm.Percussion: Hdr:Services
rm.Percussion: Version
rm.Percussion: s.MsgCode
