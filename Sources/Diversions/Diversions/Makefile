# Makefile for Dversions (ReadMe etc)
# 
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name   Description
# ----       ----   -----------
# 30-Jan-95  AMcC   Created
#

#
# Program specific options:
#
COMPONENT  = Diversions
DDIR       = DataFiles
LDIR       = ${LOCALE}
INSTDIR    = ${INSTDIR}

# Generic options:
#
MKDIR   = cdir
CP      = copy
RM      = remove
WIPE    = -wipe

CPFLAGS = ~cfr~v
WFLAGS  = ~c~v

FILES =\
 ${LDIR}.ReadMe\
 ${DDIR}.Desktop

#
# Main rules:
#
all: ${FILES}
        @echo ${COMPONENT}: All built (Disc)

install: ${FILES}
        ${CP} ${LDIR}.ReadMe  ${INSTDIR}.ReadMe  ${CPFLAGS}
        ${CP} ${DDIR}.Desktop ${INSTDIR}.Desktop ${CPFLAGS}
        Access ${INSTDIR}.ReadMe WR/r
        Access ${INSTDIR}.Desktop WR/r
        @echo ${COMPONENT}: All installed (HardDisc)

clean:
        @echo ${COMPONENT}: cleaned

#---------------------------------------------------------------------------
# Dynamic dependencies:
