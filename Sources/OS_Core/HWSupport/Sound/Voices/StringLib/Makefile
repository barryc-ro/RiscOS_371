# Makefile for StringLib
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
COMPONENT = StringLib
SOURCE    = s.StringLib
TARGET    = rm.StringLib

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
rm.StringLib: Hdr:ListOpts
rm.StringLib: Hdr:Macros
rm.StringLib: Hdr:System
rm.StringLib: Hdr:SWIs
rm.StringLib: Hdr:CPU.Generic26
rm.StringLib: Hdr:IO.GenericIO
rm.StringLib: Hdr:RISCOS
rm.StringLib: Hdr:ModHand
rm.StringLib: Hdr:PublicWS
rm.StringLib: Hdr:Sound
rm.StringLib: Hdr:Proc
rm.StringLib: Hdr:MsgTrans
rm.StringLib: Hdr:Services
rm.StringLib: Hdr:HostFS
rm.StringLib: Hdr:Debug
rm.StringLib: Version
rm.StringLib: s.MsgCode
