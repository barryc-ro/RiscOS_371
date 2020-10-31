# Makefile for PartNumber
# 
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name   Description
# ----       ----   -----------
# 12-Jan-95  AMcC   Created
#

#
# Program specific options:
#
COMPONENT  = PartNumber
LDIR       = ${LOCALE}
INSTDIR    = ${INSTDIR}
#PART      = ...set by calling makefile/obey file

# Generic options:
#
MKDIR   = cdir
CP      = copy
RM      = remove
WIPE    = -wipe

CPFLAGS = ~cfr~v
WFLAGS  = ~c~v

FILES = 

#
# Main rules:
#
all: ${FILES}
        @echo ${COMPONENT}: All built (Disc)

install: install_${PART}

install_HardDisc: ${FILES}
        ${CP} ${LDIR}.${PART}.PartNumber ${INSTDIR}.PartNumber ${CPFLAGS}
        Access ${INSTDIR}.PartNumber LR/r
        @echo ${COMPONENT}: All installed (HardDisc)

clean:
        @echo ${COMPONENT}: cleaned

#---------------------------------------------------------------------------
# Dynamic dependencies:
