# Makefile for Sound Event Scheduler (Sound2)
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
COMPONENT = Sound2
SOURCE    = s.Sound2
TARGET    = rm.Sound2

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
        ${MKDIR} ${RESDIR}.SoundSched
        ${CP} Resources.${LOCALE}.Messages  ${RESDIR}.SoundSched.Messages  ${CPFLAGS}
        @echo ${COMPONENT}: resource files copied

${TARGET}: ${SOURCE} s.TokHelpSrc
        ${AS} ${ASFLAGS} ${SOURCE}

s.TokHelpSrc: Hdr:Tokens HelpSrc
        tokenise Hdr:Tokens HelpSrc $@

# Dynamic dependencies:
rm.Sound2: Hdr:ListOpts
rm.Sound2: Hdr:Macros
rm.Sound2: Hdr:System
rm.Sound2: Hdr:SWIs
rm.Sound2: Hdr:CPU.Generic26
rm.Sound2: Hdr:IO.GenericIO
rm.Sound2: Hdr:RISCOS
rm.Sound2: Hdr:ModHand
rm.Sound2: Hdr:Services
rm.Sound2: Hdr:FSNumbers
rm.Sound2: Hdr:NewErrors
rm.Sound2: Hdr:PublicWS
rm.Sound2: Hdr:Proc
rm.Sound2: Hdr:Tokens
rm.Sound2: Hdr:MsgTrans
rm.Sound2: Hdr:Sound
rm.Sound2: Version
rm.Sound2: s.TokHelpSrc
