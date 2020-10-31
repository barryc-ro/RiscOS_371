# Makefile for MsgTrans
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
COMPONENT = MsgTrans
SOURCE    = s.MsgTrans
TARGET    = rm.MsgTrans
EXPORTS   = ${EXP_HDR}.MsgTrans \
            ${EXP_HDR}.MsgMenus
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

${EXP_HDR}.MsgTrans: hdr.MsgTrans
        ${CP} hdr.MsgTrans $@ ${CPFLAGS}

${EXP_HDR}.MsgMenus: hdr.MsgMenus
        ${CP} hdr.MsgMenus $@ ${CPFLAGS}

# Dynamic dependencies:
rm.MsgTrans: Hdr:ListOpts
rm.MsgTrans: Hdr:Macros
rm.MsgTrans: Hdr:Symbols
rm.MsgTrans: Hdr:System
rm.MsgTrans: Hdr:SWIs
rm.MsgTrans: Hdr:CPU.Generic26
rm.MsgTrans: Hdr:IO.GenericIO
rm.MsgTrans: Hdr:RISCOS
rm.MsgTrans: Hdr:ModHand
rm.MsgTrans: Hdr:FSNumbers
rm.MsgTrans: Hdr:HighFSI
rm.MsgTrans: Hdr:NewErrors
rm.MsgTrans: Hdr:WimpSpace
rm.MsgTrans: Hdr:Messages
rm.MsgTrans: Hdr:Proc
rm.MsgTrans: Hdr:Services
rm.MsgTrans: Hdr:MsgTrans
rm.MsgTrans: Hdr:NDRDebug
rm.MsgTrans: Hdr:PublicWS
rm.MsgTrans: Hdr:Squash
rm.MsgTrans: Version
