# Makefile for SparkFS Patch
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
COMPONENT  = SparkFS
RDIR       = Resources
LDIR       = ${RDIR}.${LOCALE}
INSTDIR    = ${INSTDIR}.SparkFS

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
 $(RDIR).SparkFS

#
# GENERIC RULES
#                  
all: $(FILES)
        @echo $(COMPONENT): all build complete

install: $(FILES)
        $(MKDIR) $(INSTDIR)
        |
        $(CP) $(LDIR).ReadMe  $(INSTDIR).ReadMe  $(CPFLAGS)
        $(CP) $(RDIR).SparkFS $(INSTDIR).SparkFS $(CPFLAGS)
        |
        Access ${INSTDIR} /r
        Access ${INSTDIR}.* WR/r
        |
        @echo $(COMPONENT): installed

clean:
        @echo $(COMPONENT): cleaned

#---------------------------------------------------------------------------
# Dynamic dependencies:
