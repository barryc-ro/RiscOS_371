# Makefile for NetPrint
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name         Description
# ----       ----         -----------
# 25-May-94  AMcC         Created.
#

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

TOKENISE = tokenise
TOKENS   = Hdr:Tokens

#
# Program specific options:
#
COMPONENT = NetPrint
SOURCE    = NewOS
TARGET    = rm.NetPrint

#
# Generic rules:
#
rom: ${TARGET}
        @echo ${COMPONENT}: rom module built

export: 
        @echo ${COMPONENT}: export complete

install_rom: ${TARGET}
        ${CP} ${TARGET} ${INSTDIR}.${COMPONENT} ${CPFLAGS}
        @echo ${COMPONENT}: rom module installed

clean:
        ${RM} ${TARGET}
        ${RM} s.HelpTokens
        @echo ${COMPONENT}: cleaned

resources:
        ${MKDIR} ${RESDIR}.${COMPONENT}
        ${CP} Resources.${LOCALE}.Messages  ${RESDIR}.${COMPONENT}.Messages  ${CPFLAGS}
        @echo ${COMPONENT}: resource files copied

${TARGET}: ${SOURCE} s.HelpTokens
        ${AS} ${ASFLAGS} ${SOURCE}

s.HelpTokens: ${TOKENS} HelpTexts
        ${TOKENISE} ${TOKENS} HelpTexts $@

# Dynamic dependencies:
rm.NetPrint: s.Module
rm.NetPrint: Hdr:ListOpts
rm.NetPrint: Hdr:Macros
rm.NetPrint: Hdr:System
rm.NetPrint: Hdr:SWIs
rm.NetPrint: Hdr:CPU.Generic26
rm.NetPrint: Hdr:IO.GenericIO
rm.NetPrint: Hdr:RISCOS
rm.NetPrint: Hdr:CMOS
rm.NetPrint: Hdr:ModHand
rm.NetPrint: Hdr:Services
rm.NetPrint: Hdr:Econet
rm.NetPrint: Hdr:LowFSi
rm.NetPrint: Hdr:FSNumbers
rm.NetPrint: Hdr:HighFSI
rm.NetPrint: Hdr:Debug
rm.NetPrint: Hdr:NewErrors
rm.NetPrint: Hdr:Tokens
rm.NetPrint: Hdr:MsgTrans
rm.NetPrint: Hdr:Hourglass
rm.NetPrint: Hdr:Territory
rm.NetPrint: Hdr:Symbols
rm.NetPrint: Hdr:Proc
rm.NetPrint: Hdr:HostFS
rm.NetPrint: Time+Date
rm.NetPrint: s.Interface
rm.NetPrint: s.Commands
rm.NetPrint: s.HelpTokens
rm.NetPrint: s.FileSystem
