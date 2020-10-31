# Makefile for RAMFSFiler
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
COMPONENT = RAMFSFiler
SOURCE    = s.RAMFSFiler
TARGET    = rm.RAMFSFiler

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
rm.RAMFSFiler: Hdr:ListOpts
rm.RAMFSFiler: Hdr:Macros
rm.RAMFSFiler: Hdr:System
rm.RAMFSFiler: Hdr:SWIs
rm.RAMFSFiler: Hdr:CPU.Generic26
rm.RAMFSFiler: Hdr:IO.GenericIO
rm.RAMFSFiler: Hdr:RISCOS
rm.RAMFSFiler: Hdr:ModHand
rm.RAMFSFiler: Hdr:FSNumbers
rm.RAMFSFiler: Hdr:HighFSI
rm.RAMFSFiler: Hdr:NewErrors
rm.RAMFSFiler: Hdr:Wimp
rm.RAMFSFiler: Hdr:WimpSpace
rm.RAMFSFiler: Hdr:Messages
rm.RAMFSFiler: Hdr:Sprite
rm.RAMFSFiler: Hdr:VduExt
rm.RAMFSFiler: Hdr:Proc
rm.RAMFSFiler: Hdr:Services
rm.RAMFSFiler: Hdr:Variables
rm.RAMFSFiler: Hdr:MsgTrans
rm.RAMFSFiler: Hdr:MsgMenus
rm.RAMFSFiler: Hdr:ResourceFS
rm.RAMFSFiler: Version
rm.RAMFSFiler: Hdr:HostFS
rm.RAMFSFiler: Hdr:Debug
rm.RAMFSFiler: s.MsgCode
