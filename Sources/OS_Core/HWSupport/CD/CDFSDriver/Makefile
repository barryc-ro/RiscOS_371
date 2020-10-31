# Makefile for CDFS Driver
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name   Description
# ----       ----   -----------
# 25-May-94  AMcC   Created.
# 23-Feb-95  AMcC   Resources now copied to CDFSRes
#

#
# Paths
#
EXP_HDR = <export$dir>

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
# Program specific options:
#
COMPONENT = CDFSDriver
EXPORTS   = ${EXP_HDR}.CDROM ${EXP_HDR}.CDErrors
SOURCE    = s.Main
TARGET    = rm.CDFSDriver
RDIR      = Resources
LDIR      = ${RDIR}.${LOCALE}
CDFSRES   = <src$dir>.OS_Core.FileSys.CDFS.CDFSRes
RESDIR    = ${CDFSRES}.Resources.${Locale}.Resources.CDFSDriver.${COMPONENT}

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

resources:
        @echo ${COMPONENT}: Resources are in CDFSRes

clean:
        ${RM} ${TARGET}
        @echo ${COMPONENT}: cleaned

${TARGET}: ${SOURCE}
        ${AS} ${AFLAGS} -To $@ -From ${SOURCE}

${EXP_HDR}.CDROM: hdr.CDROM
        ${CP} hdr.CDROM $@ ${CPFLAGS}

${EXP_HDR}.CDErrors: hdr.CDErrors
        ${CP} hdr.CDErrors $@ ${CPFLAGS}

# Dynamic dependencies:
rm.CDFSDriver: Hdr:ListOpts
rm.CDFSDriver: Hdr:Macros
rm.CDFSDriver: Hdr:System
rm.CDFSDriver: Hdr:SWIs
rm.CDFSDriver: Hdr:CPU.Generic26
rm.CDFSDriver: Hdr:IO.GenericIO
rm.CDFSDriver: Hdr:RISCOS
rm.CDFSDriver: Hdr:SCSI
rm.CDFSDriver: Hdr:CDROM
rm.CDFSDriver: Hdr:MsgTrans
rm.CDFSDriver: Hdr:HostFS
rm.CDFSDriver: hdr.Hashes
rm.CDFSDriver: hdr.CDMacros
rm.CDFSDriver: Version
rm.CDFSDriver: S.Strings
rm.CDFSDriver: S.Tables
rm.CDFSDriver: S.Module
rm.CDFSDriver: S.Register
rm.CDFSDriver: S.Unregister
rm.CDFSDriver: S.Identify
rm.CDFSDriver: S.CD_Routs
rm.CDFSDriver: S.OnError
rm.CDFSDriver: S.ExtraBits
rm.CDFSDriver: S.ByteCopy
rm.CDFSDriver: S.Variables
