# Makefile for FileSwitch
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
COMPONENT = FileSwitch
SOURCE    = s.FileSwitch
TARGET    = rm.FileSwitch
EXPORTS   = ${EXP_HDR}.LowFSI \
            ${EXP_HDR}.HighFSI

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
        ${RM} s.TokHelpSrc
        @echo ${COMPONENT}: cleaned

resources:
        ${MKDIR} ${RESDIR}.${COMPONENT}
        ${CP} Resources.${LOCALE}.Messages  ${RESDIR}.${COMPONENT}.Messages  ${CPFLAGS}
        @echo ${COMPONENT}: resource files copied

${TARGET}: ${SOURCE} s.TokHelpSrc
        ${AS} ${ASFLAGS} ${SOURCE}

s.TokHelpSrc: Hdr:Tokens HelpSrc
        tokenise Hdr:Tokens HelpSrc $@

${EXP_HDR}.LowFSI: hdr.LowFSI
        ${CP} hdr.LowFSI $@ ${CPFLAGS}

${EXP_HDR}.HighFSI: hdr.HighFSI
        ${CP} hdr.HighFSI $@ ${CPFLAGS}

# Dynamic dependencies:
rm.FileSwitch: s.FileSwHdr
rm.FileSwitch: Hdr:ListOpts
rm.FileSwitch: Hdr:Macros
rm.FileSwitch: Hdr:System
rm.FileSwitch: Hdr:SWIs
rm.FileSwitch: Hdr:CPU.Generic26
rm.FileSwitch: Hdr:IO.GenericIO
rm.FileSwitch: Hdr:RISCOS
rm.FileSwitch: Hdr:CMOS
rm.FileSwitch: Hdr:ModHand
rm.FileSwitch: Hdr:Services
rm.FileSwitch: Hdr:FSNumbers
rm.FileSwitch: Hdr:HighFSI
rm.FileSwitch: Hdr:NewErrors
rm.FileSwitch: Hdr:Heap
rm.FileSwitch: Hdr:Variables
rm.FileSwitch: Hdr:EnvNumbers
rm.FileSwitch: Hdr:Proc
rm.FileSwitch: Hdr:PublicWS
rm.FileSwitch: Hdr:Tokens
rm.FileSwitch: Hdr:FileTypes
rm.FileSwitch: Hdr:VduExt
rm.FileSwitch: Hdr:UpCall
rm.FileSwitch: Hdr:LowFSi
rm.FileSwitch: Hdr:Wimp
rm.FileSwitch: Hdr:MsgTrans
rm.FileSwitch: Hdr:Territory
rm.FileSwitch: s.DebugOpts
rm.FileSwitch: s.FileSwBody
rm.FileSwitch: Version
rm.FileSwitch: HelpSrc
rm.FileSwitch: s.FSCommands
rm.FileSwitch: s.FSErrors
rm.FileSwitch: s.FSCommon
rm.FileSwitch: s.MsgsStuff
rm.FileSwitch: s.SysVars
rm.FileSwitch: s.Canonical
rm.FileSwitch: s.Ensure
rm.FileSwitch: s.FileTypes
rm.FileSwitch: s.DirStore
rm.FileSwitch: s.FSPath
rm.FileSwitch: s.TopPath
rm.FileSwitch: s.FSUtils
rm.FileSwitch: s.FSUtils2
rm.FileSwitch: s.FSUtils3
rm.FileSwitch: s.FSControl
rm.FileSwitch: s.CtrlUtils
rm.FileSwitch: s.FSCtrl2
rm.FileSwitch: s.StreamBits
rm.FileSwitch: s.OSFile
rm.FileSwitch: s.OSFind
rm.FileSwitch: s.OSBGetBPut
rm.FileSwitch: s.OSGBPB
rm.FileSwitch: s.OSArgs
rm.FileSwitch: s.LowLevel
rm.FileSwitch: s.FSShared
