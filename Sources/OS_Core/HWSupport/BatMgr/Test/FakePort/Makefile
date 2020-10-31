# Makefile for Fake Portable
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name         Description
# ----       ----         -----------
# 09-Aug-94  AMcC         Created.
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
COMPONENT = FakePort
SOURCE    = s.Portable
TARGET    = rm.Portable

#
# Generic rules:
#
all: ${TARGET}
        @echo ${COMPONENT}: all built

clean:
        ${RM} ${TARGET}
        @echo ${COMPONENT}: cleaned

${TARGET}: ${SOURCE}
        ${AS} ${ASFLAGS} ${SOURCE}

# Dynamic dependencies:
rm.Portable: Hdr:ListOpts
rm.Portable: Hdr:Macros
rm.Portable: Hdr:System
rm.Portable: Hdr:SWIs
rm.Portable: Hdr:CPU.Generic26
rm.Portable: Hdr:IO.GenericIO
rm.Portable: Hdr:RISCOS
rm.Portable: Hdr:ModHand
rm.Portable: Hdr:Services
rm.Portable: Hdr:FSNumbers
rm.Portable: Hdr:NewErrors
rm.Portable: Hdr:Portable
rm.Portable: s.date/time
