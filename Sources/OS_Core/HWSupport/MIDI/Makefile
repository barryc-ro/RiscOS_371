# MakeFile for MIDI Podule
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
MKDIR    = cdir
AS       = aasm
CP       = copy
MODGEN   = modgen
RM       = remove
TOKENISE = tokenise

AFLAGS   = -depend !Depend -stamp -closeexec -quit
CPFLAGS  = ~cfr~v

TOKENS   = Hdr:Tokens

#
# Program specific options:
#
COMPONENT = MIDI
IMAGE  = rom.MIDIPodule
MODULE = rm.MIDI
LOADER = rm.Loader

all: ${MODULE}
        @echo ${COMPONENT}: all built

clean:
        ${RM} ${IMAGE}
        ${RM} ${MODULE}
        ${RM} ${LOADER}
        ${RM} rm.MIDIlog
        @echo ${COMPONENT}: cleaned

${IMAGE}: MakeROM ${MODULE} ${LOADER}
        MakeROM

${MODULE}: s.MIDIsrc
        ${AS} s.MIDIsrc $@ -module ${AFLAGS}

rm.MIDIlog: s.MIDIlog
        ${AS} s.MIDIlog $@ -module ${AFLAGS}

${LOADER}: s.Loader
        ${AS} s.Loader $@ ${AFLAGS}

#---------------------------------------------------------------------------
# Dynamic dependencies:
rm.Loader: Hdr:ListOpts
rm.Loader: Hdr:Macros
rm.Loader: Hdr:System
rm.Loader: Hdr:SWIs
rm.Loader: Hdr:CPU.Generic26
rm.Loader: Hdr:IO.GenericIO
rm.Loader: Hdr:RISCOS
rm.Loader: Hdr:ModHand
rm.Loader: Hdr:FSNumbers
rm.Loader: Hdr:NewErrors
rm.Loader: Hdr:Podule
rm.Loader: LdrVersion
rm.MIDI: Hdr:ListOpts
rm.MIDI: Hdr:Macros
rm.MIDI: Hdr:System
rm.MIDI: Hdr:SWIs
rm.MIDI: Hdr:CPU.Generic26
rm.MIDI: Hdr:IO.GenericIO
rm.MIDI: Hdr:RISCOS
rm.MIDI: Hdr:Services
rm.MIDI: Hdr:ModHand
rm.MIDI: Hdr:FSNumbers
rm.MIDI: Hdr:NewErrors
rm.MIDI: Hdr:PublicWS
rm.MIDI: Hdr:Sound
rm.MIDI: Hdr:Podule
rm.MIDI: Hdr:PoduleReg
rm.MIDI: Hdr:DevNos
rm.MIDI: Hdr.MIDI
rm.MIDI: Hdr.MIDIStatus
rm.MIDI: Hdr.ACIA
rm.MIDI: Hdr.UART
rm.MIDI: Hdr.VIA
rm.MIDI: Version
