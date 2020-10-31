# Makefile for HForm
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
COMPONENT  = HForm
APP        = !${COMPONENT}
RDIR       = Resources
LDIR       = ${RDIR}.${LOCALE}
INSTDIR    = ${INSTDIR}.${APP}

# Generic options:
#
MKDIR   = cdir
CP      = copy
RM      = remove
SQUISH  = squish
WIPE    = -wipe

CPFLAGS = ~cfr~v
SQFLAGS = -nolist
WFLAGS  = ~c~v

FILES  =\
 $(LDIR).!Run\
 $(LDIR).!Help\
 $(RDIR).!RunImage\
 $(LDIR).!Sprites\
 $(LDIR).!Sprites22\
 $(LDIR).Messages

#
# Generic build rules:
#
all: $(FILES)
     @echo $(COMPONENT): all build complete

install: $(FILES)
         $(MKDIR) $(INSTDIR)
         |
         ${CP} $(LDIR).!Run        ${INSTDIR}.!Run       ${CPFLAGS}
         ${CP} $(LDIR).!Help       ${INSTDIR}.!Help      ${CPFLAGS}
         ${CP} $(RDIR).!RunImage   ${INSTDIR}.!RunImage  ${CPFLAGS}
         ${CP} $(LDIR).!Sprites    ${INSTDIR}.!Sprites   ${CPFLAGS}
         ${CP} $(LDIR).!Sprites22  ${INSTDIR}.!Sprites22 ${CPFLAGS}
         ${CP} $(LDIR).Messages    ${INSTDIR}.Messages   ${CPFLAGS}
         |
         Access ${INSTDIR} /r
         Access ${INSTDIR}.* LR/r
         |
         @echo $(COMPONENT): installed

clean:
       $(RM) $(RDIR).!RunImage
       $(RM) crunched.!RunImage
       @echo $(COMPONENT): cleaned

#
# Static dependencies:
#
$(RDIR).!RunImage: crunched.!RunImage
        $(SQUISH) $(SQFLAGS) -keep bas.Keep -from crunched.!RunImage -to $@

crunched.!RunImage: bas.!RunImage
        crunch.!RunImage; BASIC

#---------------------------------------------------------------------------
# Dynamic dependencies:
