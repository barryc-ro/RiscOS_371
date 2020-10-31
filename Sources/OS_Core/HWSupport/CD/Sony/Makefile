# Makefile for the Sony Driver module
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name         Description
# ----       ----         -----------
# 25-May-94  AMcC         Created.
# 23-Feb-95  AMcC   Resources now copied to CDFSRes
#

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
COMPONENT = Sony
SOURCE    = s.Main
TARGET    = rm.Sony
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

# Dynamic dependencies:
rm.Sony: Version
rm.Sony: hdr.Hashes
rm.Sony: hdr.Macros
rm.Sony: s.Strings
rm.Sony: s.DriverCode
rm.Sony: s.Extras
rm.Sony: s.OnError
rm.Sony: s.Module
rm.Sony: s.Variables
