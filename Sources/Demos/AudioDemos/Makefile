# Makefile for AudioDemos
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name   Description
# ----       ----   -----------
# 13-Mar-95  AMcC   Created.
#

#
# Program specific options:
#
COMPONENT  = AudioDemos
INSTDIR    = ${INSTDIR}.${COMPONENT}
LDIR       = ${LOCALE}

# Generic options:
#
MKDIR   = cdir
CP      = copy
RM      = remove
WIPE    = -wipe

CPFLAGS = ~cfr~v
WFLAGS  = ~c~v

ARMOVIE =\
 ARMovie.Applause \
 ARMovie.Blues \
 ARMovie.Drum+Cym\
 ARMovie.G2 \
 ARMovie.Minor \
 ARMovie.Piano \
 ARMovie.Sax3 \
 ARMovie.Space \
 ARMovie.Trumpet

WAVEFORM =\
 WaveForm.Blast \
 WaveForm.Drum \
 WaveForm.HiHat \
 WaveForm.HiTom \
 WaveForm.RingBass

FILES = ${LDIR}.Readme ${ARMOVIE} ${WAVEFORM}

#
# GENERIC RULES
#                  
all: ${FILES}
        @echo $(COMPONENT): all build complete

install: ${FILES}
        ${MKDIR} ${INSTDIR}
        |
        ${CP} ${LDIR}.Readme ${INSTDIR}.Readme $(CPFLAGS)
        $(CP) ARMovie.*  $(INSTDIR).* $(CPFLAGS)
        $(CP) WaveForm.* $(INSTDIR).* $(CPFLAGS)
        |
        Access ${INSTDIR} /r
        Access ${INSTDIR}.* WR/r
        |
        @echo $(COMPONENT): installed

clean:
        @echo $(COMPONENT): cleaned

#---------------------------------------------------------------------------
# Dynamic dependencies:
