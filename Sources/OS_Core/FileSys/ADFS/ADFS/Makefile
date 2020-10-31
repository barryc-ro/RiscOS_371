# Makefile for ADFS
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
COMPONENT = ADFS
SOURCE    = s.ADFS
TARGET    = rm.${MACHINE}.ADFS
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
        ${RM} s.TokenHelp
        @echo ${COMPONENT}: cleaned

resources:
        ${MKDIR} ${RESDIR}.${COMPONENT}
        ${CP} Resources.${LOCALE}.Messages  ${RESDIR}.${COMPONENT}.Messages  ${CPFLAGS}
        @echo ${COMPONENT}: resource files copied

${TARGET}: ${SOURCE} s.TokenHelp
        ${MKDIR} rm.${MACHINE}
        ${AS} ${ASFLAGS} ${SOURCE}

s.TokenHelp: Hdr:Tokens HelpText
        tokenise Hdr:Tokens HelpText $@

${EXP_HDR}.${COMPONENT}: hdr.${COMPONENT}
        ${CP} hdr.${COMPONENT} $@ ${CPFLAGS}

# Dynamic dependencies:
rm.Jordan.ADFS: Ver.<Machine>
rm.Jordan.ADFS: Version
rm.Jordan.ADFS: s.Fixes
rm.Jordan.ADFS: DevVersion
rm.Jordan.ADFS: Hdr:ListOpts
rm.Jordan.ADFS: Hdr:Macros
rm.Jordan.ADFS: Hdr:System
rm.Jordan.ADFS: Hdr:SWIs
rm.Jordan.ADFS: Hdr:CPU.Generic26
rm.Jordan.ADFS: Hdr:IO.GenericIO
rm.Jordan.ADFS: Hdr:RISCOS
rm.Jordan.ADFS: Hdr:DevNos
rm.Jordan.ADFS: Hdr:CMOS
rm.Jordan.ADFS: Hdr:Services
rm.Jordan.ADFS: Hdr:ModHand
rm.Jordan.ADFS: Hdr:PublicWS
rm.Jordan.ADFS: Hdr:Tokens
rm.Jordan.ADFS: Hdr:UpCall
rm.Jordan.ADFS: Hdr:FSNumbers
rm.Jordan.ADFS: Hdr:HighFSI
rm.Jordan.ADFS: Hdr:MultiFS
rm.Jordan.ADFS: Hdr:FileCore
rm.Jordan.ADFS: Hdr:ADFS
rm.Jordan.ADFS: Hdr:MsgTrans
rm.Jordan.ADFS: Hdr:NewErrors
rm.Jordan.ADFS: Hdr:Portable
rm.Jordan.ADFS: Hdr:Proc
rm.Jordan.ADFS: Hdr:IO.IOEB
rm.Jordan.ADFS: Hdr:IO.IOC
rm.Jordan.ADFS: Hdr:IO.IOMD
rm.Jordan.ADFS: Hdr:CPU.ARM600
rm.Jordan.ADFS: s.NewBits
rm.Jordan.ADFS: s.ADFSMacros
rm.Jordan.ADFS: s.Consts
rm.Jordan.ADFS: s.DebugOpts
rm.Jordan.ADFS: s.ModHeader
rm.Jordan.ADFS: s.ADFSErrors
rm.Jordan.ADFS: s.ADFS00
rm.Jordan.ADFS: s.ConstIDE
rm.Jordan.ADFS: s.StaticsFDC
rm.Jordan.ADFS: s.StaticsIDE
rm.Jordan.ADFS: s.ADFS05
rm.Jordan.ADFS: s.MEMC1ABits
rm.Jordan.ADFS: s.Adfs11
rm.Jordan.ADFS: s.ADFS12
rm.Jordan.ADFS: s.ADFS13
rm.Jordan.ADFS: s.ADFS14
rm.Jordan.ADFS: s.ADFS15
rm.Jordan.ADFS: s.ADFS17
rm.Jordan.ADFS: s.ADFS18
rm.Jordan.ADFS: s.ADFS19
rm.Jordan.ADFS: s.ADFS20
rm.Jordan.ADFS: s.TokenHelp
rm.Jordan.ADFS: s.ADFS50
rm.Jordan.ADFS: s.MFormat
rm.Morris.ADFS: Ver.<Machine>
rm.Morris.ADFS: Version
rm.Morris.ADFS: s.Fixes
rm.Morris.ADFS: DevVersion
rm.Morris.ADFS: Hdr:ListOpts
rm.Morris.ADFS: Hdr:Macros
rm.Morris.ADFS: Hdr:System
rm.Morris.ADFS: Hdr:SWIs
rm.Morris.ADFS: Hdr:CPU.Generic26
rm.Morris.ADFS: Hdr:IO.GenericIO
rm.Morris.ADFS: Hdr:RISCOS
rm.Morris.ADFS: Hdr:DevNos
rm.Morris.ADFS: Hdr:CMOS
rm.Morris.ADFS: Hdr:Services
rm.Morris.ADFS: Hdr:ModHand
rm.Morris.ADFS: Hdr:PublicWS
rm.Morris.ADFS: Hdr:Tokens
rm.Morris.ADFS: Hdr:UpCall
rm.Morris.ADFS: Hdr:FSNumbers
rm.Morris.ADFS: Hdr:HighFSI
rm.Morris.ADFS: Hdr:MultiFS
rm.Morris.ADFS: Hdr:FileCore
rm.Morris.ADFS: Hdr:ADFS
rm.Morris.ADFS: Hdr:MsgTrans
rm.Morris.ADFS: Hdr:NewErrors
rm.Morris.ADFS: Hdr:Portable
rm.Morris.ADFS: Hdr:Proc
rm.Morris.ADFS: Hdr:IO.IOEB
rm.Morris.ADFS: Hdr:IO.IOC
rm.Morris.ADFS: Hdr:IO.IOMD
rm.Morris.ADFS: Hdr:CPU.ARM600
rm.Morris.ADFS: s.NewBits
rm.Morris.ADFS: s.ADFSMacros
rm.Morris.ADFS: s.Consts
rm.Morris.ADFS: s.DebugOpts
rm.Morris.ADFS: s.ModHeader
rm.Morris.ADFS: s.ADFSErrors
rm.Morris.ADFS: s.ADFS00
rm.Morris.ADFS: s.ConstIDE
rm.Morris.ADFS: s.StaticsFDC
rm.Morris.ADFS: s.StaticsIDE
rm.Morris.ADFS: s.ADFS05
rm.Morris.ADFS: s.MEMC1ABits
rm.Morris.ADFS: s.Adfs11
rm.Morris.ADFS: s.ADFS12
rm.Morris.ADFS: s.ADFS13
rm.Morris.ADFS: s.ADFS14
rm.Morris.ADFS: s.ADFS15
rm.Morris.ADFS: s.ADFS17
rm.Morris.ADFS: s.ADFS18
rm.Morris.ADFS: s.ADFS19
rm.Morris.ADFS: s.ADFS20
rm.Morris.ADFS: s.TokenHelp
rm.Morris.ADFS: s.ADFS50
rm.Morris.ADFS: s.MFormat
rm.Morris.ADFS: s.ADFS_SA
