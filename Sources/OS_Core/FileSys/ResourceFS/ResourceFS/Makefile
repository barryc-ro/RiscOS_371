# Makefile for ResourceFS
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
COMPONENT = ResourceFS
SOURCE    = s.ResourceFS
TARGET    = rm.ResourceFS
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
        ${MKDIR} ${RESDIR}.${COMPONENT}
        ${CP} Resources.${LOCALE}.Messages  ${RESDIR}.${COMPONENT}.Messages  ${CPFLAGS}
        @echo ${COMPONENT}: resource files copied

${TARGET}: ${SOURCE}
        ${AS} ${ASFLAGS} ${SOURCE}

${EXP_HDR}.${COMPONENT}: hdr.${COMPONENT}
        ${CP} hdr.${COMPONENT} $@ ${CPFLAGS}

# Dynamic dependencies:
rm.ResourceFS: Hdr:ListOpts
rm.ResourceFS: Hdr:Macros
rm.ResourceFS: Hdr:System
rm.ResourceFS: Hdr:SWIs
rm.ResourceFS: Hdr:CPU.Generic26
rm.ResourceFS: Hdr:IO.GenericIO
rm.ResourceFS: Hdr:RISCOS
rm.ResourceFS: Hdr:ModHand
rm.ResourceFS: Hdr:Services
rm.ResourceFS: Hdr:CMOS
rm.ResourceFS: Hdr:Proc
rm.ResourceFS: Hdr:FSNumbers
rm.ResourceFS: Hdr:HighFSI
rm.ResourceFS: Hdr:LowFSi
rm.ResourceFS: Hdr:NewErrors
rm.ResourceFS: Hdr:Variables
rm.ResourceFS: Hdr:Wimp
rm.ResourceFS: Hdr:ResourceFS
rm.ResourceFS: Hdr:UpCall
rm.ResourceFS: Hdr:MsgTrans
rm.ResourceFS: Hdr:Territory
rm.ResourceFS: Version
rm.ResourceFS: Hdr:NDRDebug
rm.ResourceFS: s.MsgCode
