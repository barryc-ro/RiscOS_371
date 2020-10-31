# Makefile for IRQUtils2
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
COMPONENT = IRQUtils2
SOURCE    = s.IRQUtils2
TARGET    = rm.IRQUtils2

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
rm.IRQUtils2: Hdr:ListOpts
rm.IRQUtils2: Hdr:Macros
rm.IRQUtils2: Hdr:System
rm.IRQUtils2: Hdr:SWIs
rm.IRQUtils2: Hdr:CPU.Generic26
rm.IRQUtils2: Hdr:IO.GenericIO
rm.IRQUtils2: Hdr:RISCOS
rm.IRQUtils2: Hdr:ModHand
rm.IRQUtils2: Hdr:NdrDebug
rm.IRQUtils2: Version2
