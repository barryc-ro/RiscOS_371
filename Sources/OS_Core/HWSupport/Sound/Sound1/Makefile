# Makefile for Sound Channel Handler (Sound1)
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

#
# Program specific options:
#
COMPONENT = Sound1
SOURCE    = s.Sound1
TARGET    = rm.${MACHINE}.Sound1

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
        ${RM} s.TokHelpSrc
        @echo ${COMPONENT}: cleaned

resources:
        ${MKDIR} ${RESDIR}.SoundChann
        ${CP} Resources.${LOCALE}.Messages  ${RESDIR}.SoundChann.Messages  ${CPFLAGS}
        @echo ${COMPONENT}: resource files copied

${TARGET}: ${SOURCE} s.TokHelpSrc
        ${MKDIR} rm.${MACHINE}
        ${AS} ${ASFLAGS} ${SOURCE}

s.TokHelpSrc: Hdr:Tokens HelpSrc
        tokenise Hdr:Tokens HelpSrc $@

# Dynamic dependencies:
rm.Jordan.Sound1: Hdr:ListOpts
rm.Jordan.Sound1: Hdr:Macros
rm.Jordan.Sound1: Hdr:System
rm.Jordan.Sound1: Hdr:SWIs
rm.Jordan.Sound1: Hdr:CPU.Generic26
rm.Jordan.Sound1: Hdr:IO.GenericIO
rm.Jordan.Sound1: Hdr:RISCOS
rm.Jordan.Sound1: Hdr:Machine.<Machine>
rm.Jordan.Sound1: Hdr:ModHand
rm.Jordan.Sound1: Hdr:Services
rm.Jordan.Sound1: Hdr:FSNumbers
rm.Jordan.Sound1: Hdr:NewErrors
rm.Jordan.Sound1: Hdr:PublicWS
rm.Jordan.Sound1: Hdr:Proc
rm.Jordan.Sound1: Hdr:CMOS
rm.Jordan.Sound1: Hdr:Tokens
rm.Jordan.Sound1: Hdr:MsgTrans
rm.Jordan.Sound1: Hdr:Debug
rm.Jordan.Sound1: Hdr:Sound
rm.Jordan.Sound1: Version
rm.Jordan.Sound1: s.TokHelpSrc
rm.Morris.Sound1: Hdr:ListOpts
rm.Morris.Sound1: Hdr:Macros
rm.Morris.Sound1: Hdr:System
rm.Morris.Sound1: Hdr:SWIs
rm.Morris.Sound1: Hdr:CPU.Generic26
rm.Morris.Sound1: Hdr:IO.GenericIO
rm.Morris.Sound1: Hdr:RISCOS
rm.Morris.Sound1: Hdr:Machine.<Machine>
rm.Morris.Sound1: Hdr:ModHand
rm.Morris.Sound1: Hdr:Services
rm.Morris.Sound1: Hdr:FSNumbers
rm.Morris.Sound1: Hdr:NewErrors
rm.Morris.Sound1: Hdr:PublicWS
rm.Morris.Sound1: Hdr:Proc
rm.Morris.Sound1: Hdr:CMOS
rm.Morris.Sound1: Hdr:Tokens
rm.Morris.Sound1: Hdr:MsgTrans
rm.Morris.Sound1: Hdr:Debug
rm.Morris.Sound1: Hdr:Sound
rm.Morris.Sound1: Version
rm.Morris.Sound1: s.TokHelpSrc
