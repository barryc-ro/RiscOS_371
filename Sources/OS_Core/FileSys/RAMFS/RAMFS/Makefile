# Makefile for RAMFS
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

TOKENISE = tokenise
TOKENS   = Hdr:Tokens

#
# Program specific options:
#
COMPONENT = RAMFS
SOURCE    = s.RAMFS
TARGET    = rm.RAMFS
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
        ${AS} ${ASFLAGS} ${SOURCE}

s.TokenHelp: ${TOKENS} HelpText
        ${TOKENISE} ${TOKENS} HelpText $@

${EXP_HDR}.${COMPONENT}: hdr.${COMPONENT}
        ${CP} hdr.${COMPONENT} $@ ${CPFLAGS}

# Dynamic dependencies:
rm.RAMFS: Version
rm.RAMFS: Hdr:ListOpts
rm.RAMFS: Hdr:Macros
rm.RAMFS: Hdr:System
rm.RAMFS: Hdr:SWIs
rm.RAMFS: Hdr:CPU.Generic26
rm.RAMFS: Hdr:IO.GenericIO
rm.RAMFS: Hdr:RISCOS
rm.RAMFS: Hdr:Services
rm.RAMFS: Hdr:ModHand
rm.RAMFS: Hdr:UpCall
rm.RAMFS: Hdr:Tokens
rm.RAMFS: Hdr:Proc
rm.RAMFS: Hdr:MsgTrans
rm.RAMFS: Hdr:FileCore
rm.RAMFS: Hdr:FSNumbers
rm.RAMFS: Hdr:NewErrors
rm.RAMFS: s.MyMacros
rm.RAMFS: s.Defns
rm.RAMFS: s.DebugOpts
rm.RAMFS: s.Header
rm.RAMFS: s.Errors
rm.RAMFS: s.RamFS00
rm.RAMFS: s.RamFS05
rm.RAMFS: s.RamFS15
rm.RAMFS: s.TokenHelp
rm.RAMFS: s.RamFS50
rm.RAMFS: s.MsgCode
