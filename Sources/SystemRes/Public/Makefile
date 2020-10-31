# Makefile for Public
# 
# Public directory created by top-level Makefile
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name   Description
# ----       ----   -----------
# 09-Jan-95  AMcC   Created
# 23-Mar-95  AMcC   Directory access set to WR/wr
#

#
# Program specific options:
#
COMPONENT  = Public

# Generic options:
#
MKDIR   = cdir
CP      = copy
RM      = remove
WIPE    = -wipe

CPFLAGS = ~cfr~v
WFLAGS  = ~c~v

FILES=

#
# Main rules:
#
all: ${FILES}
        @echo ${COMPONENT}: All built (Disc)

install: ${FILES}
        Access ${INSTDIR} WR/wr
        @echo ${COMPONENT}: All installed (Disc)

clean:
        @echo ${COMPONENT}: cleaned

#---------------------------------------------------------------------------
# Dynamic dependencies:
