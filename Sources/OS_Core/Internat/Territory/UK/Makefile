# Makefile for UK Territory
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
COMPONENT = UK
SOURCE    = s.UK
TARGET    = rm.UK

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
        @echo ${COMPONENT}: cleaned

resources:
        ${MKDIR} ${RESDIR}.${COMPONENT}
        ${CP} Resources.${LOCALE}.Messages  ${RESDIR}.${COMPONENT}.Messages  ${CPFLAGS}
        @echo ${COMPONENT}: resource files copied

${TARGET}: ${SOURCE}
        ${AS} ${ASFLAGS} ${SOURCE}

# Dynamic dependencies:
rm.UK: Hdr:ListOpts
rm.UK: Hdr:Macros
rm.UK: Hdr:System
rm.UK: Hdr:SWIs
rm.UK: Hdr:CPU.Generic26
rm.UK: Hdr:IO.GenericIO
rm.UK: Hdr:RISCOS
rm.UK: Hdr:ModHand
rm.UK: Hdr:Services
rm.UK: Hdr:FSNumbers
rm.UK: Hdr:NewErrors
rm.UK: Hdr:Variables
rm.UK: Hdr:Proc
rm.UK: Hdr:Messages
rm.UK: Hdr:CMOS
rm.UK: Hdr:MsgTrans
rm.UK: Hdr:Territory
rm.UK: Hdr:NdrDebug
rm.UK: Version
rm.UK: s.ModHead
rm.UK: s.Entries
rm.UK: s.TimeZones
rm.UK: s.Symbols
rm.UK: s.Calendar
rm.UK: s.Tables
rm.UK: s.DateTime
rm.UK: s.Transform
rm.UK: s.tail
