# Makefile for GameModes2
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
COMPONENT = GameModes2
SOURCE    = s.GameModes2
TARGET    = rm.GameModes2

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

# Dynamic dependencies:
rm.GameModes2: Hdr:ListOpts
rm.GameModes2: Hdr:Macros
rm.GameModes2: Hdr:System
rm.GameModes2: Hdr:SWIs
rm.GameModes2: Hdr:CPU.Generic26
rm.GameModes2: Hdr:IO.GenericIO
rm.GameModes2: Hdr:RISCOS
rm.GameModes2: Hdr:ModHand
rm.GameModes2: Hdr:NdrDebug
rm.GameModes2: Version
