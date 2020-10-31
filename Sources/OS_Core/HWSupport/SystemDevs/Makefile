# Makefile for SystemDevs
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
COMPONENT = SystemDevs
SOURCE    = s.SystemDevs
TARGET    = rm.SystemDevs
TARGETSA  = rm.sa.SystemDevs
RESOURCES = Resources.${LOCALE}.Messages

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
        ${RM} ${TARGETSA}
        @echo ${COMPONENT}: cleaned

resources:
        ${MKDIR} ${RESDIR}.${COMPONENT}
        ${CP} Resources.${LOCALE}.Messages  ${RESDIR}.${COMPONENT}.Messages  ${CPFLAGS}
        @echo ${COMPONENT}: resource files copied

${TARGET}: ${SOURCE}
        ${AS} ${ASFLAGS} ${SOURCE}

#
# Makes a stand-alone version with messages bound in
#
standalone: ${TARGETSA}
        @echo ${COMPONENT}: standalone module built

${TARGETSA}: s.StandAlone ${RESOURCES}
        ${AS} ${ASFLAGS} s.StandAlone

# Dynamic dependencies:
rm.sa.SystemDevs: s.SystemDevs
rm.sa.SystemDevs: Hdr:ListOpts
rm.sa.SystemDevs: Hdr:Macros
rm.sa.SystemDevs: Hdr:System
rm.sa.SystemDevs: Hdr:SWIs
rm.sa.SystemDevs: Hdr:CPU.Generic26
rm.sa.SystemDevs: Hdr:IO.GenericIO
rm.sa.SystemDevs: Hdr:RISCOS
rm.sa.SystemDevs: Hdr:ModHand
rm.sa.SystemDevs: Hdr:Services
rm.sa.SystemDevs: Hdr:Proc
rm.sa.SystemDevs: Hdr:FSNumbers
rm.sa.SystemDevs: Hdr:HighFSI
rm.sa.SystemDevs: Hdr:LowFSi
rm.sa.SystemDevs: Hdr:NewErrors
rm.sa.SystemDevs: Hdr:CMOS
rm.sa.SystemDevs: Hdr:Variables
rm.sa.SystemDevs: Hdr:MsgTrans
rm.sa.SystemDevs: Hdr:ResourceFS
rm.sa.SystemDevs: Version
rm.sa.SystemDevs: s.MsgCode
rm.sa.SystemDevs: s.ResFiles
rm.SystemDevs: Hdr:ListOpts
rm.SystemDevs: Hdr:Macros
rm.SystemDevs: Hdr:System
rm.SystemDevs: Hdr:SWIs
rm.SystemDevs: Hdr:CPU.Generic26
rm.SystemDevs: Hdr:IO.GenericIO
rm.SystemDevs: Hdr:RISCOS
rm.SystemDevs: Hdr:ModHand
rm.SystemDevs: Hdr:Services
rm.SystemDevs: Hdr:Proc
rm.SystemDevs: Hdr:FSNumbers
rm.SystemDevs: Hdr:HighFSI
rm.SystemDevs: Hdr:LowFSi
rm.SystemDevs: Hdr:NewErrors
rm.SystemDevs: Hdr:CMOS
rm.SystemDevs: Hdr:Variables
rm.SystemDevs: Hdr:MsgTrans
rm.SystemDevs: Hdr:ResourceFS
rm.SystemDevs: Version
rm.SystemDevs: s.MsgCode
