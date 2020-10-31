# Makefile for FileCore
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
COMPONENT = FileCore
SOURCE    = s.FileCore
TARGET    = rm.FileCore
EXPORTS   = ${EXP_HDR}.FileCore \
            ${EXP_HDR}.MultiFS

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
        ${RM} s.TokenHelp
        @echo ${COMPONENT}: cleaned

resources:
        ${MKDIR} ${RESDIR}.${COMPONENT}
        ${CP} Resources.${LOCALE}.Messages  ${RESDIR}.${COMPONENT}.Messages  ${CPFLAGS}
        @echo ${COMPONENT}: resource files copied

${TARGET}: ${SOURCE} s.TokenHelp
        ${AS} ${ASFLAGS} ${SOURCE}

s.TokenHelp: Hdr:Tokens HelpText
        tokenise Hdr:Tokens HelpText $@

${EXP_HDR}.FileCore: hdr.FileCore
        ${CP} hdr.FileCore $@ ${CPFLAGS}

${EXP_HDR}.MultiFS: hdr.MultiFS
        ${CP} hdr.MultiFS $@ ${CPFLAGS}

# Dynamic dependencies:
rm.FileCore: Version
rm.FileCore: s.Fixes
rm.FileCore: s.AsmHdr
rm.FileCore: s.DevVersion
rm.FileCore: Hdr:ListOpts
rm.FileCore: Hdr:Macros
rm.FileCore: Hdr:System
rm.FileCore: Hdr:SWIs
rm.FileCore: Hdr:CPU.Generic26
rm.FileCore: Hdr:IO.GenericIO
rm.FileCore: Hdr:RISCOS
rm.FileCore: Hdr:CMOS
rm.FileCore: Hdr:Services
rm.FileCore: Hdr:ModHand
rm.FileCore: Hdr:FSNumbers
rm.FileCore: Hdr:HighFSI
rm.FileCore: Hdr:PublicWS
rm.FileCore: Hdr:Tokens
rm.FileCore: Hdr:Wimp
rm.FileCore: Hdr:UpCall
rm.FileCore: Hdr:LowFSi
rm.FileCore: Hdr:Heap
rm.FileCore: Hdr:FileCore
rm.FileCore: Hdr:MsgTrans
rm.FileCore: Hdr:FileTypes
rm.FileCore: Hdr:MultiFS
rm.FileCore: Hdr:NewErrors
rm.FileCore: Hdr:Territory
rm.FileCore: s.DebugOpts
rm.FileCore: s.MyMacros
rm.FileCore: s.Defns
rm.FileCore: s.FileCore00
rm.FileCore: s.Errors
rm.FileCore: s.FileCore05
rm.FileCore: s.FileCore15
rm.FileCore: s.FileCore20
rm.FileCore: s.FileCore25
rm.FileCore: s.FileCore30
rm.FileCore: s.FileCore31
rm.FileCore: s.FileCore32
rm.FileCore: s.FileCore33
rm.FileCore: s.FileCore35
rm.FileCore: s.FileCore40
rm.FileCore: s.FileCore45
rm.FileCore: s.TokenHelp
rm.FileCore: s.InitDieSvc
rm.FileCore: s.Commands
rm.FileCore: s.GenSWIs
rm.FileCore: s.MsgsStuff
rm.FileCore: s.FileCore60
rm.FileCore: s.FileCore70
rm.FileCore: s.FileCore80
rm.FileCore: s.FormSrvcs
rm.FileCore: s.FormSWIs
rm.FileCore: s.Identify
