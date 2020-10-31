# Makefile for Mbuf Manager (imported objects)
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name   Description
# ----       ----   -----------
# 21-Nov-94  AMcC   Created
#

#
# Component specific options:
#
COMPONENT  = MManager
ROM_MODULE = rm.MManager
#
# Generic options:
#
MKDIR   = cdir
CP      = copy
LD      = link
RM      = remove
WIPE    = -wipe

CPFLAGS = ~cfr~v
WFLAGS  = ~c~v

#
# Main rules:
#
#
install_rom: ${ROM_MODULE}
        ${CP} ${ROM_MODULE} ${INSTDIR}.${COMPONENT} ${CPFLAGS}
        @echo ${COMPONENT}: Module installed (ROM)

#---------------------------------------------------------------------------
# Dynamic dependencies:
