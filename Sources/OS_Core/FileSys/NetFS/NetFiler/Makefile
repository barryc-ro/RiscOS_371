# Makefile for NetFiler
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
COMPONENT = NetFiler
SOURCE    = s.NetFiler
TARGET    = rm.NetFiler

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
rm.NetFiler: Version
rm.NetFiler: Hdr:ListOpts
rm.NetFiler: Hdr:Macros
rm.NetFiler: Hdr:System
rm.NetFiler: Hdr:SWIs
rm.NetFiler: Hdr:CPU.Generic26
rm.NetFiler: Hdr:IO.GenericIO
rm.NetFiler: Hdr:RISCOS
rm.NetFiler: Hdr:CMOS
rm.NetFiler: Hdr:ModHand
rm.NetFiler: Hdr:FSNumbers
rm.NetFiler: Hdr:HighFSI
rm.NetFiler: Hdr:NewErrors
rm.NetFiler: Hdr:PublicWS
rm.NetFiler: Hdr:Wimp
rm.NetFiler: Hdr:WimpSpace
rm.NetFiler: Hdr:Messages
rm.NetFiler: Hdr:Sprite
rm.NetFiler: Hdr:VduExt
rm.NetFiler: Hdr:Econet
rm.NetFiler: Hdr:Proc
rm.NetFiler: Hdr:Services
rm.NetFiler: Hdr:Variables
rm.NetFiler: Hdr:MsgTrans
rm.NetFiler: Hdr:MsgMenus
rm.NetFiler: Hdr:ResourceFS
rm.NetFiler: Hdr:NDRDebug
