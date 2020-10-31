# Makefile for Sounds
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name   Description
# ----       ----   -----------
# 18-Nov-94  AMcC   Updated for Black build
#

#
# Program specific options:
#
COMPONENT  = Sounds

# Generic options:
#
MKDIR   = cdir
CP      = copy
RM      = remove
WIPE    = -wipe

CPFLAGS = ~cfr~v
WFLAGS  = ~c~v

ARMOVIE =\
 ARMovie.1812\
 ARMovie.Enigma

MAESTRO =\
 Maestro.BachFXVI\
 Maestro.Fanfare\
 Maestro.Gigue\
 Maestro.HandlMes1a\
 Maestro.HandlMes1B\
 Maestro.ShostF1

#
# GENERIC RULES
#                  
all: ${ARMOVIE} ${MAESTRO}
          @echo $(COMPONENT): all build complete

install: install_${INSTFLAG}
         Access ${INSTDIR}.* WR/r
         @echo $(COMPONENT): installed (${INSTFLAG})

install_all: install_armovie install_maestro; @

install_armovie: ${ARMOVIE}
         $(CP) ARMovie.1812 $(INSTDIR).1812 $(CPFLAGS)
         $(CP) ARMovie.Enigma $(INSTDIR).Enigma $(CPFLAGS)

install_maestro: ${MAESTRO}
         $(CP) Maestro.BachFXVI $(INSTDIR).BachFXVI $(CPFLAGS)
         $(CP) Maestro.Fanfare $(INSTDIR).Fanfare $(CPFLAGS)
         $(CP) Maestro.Gigue $(INSTDIR).Gigue $(CPFLAGS)
         $(CP) Maestro.HandlMes1a $(INSTDIR).HandlMes1a $(CPFLAGS)
         $(CP) Maestro.HandlMes1b $(INSTDIR).HandlMes1b $(CPFLAGS)
         $(CP) Maestro.ShostF1 $(INSTDIR).ShostF1 $(CPFLAGS)

clean:
         @echo $(COMPONENT): cleaned

#---------------------------------------------------------------------------
# Dynamic dependencies:
