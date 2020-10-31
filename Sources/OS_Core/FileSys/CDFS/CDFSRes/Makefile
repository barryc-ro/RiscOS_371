# Makefile for CDFS Resources Module
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name         Description
# ----       ----         -----------
# 23-Feb-95  AMcC         Created.
#

#
# Generic options:
#
CP       = copy
MKDIR    = cdir
MODGEN   = modgen
MODSQZ   = modsqz
RM       = remove
SCANRES  = scanres
WIPE    = -wipe

CPFLAGS  = ~cfr~v
WFLAGS  = ~cr~v

#
# Program specific options:
#
COMPONENT   = CDFSRes
VERSION     = 2.34
TARGET      = rm.CDFSRes
MODULE_HELP = "CDFSResources"
MODULE_NAME = CDFSResources
FILELIST    = Resources.${LOCALE}.List

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

${TARGET}: ${FILELIST}
        ${MODGEN} $@ ${MODULE_NAME} ${MODULE_HELP} ${VERSION} -via ${FILELIST}

# Dynamic dependencies:
