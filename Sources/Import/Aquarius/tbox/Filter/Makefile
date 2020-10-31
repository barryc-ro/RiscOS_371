# Makefile for Filter Manager
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
COMPONENT = FilterMgr
SOURCE    = s.FilterMgr
TARGET    = rm.FilterMgr
EXPORTS   = ${EXP_HDR}.Filter

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

${EXP_HDR}.Filter: hdr.Filter
        ${CP} hdr.Filter $@ ${CPFLAGS}

# Dynamic dependencies:
rm.FilterMgr: Hdr:ListOpts
rm.FilterMgr: Hdr:Macros
rm.FilterMgr: Hdr:System
rm.FilterMgr: Hdr:SWIs
rm.FilterMgr: Hdr:CPU.Generic26
rm.FilterMgr: Hdr:IO.GenericIO
rm.FilterMgr: Hdr:RISCOS
rm.FilterMgr: Hdr:ModHand
rm.FilterMgr: Hdr:Services
rm.FilterMgr: Hdr:VduExt
rm.FilterMgr: Hdr:File
rm.FilterMgr: Hdr:NewErrors
rm.FilterMgr: Hdr:Variables
rm.FilterMgr: Hdr:Proc
rm.FilterMgr: Hdr:Sprite
rm.FilterMgr: Hdr:Wimp
rm.FilterMgr: Hdr:WimpSpace
rm.FilterMgr: Hdr:Messages
rm.FilterMgr: Hdr:CMOS
rm.FilterMgr: Hdr:MsgTrans
rm.FilterMgr: Hdr:MsgMenus
rm.FilterMgr: Hdr:ResourceFS
rm.FilterMgr: Hdr:ColourTran
rm.FilterMgr: Hdr:Hourglass
rm.FilterMgr: Hdr:NdrDebug
rm.FilterMgr: Hdr:Switcher
rm.FilterMgr: Version
rm.FilterMgr: s.ModHead
rm.FilterMgr: s.SWIs
rm.FilterMgr: s.MsgTrans
rm.FilterMgr: s.PreFilter
rm.FilterMgr: s.RectFilter
rm.FilterMgr: s.PostFilter
rm.FilterMgr: s.Tail
