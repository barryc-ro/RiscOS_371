# Makefile for Territory Manager
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
COMPONENT = TerrMgr
SOURCE    = s.TerrMgr
TARGET    = rm.TerrMgr
EXPORTS   = ${EXP_HDR}.Territory

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
        ${RM} z.SystemDisc
        @echo ${COMPONENT}: cleaned

resources:
        ${MKDIR} ${RESDIR}.${COMPONENT}
        ${CP} Resources.${LOCALE}.Messages  ${RESDIR}.${COMPONENT}.Messages  ${CPFLAGS}
        @echo ${COMPONENT}: resource files copied

${TARGET}: ${SOURCE} z.SystemDisc
        ${AS} ${ASFLAGS} ${SOURCE}

z.SystemDisc: SystemDisc
        @echo Compressing sprite
        MakeSprite
        stamp $@

${EXP_HDR}.Territory: hdr.Territory
        ${CP} hdr.Territory $@ ${CPFLAGS}

# Dynamic dependencies:
rm.TerrMgr: Hdr:ListOpts
rm.TerrMgr: Hdr:Macros
rm.TerrMgr: Hdr:System
rm.TerrMgr: Hdr:SWIs
rm.TerrMgr: Hdr:CPU.Generic26
rm.TerrMgr: Hdr:IO.GenericIO
rm.TerrMgr: Hdr:RISCOS
rm.TerrMgr: Hdr:ModHand
rm.TerrMgr: Hdr:Services
rm.TerrMgr: Hdr:VduExt
rm.TerrMgr: Hdr:FSNumbers
rm.TerrMgr: Hdr:NewErrors
rm.TerrMgr: Hdr:Variables
rm.TerrMgr: Hdr:Proc
rm.TerrMgr: Hdr:Sprite
rm.TerrMgr: Hdr:Wimp
rm.TerrMgr: Hdr:Messages
rm.TerrMgr: Hdr:CMOS
rm.TerrMgr: Hdr:MsgTrans
rm.TerrMgr: Hdr:Squash
rm.TerrMgr: Hdr:ColourTran
rm.TerrMgr: Hdr:Territory
rm.TerrMgr: Hdr:NdrDebug
rm.TerrMgr: Version
rm.TerrMgr: s.ModHead
rm.TerrMgr: s.SWIs
rm.TerrMgr: s.Tail
