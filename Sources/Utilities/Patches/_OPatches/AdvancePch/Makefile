# Makefile for Advance Patch
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
COMPONENT  = AdvancePch
APP        = !AdvanceWP
RDIR       = Resources
LDIR       = ${RDIR}.${LOCALE}
INSTDIR    = ${INSTDIR}.AdvancePch

# Generic options:
#
CP      = copy
MKDIR   = cdir
RM      = remove
WIPE    = -wipe
CPFLAGS = ~cfr~v
WFLAGS  = ~c~v


FILES  =\
 $(LDIR).ReadMe\
 $(RDIR).!RunImage\
 $(LDIR).Resources.UK

#
# GENERIC RULES
#                  
all: $(FILES)
        @echo $(COMPONENT): all build complete

install: $(FILES)
        $(MKDIR) $(INSTDIR)
        $(MKDIR) $(INSTDIR).$(APP)
        $(MKDIR) $(INSTDIR).$(APP).Resources
        |
        $(CP) $(LDIR).ReadMe $(INSTDIR).ReadMe $(CPFLAGS)
        $(CP) $(RDIR).!RunImage $(INSTDIR).$(APP).!RunImage $(CPFLAGS)
        $(CP) $(LDIR).Resources.UK $(INSTDIR).$(APP).Resources.UK $(CPFLAGS)
        |
        -attr -directories +wr ${INSTDIR}
        -attr -files +or +ow +wr -ww ${INSTDIR}
        |
        @echo $(COMPONENT): installed

clean:
        @echo $(COMPONENT): cleaned

#---------------------------------------------------------------------------
# Dynamic dependencies:
