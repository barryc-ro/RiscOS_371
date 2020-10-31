# Makefile for Videos
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name   Description
# ----       ----   -----------
# 18-Nov-94  AMcC   Updated for Black build
# 4-Sep-1995 J R C  Removed explicit file names
#

#
# Program specific options:
#
COMPONENT  = Videos
DDIR       = ARMovies
LDIR       = ${LOCALE}

# Generic options:
#
MKDIR   = cdir
CP      = copy
RM      = remove
WIPE    = -wipe

CPFLAGS = ~cfr~v
WFLAGS  = ~c~v

#
# GENERIC RULES
#                  
all:
          @echo $(COMPONENT): all build complete
#
# PROGRAM SPECIFIC RULES
#
install:
         $(CP) $(LDIR).ReadMe $(INSTDIR).ReadMe $(CPFLAGS)
         $(CP) $(DDIR) $(INSTDIR) $(CPFLAGS)
         Attr +or +ow +wr ${INSTDIR}
         @echo $(COMPONENT): installed

clean:
         @echo $(PROGRAM): cleaned

#---------------------------------------------------------------------------
# Dynamic dependencies:
