# Makefile for NetFS
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name         Description
# ----       ----         -----------
# 25-May-94  AMcC         Created.
#

# AMcC {28-Apr-94}: Source should be set to CurrentOS - it's set to NewOS
# for comparison with RISC OS 3.50 only.
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
COMPONENT = NetFS
SOURCE    = CurrentOS
TARGET    = rm.NetFS

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
rm.NetFS: s.Module
rm.NetFS: Hdr:ListOpts
rm.NetFS: Hdr:Macros
rm.NetFS: Hdr:System
rm.NetFS: Hdr:SWIs
rm.NetFS: Hdr:CPU.Generic26
rm.NetFS: Hdr:IO.GenericIO
rm.NetFS: Hdr:RISCOS
rm.NetFS: Hdr:CMOS
rm.NetFS: Hdr:ModHand
rm.NetFS: Hdr:Heap
rm.NetFS: Hdr:Services
rm.NetFS: Hdr:Debug
rm.NetFS: Hdr:FSNumbers
rm.NetFS: Hdr:HighFSI
rm.NetFS: Hdr:LowFSI
rm.NetFS: Hdr:Econet
rm.NetFS: Hdr:NewErrors
rm.NetFS: Hdr:VduExt
rm.NetFS: Hdr:Tokens
rm.NetFS: Hdr:MsgTrans
rm.NetFS: Hdr:Territory
rm.NetFS: Hdr:Symbols
rm.NetFS: Time+Date
rm.NetFS: s.Memory
rm.NetFS: s.Interface
rm.NetFS: s.FileSystem
rm.NetFS: s.Commands
rm.NetFS: s.Configure
rm.NetFS: s.OsFile
rm.NetFS: s.Random
rm.NetFS: s.Functions
rm.NetFS: s.Catalog
rm.NetFS: s.HelpTokens
