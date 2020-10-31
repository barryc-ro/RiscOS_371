# Makefile for Buffer Manager
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
COMPONENT = Buffers
SOURCE    = s.Buffers
TARGET    = rm.Buffers
TARGETSA  = rm.BuffersSA
EXPORTS   = ${EXP_HDR}.Buffer

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

${EXP_HDR}.Buffer: hdr.Buffer
        ${CP} hdr.Buffer $@ ${CPFLAGS}

#
# Makes a stand-alone version with messages bound in
#
standalone: ${TARGETSA}
        @echo ${COMPONENT}: standalone module built


${TARGETSA}: s.StandAlone ${RESOURCES}
        ${AS} ${ASFLAGS} s.StandAlone

# Dynamic dependencies:
rm.BuffersSA: s.Buffers
rm.BuffersSA: Hdr:ListOpts
rm.BuffersSA: Hdr:Macros
rm.BuffersSA: Hdr:System
rm.BuffersSA: Hdr:SWIs
rm.BuffersSA: Hdr:CPU.Generic26
rm.BuffersSA: Hdr:IO.GenericIO
rm.BuffersSA: Hdr:RISCOS
rm.BuffersSA: Hdr:ModHand
rm.BuffersSA: Hdr:FSNumbers
rm.BuffersSA: Hdr:NewErrors
rm.BuffersSA: Hdr:Services
rm.BuffersSA: Hdr:Symbols
rm.BuffersSA: Hdr:NdrDebug
rm.BuffersSA: Hdr:DDVMacros
rm.BuffersSA: Hdr:UpCall
rm.BuffersSA: Hdr:MsgTrans
rm.BuffersSA: Hdr:Proc
rm.BuffersSA: Hdr:ResourceFS
rm.BuffersSA: Version
rm.BuffersSA: s.Errors
rm.BuffersSA: s.ResFiles
rm.BuffersSA: s.MoveBlock
rm.Buffers: Hdr:ListOpts
rm.Buffers: Hdr:Macros
rm.Buffers: Hdr:System
rm.Buffers: Hdr:SWIs
rm.Buffers: Hdr:CPU.Generic26
rm.Buffers: Hdr:IO.GenericIO
rm.Buffers: Hdr:RISCOS
rm.Buffers: Hdr:ModHand
rm.Buffers: Hdr:FSNumbers
rm.Buffers: Hdr:NewErrors
rm.Buffers: Hdr:Services
rm.Buffers: Hdr:Symbols
rm.Buffers: Hdr:NdrDebug
rm.Buffers: Hdr:DDVMacros
rm.Buffers: Hdr:UpCall
rm.Buffers: Hdr:MsgTrans
rm.Buffers: Hdr:Proc
rm.Buffers: Hdr:ResourceFS
rm.Buffers: Version
rm.Buffers: s.Errors
rm.Buffers: s.MoveBlock
