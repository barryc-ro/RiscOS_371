# Makefile for ADFSFiler
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
COMPONENT = ADFSFiler
SOURCE    = s.ADFSFiler
TARGET    = rm.ADFSFiler

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
        ${CP} Resources.${LOCALE}.Templates ${RESDIR}.${COMPONENT}.Templates ${CPFLAGS}
        @echo ${COMPONENT}: resource files copied

${TARGET}: ${SOURCE}
        ${AS} ${ASFLAGS} ${SOURCE}

# Dynamic dependencies:
rm.ADFSFiler: Hdr:ListOpts
rm.ADFSFiler: Hdr:Macros
rm.ADFSFiler: Hdr:System
rm.ADFSFiler: Hdr:SWIs
rm.ADFSFiler: Hdr:CPU.Generic26
rm.ADFSFiler: Hdr:IO.GenericIO
rm.ADFSFiler: Hdr:RISCOS
rm.ADFSFiler: Hdr:ModHand
rm.ADFSFiler: Hdr:CMOS
rm.ADFSFiler: Hdr:FSNumbers
rm.ADFSFiler: Hdr:HighFSI
rm.ADFSFiler: Hdr:NewErrors
rm.ADFSFiler: Hdr:Wimp
rm.ADFSFiler: Hdr:WimpSpace
rm.ADFSFiler: Hdr:Messages
rm.ADFSFiler: Hdr:Sprite
rm.ADFSFiler: Hdr:VduExt
rm.ADFSFiler: Hdr:Variables
rm.ADFSFiler: Hdr:Proc
rm.ADFSFiler: Hdr:Services
rm.ADFSFiler: Hdr:MsgTrans
rm.ADFSFiler: Hdr:MsgMenus
rm.ADFSFiler: Hdr:ADFS
rm.ADFSFiler: Hdr:Territory
rm.ADFSFiler: Hdr:FileCore
rm.ADFSFiler: Hdr:MultiFS
rm.ADFSFiler: Hdr:UpCall
rm.ADFSFiler: Hdr:ResourceFS
rm.ADFSFiler: Hdr:ShareD
rm.ADFSFiler: Hdr:ExtraLong
rm.ADFSFiler: Version
rm.ADFSFiler: Hdr:NdrDebug
rm.ADFSFiler: s.Format
rm.ADFSFiler: s.Backup
