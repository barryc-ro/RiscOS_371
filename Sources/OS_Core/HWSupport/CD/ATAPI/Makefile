# Makefile for the ATAPI Driver module
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name   Description
# ----       ----   -----------
# 07-Dec-94  AMcC   Created.
# 03-Jan-95  AMcC   Now exports hdr.ATAPI
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
COMPONENT = ATAPI
EXPORTS   = ${EXP_HDR}.ATAPI
SOURCE    = s.Main
TARGET    = rm.ATAPI
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

${EXP_HDR}.ATAPI: hdr.ATAPI
        ${CP} hdr.ATAPI $@ ${CPFLAGS}

# Dynamic dependencies:
rm.ATAPI: Version
rm.ATAPI: hdr.Hashes
rm.ATAPI: hdr.IDEdefs
rm.ATAPI: hdr.Macros
rm.ATAPI: hdr:ListOpts
rm.ATAPI: hdr:CMOS
rm.ATAPI: s.DriverCode
rm.ATAPI: s.ATAPIStuff
rm.ATAPI: s.Extras
rm.ATAPI: s.OnError
rm.ATAPI: s.Module
rm.ATAPI: s.Variables
rm.ATAPI: s.Strings
