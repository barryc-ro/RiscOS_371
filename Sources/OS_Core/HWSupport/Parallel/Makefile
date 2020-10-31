# Makefile for Parallel Port Driver
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
COMPONENT = Parallel
SOURCE    = s.Parallel
TARGET    = rm.Parallel
TARGETSA  = rm.ParallelSA
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
rm.ParallelSA: s.Parallel
rm.ParallelSA: Hdr:ListOpts
rm.ParallelSA: Hdr:Macros
rm.ParallelSA: Hdr:System
rm.ParallelSA: Hdr:SWIs
rm.ParallelSA: Hdr:CPU.Generic26
rm.ParallelSA: Hdr:IO.GenericIO
rm.ParallelSA: Hdr:RISCOS
rm.ParallelSA: Hdr:ModHand
rm.ParallelSA: Hdr:FSNumbers
rm.ParallelSA: Hdr:NewErrors
rm.ParallelSA: Hdr:Services
rm.ParallelSA: Hdr:Symbols
rm.ParallelSA: Hdr:NdrDebug
rm.ParallelSA: Hdr:Proc
rm.ParallelSA: Hdr:DevNos
rm.ParallelSA: Hdr:PublicWS
rm.ParallelSA: Hdr:DDVMacros
rm.ParallelSA: Hdr:Buffer
rm.ParallelSA: Hdr:DeviceFS
rm.ParallelSA: Hdr:IO.IOC-A1
rm.ParallelSA: Hdr:IO.IOC
rm.ParallelSA: Hdr:IO.IOEB
rm.ParallelSA: Hdr:IO.IOC
rm.ParallelSA: Hdr:CMOS
rm.ParallelSA: Hdr:MsgTrans
rm.ParallelSA: Hdr:ResourceFS
rm.ParallelSA: Version
rm.ParallelSA: s.Errors
rm.ParallelSA: s.ResFiles
rm.ParallelSA: s.Common
rm.ParallelSA: s.IOC
rm.ParallelSA: s.IOEB
rm.ParallelSA: s.FastCent
rm.Parallel: Hdr:ListOpts
rm.Parallel: Hdr:Macros
rm.Parallel: Hdr:System
rm.Parallel: Hdr:SWIs
rm.Parallel: Hdr:CPU.Generic26
rm.Parallel: Hdr:IO.GenericIO
rm.Parallel: Hdr:RISCOS
rm.Parallel: Hdr:ModHand
rm.Parallel: Hdr:FSNumbers
rm.Parallel: Hdr:NewErrors
rm.Parallel: Hdr:Services
rm.Parallel: Hdr:Symbols
rm.Parallel: Hdr:NdrDebug
rm.Parallel: Hdr:Proc
rm.Parallel: Hdr:DevNos
rm.Parallel: Hdr:PublicWS
rm.Parallel: Hdr:DDVMacros
rm.Parallel: Hdr:Buffer
rm.Parallel: Hdr:DeviceFS
rm.Parallel: Hdr:IO.IOC-A1
rm.Parallel: Hdr:IO.IOC
rm.Parallel: Hdr:IO.IOEB
rm.Parallel: Hdr:IO.IOC
rm.Parallel: Hdr:CMOS
rm.Parallel: Hdr:MsgTrans
rm.Parallel: Hdr:ResourceFS
rm.Parallel: Hdr:Portable
rm.Parallel: Version
rm.Parallel: s.Errors
rm.Parallel: s.Common
rm.Parallel: s.IOEB
rm.Parallel: s.FastCent
