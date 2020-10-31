# Makefile for SCSIFiler
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
RM       = remove
TOKENISE = tokenise

CFLAGS   = -c -depend !Depend -IC:
AFLAGS   = -depend !Depend -Stamp -quit -module
CPFLAGS  = ~cfr~v

TOKENS   = Hdr:Tokens

#
# Program specific options:
#
COMPONENT = SCSIFiler
SOURCE    = s.SCSIFiler
TARGET    = rm.SCSIFiler

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

setdate:
        makedate
        ${AS} ${AFLAGS} -To ${TARGET} -From ${SOURCE}

${TARGET}: ${SOURCE}
        ${AS} ${AFLAGS} -To $@ -From ${SOURCE}

# Dynamic dependencies:
rm.SCSIFiler: hdr:ListOpts
rm.SCSIFiler: hdr:Macros
rm.SCSIFiler: hdr:System
rm.SCSIFiler: Hdr:SWIs
rm.SCSIFiler: Hdr:CPU.Generic26
rm.SCSIFiler: Hdr:IO.GenericIO
rm.SCSIFiler: Hdr:RISCOS
rm.SCSIFiler: hdr:ModHand
rm.SCSIFiler: hdr:FSNumbers
rm.SCSIFiler: hdr:HighFSI
rm.SCSIFiler: hdr:NewErrors
rm.SCSIFiler: hdr:Wimp
rm.SCSIFiler: hdr:WimpSpace
rm.SCSIFiler: hdr:Messages
rm.SCSIFiler: hdr:Sprite
rm.SCSIFiler: hdr:VduExt
rm.SCSIFiler: hdr:Proc
rm.SCSIFiler: hdr:Services
rm.SCSIFiler: hdr:SCSIFS
rm.SCSIFiler: hdr:FileCore
rm.SCSIFiler: Version
rm.SCSIFiler: hdr:Debug
rm.SCSIFiler: hdr:HostDebug
rm.SCSIFiler: s.format
