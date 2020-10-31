# Makefile for Desktop
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
COMPONENT = Desktop
SOURCE    = s.Desktop
TARGET    = rm.Desktop

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

resources:
        ${MKDIR} ${RESDIR}.${COMPONENT}
        ${CP} Resources.${LOCALE}.Messages  ${RESDIR}.${COMPONENT}.Messages  ${CPFLAGS}
        ${CP} Resources.${LOCALE}.Templates  ${RESDIR}.${COMPONENT}.Templates  ${CPFLAGS}
        @echo ${COMPONENT}: resource files copied

${TARGET}: ${SOURCE}
        ${AS} ${ASFLAGS} ${SOURCE}

# Dynamic dependencies:
rm.Desktop: Hdr:ListOpts
rm.Desktop: Hdr:Macros
rm.Desktop: Hdr:System
rm.Desktop: Hdr:SWIs
rm.Desktop: Hdr:CPU.Generic26
rm.Desktop: Hdr:IO.GenericIO
rm.Desktop: Hdr:RISCOS
rm.Desktop: Hdr:ModHand
rm.Desktop: Hdr:Services
rm.Desktop: Hdr:CMOS
rm.Desktop: Hdr:Proc
rm.Desktop: Hdr:FSNumbers
rm.Desktop: Hdr:HighFSI
rm.Desktop: Hdr:LowFSi
rm.Desktop: Hdr:NewErrors
rm.Desktop: Hdr:Variables
rm.Desktop: Hdr:Wimp
rm.Desktop: Hdr:WimpSpace
rm.Desktop: Hdr:Messages
rm.Desktop: Hdr:ResourceFS
rm.Desktop: Hdr:MsgTrans
rm.Desktop: Hdr:Font
rm.Desktop: Hdr:Draw
rm.Desktop: Hdr:ColourTran
rm.Desktop: Version
rm.Desktop: Hdr:NDRDebug
