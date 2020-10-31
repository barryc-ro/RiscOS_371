# Makefile for CDFSFiler
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name   Description
# ----       ----   -----------
# 25-May-94  AMcC   Created.
# 27-Feb-95  AMcC   Resources now copied to CDFSRes
#

#
# Program specific options:
#
COMPONENT = CDFSFiler
SOURCE    = s.CDFSFiler
TARGET    = rm.CDFSFiler
RDIR      = Resources
LDIR      = ${RDIR}.${LOCALE}
RESDIR    = ^.CDFSRes.Resources.${Locale}.Resources.${COMPONENT}

#
# Generic options:
#
MKDIR    = cdir
AS       = aasm
CP       = copy
RM       = remove

CFLAGS   = -c -depend !Depend -IC:
AFLAGS   = -depend !Depend -Stamp -quit -module
CPFLAGS  = ~cfr~v

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

resources:
        @echo ${COMPONENT}: Resources are in CDFSRes

clean:
        ${RM} ${TARGET}
        @echo ${COMPONENT}: cleaned

${TARGET}: ${SOURCE}
        ${AS} ${AFLAGS} -To $@ -From ${SOURCE}

# Dynamic dependencies:
rm.CDFSFiler: Hdr:ListOpts
rm.CDFSFiler: Hdr:Macros
rm.CDFSFiler: Hdr:System
rm.CDFSFiler: Hdr:SWIs
rm.CDFSFiler: Hdr:CPU.Generic26
rm.CDFSFiler: Hdr:IO.GenericIO
rm.CDFSFiler: Hdr:RISCOS
rm.CDFSFiler: Hdr:ModHand
rm.CDFSFiler: Hdr:FSNumbers
rm.CDFSFiler: Hdr:HighFSI
rm.CDFSFiler: Hdr:NewErrors
rm.CDFSFiler: Hdr:Wimp
rm.CDFSFiler: Hdr:WimpSpace
rm.CDFSFiler: Hdr:Messages
rm.CDFSFiler: Hdr:Sprite
rm.CDFSFiler: Hdr:VduExt
rm.CDFSFiler: Hdr:Variables
rm.CDFSFiler: Hdr:Proc
rm.CDFSFiler: Hdr:Services
rm.CDFSFiler: Hdr:ShareD
rm.CDFSFiler: Hdr:MsgMenus
rm.CDFSFiler: Hdr:MsgTrans
rm.CDFSFiler: Hdr:ResourceFS
rm.CDFSFiler: Hdr:CDROM
rm.CDFSFiler: Hdr:CDErrors
rm.CDFSFiler: Hdr:CDFS
rm.CDFSFiler: Hdr:Hourglass
rm.CDFSFiler: Hdr:HostFS
rm.CDFSFiler: Hdr:NdrDebug
rm.CDFSFiler: Hdr:DDVMacros
rm.CDFSFiler: hdr.Icons
rm.CDFSFiler: Version
