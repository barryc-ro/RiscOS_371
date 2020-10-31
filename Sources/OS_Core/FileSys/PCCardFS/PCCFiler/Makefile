# Makefile for PCCardFSFiler
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name         Description
# ----       ----         -----------
# 18-11-94   WT           Created
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
COMPONENT = PCCFiler
SOURCE    = s.Front
TARGET    = rm.PCCFiler
EXPORTS   = ${EXP_HDR}.${COMPONENT}
RDIR        = Resources
LDIR        = ${RDIR}.${LOCALE}

#
# Export Paths for Messages module
#
RESDIR = <resource$dir>.Resources2.${COMPONENT}

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
        ${MKDIR} ${RESDIR}
        ${CP} ${LDIR}.Messages  ${RESDIR}.Messages ${CPFLAGS}
        ${CP} ${LDIR}.Templates ${RESDIR}.Templates ${CPFLAGS}
        @echo ${COMPONENT}: resource files copied

${TARGET}: ${SOURCE}
        ${AS} ${ASFLAGS} ${SOURCE}

${EXP_HDR}.${COMPONENT}: hdr.${COMPONENT}
        ${CP} hdr.${COMPONENT} $@ ${CPFLAGS}

# Dynamic dependencies:
rm.PCCFiler: Hdr:ListOpts
rm.PCCFiler: Hdr:Macros
rm.PCCFiler: Hdr:System
rm.PCCFiler: Hdr:SWIs
rm.PCCFiler: Hdr:CPU.Generic26
rm.PCCFiler: Hdr:IO.GenericIO
rm.PCCFiler: Hdr:RISCOS
rm.PCCFiler: Hdr:ModHand
rm.PCCFiler: Hdr:Wimp
rm.PCCFiler: Hdr:WimpSpace
rm.PCCFiler: Hdr:Messages
rm.PCCFiler: Hdr:Sprite
rm.PCCFiler: Hdr:VduExt
rm.PCCFiler: Hdr:NdrDebug
rm.PCCFiler: Hdr:HostFS
rm.PCCFiler: Hdr:PCMCIA
rm.PCCFiler: Hdr:PCCardFS
rm.PCCFiler: Hdr:MsgTrans
rm.PCCFiler: Hdr:MsgMenus
rm.PCCFiler: Hdr:Free
rm.PCCFiler: Hdr:Hourglass
rm.PCCFiler: Version
rm.PCCFiler: s.ModHead
rm.PCCFiler: s.Service
rm.PCCFiler: s.StarCmd
rm.PCCFiler: s.Wimpcore
rm.PCCFiler: s.events
rm.PCCFiler: s.fsops
rm.PCCFiler: s.Free
rm.PCCFiler: s.Format
rm.PCCFiler: s.Tail
