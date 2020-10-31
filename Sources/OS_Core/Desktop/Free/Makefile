# Makefile for FreeSpace
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name         Description
# ----       ----         -----------
# 25-May-94  AMcC         Created.
#

#
# Paths
#
EXP_HDR = <export$dir>

#
# Generic options:
#
MKDIR   = cdir
AS      = aasm
CP      = copy
RM      = remove
CCFLAGS = -c -depend !Depend -IC:
ASFLAGS = -depend !Depend -Stamp -quit -module
CPFLAGS = ~cfr~v

#
# Program specific options:
#
COMPONENT = Free
SOURCE    = s.Free
TARGET    = rm.Free
EXPORTS   = ${EXP_HDR}.Free

#
# Generic rules:
#
rom: ${TARGET}
        @echo ${COMPONENT}: rom module built

install_rom: ${TARGET}
        ${CP} ${TARGET} ${INSTDIR}.${COMPONENT} ${CPFLAGS}
        @echo ${COMPONENT}: rom module installed

clean:
        ${RM} ${TARGET}
        @echo ${COMPONENT}: cleaned

export: ${EXPORTS}
        @echo ${COMPONENT}: export complete

resources:
        ${MKDIR} ${RESDIR}.${COMPONENT}
        ${CP} Resources.${LOCALE}.Messages  ${RESDIR}.${COMPONENT}.Messages  ${CPFLAGS}
        ${CP} Resources.${LOCALE}.Templates ${RESDIR}.${COMPONENT}.Templates ${CPFLAGS}
        @echo ${COMPONENT}: resource files copied

${TARGET}: ${SOURCE}
        ${AS} ${ASFLAGS} -To $@ -From ${SOURCE}

${EXP_HDR}.Free: hdr.Free
        ${CP} hdr.Free $@ ${CPFLAGS}

# Dynamic dependencies:
rm.Free: Hdr:ListOpts
rm.Free: Hdr:Macros
rm.Free: Hdr:System
rm.Free: Hdr:SWIs
rm.Free: Hdr:CPU.Generic26
rm.Free: Hdr:IO.GenericIO
rm.Free: Hdr:RISCOS
rm.Free: Hdr:ModHand
rm.Free: Hdr:Services
rm.Free: Hdr:VduExt
rm.Free: Hdr:FSNumbers
rm.Free: Hdr:HighFSI
rm.Free: Hdr:NewErrors
rm.Free: Hdr:Variables
rm.Free: Hdr:Proc
rm.Free: Hdr:Sprite
rm.Free: Hdr:Wimp
rm.Free: Hdr:WimpSpace
rm.Free: Hdr:Messages
rm.Free: Hdr:FilerAct
rm.Free: Hdr:CMOS
rm.Free: Hdr:MsgTrans
rm.Free: Hdr:MsgMenus
rm.Free: Hdr:ResourceFS
rm.Free: Hdr:ColourTran
rm.Free: Hdr:Hourglass
rm.Free: Hdr:ADFS
rm.Free: Hdr:RamFS
rm.Free: Hdr:SCSIFS
rm.Free: Hdr:Econet
rm.Free: Hdr:PCCardFS
rm.Free: Hdr:UpCall
rm.Free: Hdr:HostFS
rm.Free: Hdr:NdrDebug
rm.Free: Hdr:ExtraLong
rm.Free: Version
rm.Free: s.ModHead
rm.Free: s.StartLoop
rm.Free: s.Messages
rm.Free: s.ADFS
rm.Free: s.RAMFS
rm.Free: s.SCSI
rm.Free: s.NETFS
rm.Free: s.NFS
rm.Free: s.PCCardFS
rm.Free: s.SWIs
rm.Free: s.Tail
