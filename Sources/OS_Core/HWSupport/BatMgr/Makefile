# Makefile for Battery Manager
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name         Description
# ----       ----         -----------
# 09-Aug-94  AMcC         Created.
# 03-Nov-94  AMcC         Updated resources rule

#
# Program specific options:
#
COMPONENT = BatMgr
APP       = !BatMgr
SOURCE    = s.BatMgr
TARGET    = rm.BatMgr
TARGETSA  = rm.BatMgrSA
RDIR      = Resources
LDIR      = ${RDIR}.${LOCALE}

#
# Export Paths for Messages module
#
RESDIR = <resource$dir>.Resources.${COMPONENT}
RESAPP = <resource$dir>.Apps.${APP}

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

RESOURCES = \
 ${LDIR}.Messages \
 ${LDIR}.Templates \
 ${LDIR}.!Run \
 ${RDIR}.!Sprites \
 ${RDIR}.Sprites

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

# Note: !Run and !Sprites NOT in Messages module (only required on portables)
resources:
        ${MKDIR} ${RESDIR}
        ${CP} ${LDIR}.Messages  ${RESDIR}.Messages  ${CPFLAGS}
        ${CP} ${LDIR}.Templates ${RESDIR}.Templates ${CPFLAGS}
        ${CP} ${RDIR}.Sprites   ${RESDIR}.Sprites   ${CPFLAGS}
        @echo ${COMPONENT}: resource files copied to Messages module

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
rm.BatMgrSA: s.BatMgr
rm.BatMgrSA: Hdr:ListOpts
rm.BatMgrSA: Hdr:Macros
rm.BatMgrSA: Hdr:System
rm.BatMgrSA: Hdr:SWIs
rm.BatMgrSA: Hdr:CPU.Generic26
rm.BatMgrSA: Hdr:IO.GenericIO
rm.BatMgrSA: Hdr:RISCOS
rm.BatMgrSA: Hdr:Machine.<Machine>
rm.BatMgrSA: Hdr:IO.IOMDL
rm.BatMgrSA: Hdr:Proc
rm.BatMgrSA: Hdr:ModHand
rm.BatMgrSA: Hdr:Services
rm.BatMgrSA: Hdr:Wimp
rm.BatMgrSA: Hdr:FSNumbers
rm.BatMgrSA: Hdr:Messages
rm.BatMgrSA: Hdr:NewErrors
rm.BatMgrSA: Hdr:WimpSpace
rm.BatMgrSA: Hdr:Variables
rm.BatMgrSA: Hdr:ColourTran
rm.BatMgrSA: Hdr:MsgTrans
rm.BatMgrSA: Hdr:MsgMenus
rm.BatMgrSA: Hdr:ADFS
rm.BatMgrSA: Hdr:Portable
rm.BatMgrSA: Hdr:PublicWS
rm.BatMgrSA: Hdr:Sound
rm.BatMgrSA: Hdr:ScrBlank
rm.BatMgrSA: Hdr:CMOS
rm.BatMgrSA: Hdr:Switcher
rm.BatMgrSA: Hdr:Sprite
rm.BatMgrSA: Hdr:VduExt
rm.BatMgrSA: s.Macros
rm.BatMgrSA: Version
rm.BatMgrSA: s.Const
rm.BatMgrSA: s.Workspace
rm.BatMgrSA: s.Module
rm.BatMgrSA: s.Task
rm.BatMgrSA: s.BMU
rm.BatMgrSA: Hdr:ResourceFS
rm.BatMgrSA: s.ResFiles
rm.BatMgr: Hdr:ListOpts
rm.BatMgr: Hdr:Macros
rm.BatMgr: Hdr:System
rm.BatMgr: Hdr:SWIs
rm.BatMgr: Hdr:CPU.Generic26
rm.BatMgr: Hdr:IO.GenericIO
rm.BatMgr: Hdr:RISCOS
rm.BatMgr: Hdr:Machine.<Machine>
rm.BatMgr: Hdr:IO.IOMDL
rm.BatMgr: Hdr:Proc
rm.BatMgr: Hdr:ModHand
rm.BatMgr: Hdr:Services
rm.BatMgr: Hdr:Wimp
rm.BatMgr: Hdr:FSNumbers
rm.BatMgr: Hdr:Messages
rm.BatMgr: Hdr:NewErrors
rm.BatMgr: Hdr:WimpSpace
rm.BatMgr: Hdr:Variables
rm.BatMgr: Hdr:ColourTran
rm.BatMgr: Hdr:MsgTrans
rm.BatMgr: Hdr:MsgMenus
rm.BatMgr: Hdr:ADFS
rm.BatMgr: Hdr:Portable
rm.BatMgr: Hdr:PublicWS
rm.BatMgr: Hdr:Sound
rm.BatMgr: Hdr:ScrBlank
rm.BatMgr: Hdr:CMOS
rm.BatMgr: Hdr:Switcher
rm.BatMgr: Hdr:Sprite
rm.BatMgr: Hdr:VduExt
rm.BatMgr: s.Macros
rm.BatMgr: Version
rm.BatMgr: s.Const
rm.BatMgr: s.Workspace
rm.BatMgr: s.Module
rm.BatMgr: s.Task
rm.BatMgr: s.BMU
rm.BatMgr: Hdr:ResourceFS
rm.BatMgr: s.ResFiles
