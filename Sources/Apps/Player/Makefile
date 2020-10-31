# Makefile for installing ESP's Player
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name   Description
# ----       ----   -----------
# 09-Mar-94  AMcC   Created
#

#
# Program specific options:
#
COMPONENT  = Player
APP        = !${COMPONENT}
RDIR       = Resources
LDIR       = ${RDIR}.${LOCALE}
INSTDIR    = ${INSTDIR}.${APP}

# Generic options:
#
MKDIR   = cdir
CP      = copy
RM      = remove
WIPE    = -wipe

CPFLAGS = ~cfr~v
WFLAGS  = ~c~v

FILES  =\
 $(RDIR).!Boot\
 $(LDIR).!Help\
 $(LDIR).!Run\
 $(RDIR).!RunImage\
 $(RDIR).!Sprites\
 $(RDIR).!Sprites22\
 $(LDIR).Messages\
 $(RDIR).Player\
 $(RDIR).Sprites\
 $(RDIR).Sprites\
 $(LDIR).Templates

#
# GENERIC RULES
#
all: $(FILES)
     @echo $(COMPONENT): all built

install: $(FILES)
         $(MKDIR) ${INSTDIR}
         |
         $(CP) $(RDIR).!Boot      $(INSTDIR).!Boot       $(CPFLAGS)
         $(CP) $(LDIR).!Help      $(INSTDIR).!Help       $(CPFLAGS)
         $(CP) $(LDIR).!Run       $(INSTDIR).!Run        $(CPFLAGS)
         $(CP) $(RDIR).!RunImage  $(INSTDIR).!RunImage   $(CPFLAGS)
         $(CP) $(RDIR).!Sprites   $(INSTDIR).!Sprites    $(CPFLAGS)
         $(CP) $(RDIR).!Sprites22 $(INSTDIR).!Sprites22  $(CPFLAGS)
         $(CP) $(LDIR).Messages   $(INSTDIR).Messages    $(CPFLAGS)
         $(CP) $(RDIR).Player     $(INSTDIR).Player      $(CPFLAGS)
         $(CP) $(RDIR).Sprites    $(INSTDIR).Sprites     $(CPFLAGS)
         $(CP) $(RDIR).Sprites22  $(INSTDIR).Sprites22   $(CPFLAGS)
         $(CP) $(LDIR).Templates  $(INSTDIR).Templates   $(CPFLAGS)
         |
         Access ${INSTDIR} /r
         Access ${INSTDIR}.* WR/r
         |
         @echo $(COMPONENT): installed

clean:
        @echo $(COMPONENT): cleaned

#
# Static dependencies:
#

#---------------------------------------------------------------------------
# Dynamic dependencies:
