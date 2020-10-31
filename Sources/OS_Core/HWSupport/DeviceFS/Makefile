# Makefile for DeviceFS
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
COMPONENT = DeviceFS
SOURCE    = s.DeviceFS
TARGET    = rm.DeviceFS
TARGETSA  = rm.DeviceFSSA
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

resources:
        ${MKDIR} ${RESDIR}.${COMPONENT}
        ${CP} Resources.${LOCALE}.Messages  ${RESDIR}.${COMPONENT}.Messages  ${CPFLAGS}
        @echo ${COMPONENT}: resource files copied

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
rm.DeviceFSSA: s.DeviceFS
rm.DeviceFSSA: hdr:ListOpts
rm.DeviceFSSA: hdr:Macros
rm.DeviceFSSA: hdr:System
rm.DeviceFSSA: Hdr:SWIs
rm.DeviceFSSA: Hdr:CPU.Generic26
rm.DeviceFSSA: Hdr:IO.GenericIO
rm.DeviceFSSA: Hdr:RISCOS
rm.DeviceFSSA: hdr:ModHand
rm.DeviceFSSA: hdr:PublicWS
rm.DeviceFSSA: hdr:FSNumbers
rm.DeviceFSSA: Hdr:HighFSI
rm.DeviceFSSA: hdr:LowFSI
rm.DeviceFSSA: hdr:MsgTrans
rm.DeviceFSSA: hdr:Buffer
rm.DeviceFSSA: hdr:DeviceFS
rm.DeviceFSSA: hdr:FileTypes
rm.DeviceFSSA: hdr:UpCall
rm.DeviceFSSA: hdr:Services
rm.DeviceFSSA: hdr:Symbols
rm.DeviceFSSA: hdr:Variables
rm.DeviceFSSA: hdr:CMOS
rm.DeviceFSSA: hdr:NewErrors
rm.DeviceFSSA: hdr:Territory
rm.DeviceFSSA: hdr:NdrDebug
rm.DeviceFSSA: hdr:DDVMacros
rm.DeviceFSSA: hdr:Proc
rm.DeviceFSSA: hdr:ResourceFS
rm.DeviceFSSA: Version
rm.DeviceFSSA: s.Errors
rm.DeviceFSSA: s.Macros
rm.DeviceFSSA: s.ResFiles
rm.DeviceFSSA: s.FSystem
rm.DeviceFSSA: s.Special
rm.DeviceFS: hdr:ListOpts
rm.DeviceFS: hdr:Macros
rm.DeviceFS: hdr:System
rm.DeviceFS: Hdr:SWIs
rm.DeviceFS: Hdr:CPU.Generic26
rm.DeviceFS: Hdr:IO.GenericIO
rm.DeviceFS: Hdr:RISCOS
rm.DeviceFS: hdr:ModHand
rm.DeviceFS: hdr:PublicWS
rm.DeviceFS: hdr:FSNumbers
rm.DeviceFS: Hdr:HighFSI
rm.DeviceFS: hdr:LowFSI
rm.DeviceFS: hdr:MsgTrans
rm.DeviceFS: hdr:Buffer
rm.DeviceFS: hdr:DeviceFS
rm.DeviceFS: hdr:FileTypes
rm.DeviceFS: hdr:UpCall
rm.DeviceFS: hdr:Services
rm.DeviceFS: hdr:Symbols
rm.DeviceFS: hdr:Variables
rm.DeviceFS: hdr:CMOS
rm.DeviceFS: hdr:NewErrors
rm.DeviceFS: hdr:Territory
rm.DeviceFS: hdr:NdrDebug
rm.DeviceFS: hdr:DDVMacros
rm.DeviceFS: hdr:Proc
rm.DeviceFS: hdr:ResourceFS
rm.DeviceFS: Version
rm.DeviceFS: s.Errors
rm.DeviceFS: s.Macros
rm.DeviceFS: s.FSystem
rm.DeviceFS: s.Special
