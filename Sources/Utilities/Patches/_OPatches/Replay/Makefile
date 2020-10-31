# Makefile for Replay Patch
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name   Description
# ----       ----   -----------
# 21-Nov-94  AMcC   Updated for Black build
#

#
# Program specific options:
#
COMPONENT  = Replay_Patch

# Generic options:
#
ATTR    = -attr
CP      = copy
MKDIR   = cdir
RM      = remove
WIPE    = -wipe
CPFLAGS = ~cfr~v
WFLAGS  = ~c~v

FILES  =\
 ReadMe\
 SoundDMA.!Run\
 SoundDMA.NewSound\
 SoundDMA.SoundDMA\
 Video.ReadMe

#
# GENERIC RULES
#                  
all: ${FILES}
        @echo ${COMPONENT}: all build complete

install: ${FILES}
        ${CP} ReadMe   ${INSTDIR}.ReadMe   ${CPFLAGS}
        ${CP} SoundDMA ${INSTDIR}.SoundDMA ${CPFLAGS}
        |
        ${ATTR} -directories +wr ${INSTDIR}
        ${ATTR} -files +or +ow +wr -ww ${INSTDIR}
        |
        ${MKDIR} ${INSTDIR}.^.^.^.Video
        ${CP} Video.ReadMe ${INSTDIR}.^.^.^.Video.ReadMe ${CPFLAGS}
        |
        ${ATTR} -directories +wr ${INSTDIR}.^.^.^.Video
        ${ATTR} -files +or +ow +wr -ww ${INSTDIR}.^.^.^.Video
        |
        @echo ${COMPONENT}: installed

#---------------------------------------------------------------------------
# Dynamic dependencies:
