# Makefile for BBCEconet
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name         Description
# ----       ----         -----------
# 25-May-94  AMcC         Created.
# 28-Jun-94  AMcC         Added extra development rules.
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
COMPONENT = BBCEconet
SOURCE    = s.Module
TARGET    = rm.BBCEconet

all: ${TARGET}
        @echo ${COMPONENT}: ${TARGET} built

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
        @echo ${COMPONENT}: cleaned

${TARGET}: ${SOURCE}
        ${AS} ${ASFLAGS} ${SOURCE}

#
# Extra Development rules:
#
install: ${TARGET}
        Access ${TARGET} R/r
        ${CP} ${TARGET} ${INSTDIR}.${COMPONENT} ${CPFLAGS}
        @echo ${COMPONENT}: ${TARGET} installed

maketime:
        MakeTime

version:
        Version

# Dynamic dependencies:
rm.BBCEconet: Hdr:ListOpts
rm.BBCEconet: Hdr:Macros
rm.BBCEconet: Hdr:System
rm.BBCEconet: Hdr:SWIs
rm.BBCEconet: Hdr:CPU.Generic26
rm.BBCEconet: Hdr:IO.GenericIO
rm.BBCEconet: Hdr:RISCOS
rm.BBCEconet: Hdr:Debug
rm.BBCEconet: Hdr:ModHand
rm.BBCEconet: Hdr:FSNumbers
rm.BBCEconet: Hdr:NewErrors
rm.BBCEconet: Hdr:Services
rm.BBCEconet: Hdr:Econet
rm.BBCEconet: Hdr:MsgTrans
rm.BBCEconet: Hdr:Symbols
rm.BBCEconet: Time+Date
rm.BBCEconet: s.Interface
