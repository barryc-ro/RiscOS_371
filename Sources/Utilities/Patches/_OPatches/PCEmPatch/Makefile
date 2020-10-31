# Makefile for PCEmPatch
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
COMPONENT  = PCEmPatch
APP        = !PCEm
RDIR       = Resources
LDIR       = ${RDIR}.${LOCALE}
INSTDIR    = ${INSTDIR}.PCEmPatch

#
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
 $(LDIR).!Run\
 $(RDIR).!RunImage\
 $(RDIR).pcemmod\
 $(RDIR).!Choices\
 $(LDIR).Templates

#
# GENERIC RULES
#                  
all: $(FILES)
         @echo $(COMPONENT): all build complete

install: $(FILES)
        $(MKDIR) $(INSTDIR)
        $(MKDIR) $(INSTDIR).$(APP)
        |
        $(CP) $(LDIR).ReadMe    $(INSTDIR).ReadMe $(CPFLAGS)
        $(CP) $(LDIR).!Run      $(INSTDIR).$(APP).!Run $(CPFLAGS)
        $(CP) $(RDIR).!RunImage $(INSTDIR).$(APP).!RunImage $(CPFLAGS)
        $(CP) $(RDIR).pcemmod   $(INSTDIR).$(APP).pcemmod $(CPFLAGS)
        $(CP) $(RDIR).!Choices  $(INSTDIR).$(APP).!Choices $(CPFLAGS)
        $(CP) $(LDIR).Templates $(INSTDIR).$(APP).Templates $(CPFLAGS)
        |
        -attr -directories +wr ${INSTDIR}
        -attr -files +or +ow +wr -ww ${INSTDIR}
        |
        @echo $(COMPONENT): installed

clean:
        @echo $(COMPONENT): cleaned

#---------------------------------------------------------------------------
# Dynamic dependencies:
