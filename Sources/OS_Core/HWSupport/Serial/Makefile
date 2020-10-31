# Makefile for Serial
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
COMPONENT  = Serial
SOURCE     = s.Serial
TARGET     = rm.Serial
TARGETSA   = rm.SerialSA
RESOURCES  = Resources.${LOCALE}.Messages
EXPORTS    = ${EXP_HDR}.Serial \
             ${EXP_HDR}.RS423

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

#
# Exported headers
#
${EXP_HDR}.Serial: hdr.Serial
        ${CP} hdr.Serial $@ ${CPFLAGS}

${EXP_HDR}.RS423: hdr.RS423
        ${CP} hdr.RS423 $@ ${CPFLAGS}

#
# Makes a stand-alone version with messages bound in
#
standalone: ${TARGETSA}
        @echo ${COMPONENT}: standalone module built

${TARGETSA}: s.StandAlone ${RESOURCES}
        ${AS} ${ASFLAGS} s.StandAlone

# Dynamic dependencies:
rm.SerialSA: s.Serial
rm.SerialSA: Hdr:ListOpts
rm.SerialSA: Hdr:Macros
rm.SerialSA: Hdr:System
rm.SerialSA: Hdr:SWIs
rm.SerialSA: Hdr:CPU.Generic26
rm.SerialSA: Hdr:IO.GenericIO
rm.SerialSA: Hdr:RISCOS
rm.SerialSA: Hdr:ModHand
rm.SerialSA: Hdr:FSNumbers
rm.SerialSA: Hdr:HighFSI
rm.SerialSA: Hdr:NewErrors
rm.SerialSA: Hdr:DevNos
rm.SerialSA: Hdr:Services
rm.SerialSA: Hdr:Symbols
rm.SerialSA: Hdr:UpCall
rm.SerialSA: Hdr:NdrDebug
rm.SerialSA: Hdr:DDVMacros
rm.SerialSA: Hdr:CMOS
rm.SerialSA: Hdr:DeviceFS
rm.SerialSA: Hdr:Serial
rm.SerialSA: Hdr:RS423
rm.SerialSA: Hdr:Buffer
rm.SerialSA: Hdr:IO.IOC-A1
rm.SerialSA: Hdr:IO.IOC
rm.SerialSA: Hdr:IO.IOEB
rm.SerialSA: Hdr:IO.IOC
rm.SerialSA: Hdr:MsgTrans
rm.SerialSA: Hdr:Proc
rm.SerialSA: Hdr:ResourceFS
rm.SerialSA: Hdr:Portable
rm.SerialSA: Hdr:HostFS
rm.SerialSA: Version
rm.SerialSA: s.Macros
rm.SerialSA: s.Errors
rm.SerialSA: s.Init
rm.SerialSA: s.ResFiles
rm.SerialSA: s.Common
rm.SerialSA: s.Serial6551
rm.SerialSA: s.Serial710
rm.Serial: Hdr:ListOpts
rm.Serial: Hdr:Macros
rm.Serial: Hdr:System
rm.Serial: Hdr:SWIs
rm.Serial: Hdr:CPU.Generic26
rm.Serial: Hdr:IO.GenericIO
rm.Serial: Hdr:RISCOS
rm.Serial: Hdr:ModHand
rm.Serial: Hdr:FSNumbers
rm.Serial: Hdr:HighFSI
rm.Serial: Hdr:NewErrors
rm.Serial: Hdr:DevNos
rm.Serial: Hdr:Services
rm.Serial: Hdr:Symbols
rm.Serial: Hdr:UpCall
rm.Serial: Hdr:NdrDebug
rm.Serial: Hdr:DDVMacros
rm.Serial: Hdr:CMOS
rm.Serial: Hdr:DeviceFS
rm.Serial: Hdr:Serial
rm.Serial: Hdr:RS423
rm.Serial: Hdr:Buffer
rm.Serial: Hdr:IO.IOC-A1
rm.Serial: Hdr:IO.IOC
rm.Serial: Hdr:IO.IOEB
rm.Serial: Hdr:IO.IOC
rm.Serial: Hdr:MsgTrans
rm.Serial: Hdr:Proc
rm.Serial: Hdr:ResourceFS
rm.Serial: Hdr:Portable
rm.Serial: Hdr:HostFS
rm.Serial: Version
rm.Serial: s.Macros
rm.Serial: s.Errors
rm.Serial: s.Init
rm.Serial: s.Common
rm.Serial: s.Serial710
