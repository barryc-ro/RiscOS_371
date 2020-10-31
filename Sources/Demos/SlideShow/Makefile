# Makefile for SlideShow
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
COMPONENT  = SlideShow
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
 $(LDIR).!Help\
 $(LDIR).!Run\
 $(RDIR).!RunImage\
 $(LDIR).!Sprites\
 $(LDIR).!Sprites22\
 $(LDIR).Messages\
 $(RDIR).Shell\
 $(LDIR).ShellMess\
 Data.Acorn\
 Data.Random\
 Data.RotSquare\
 Data.Slide

#
# GENERIC RULES
#
all: $(FILES)
     @echo $(COMPONENT): all build complete

install: $(FILES)
         $(MKDIR) ${INSTDIR}
         $(MKDIR) $(INSTDIR).Data
         $(CP) $(LDIR).!Help      $(INSTDIR).!Help       $(CPFLAGS)
         $(CP) $(LDIR).!Run       $(INSTDIR).!Run        $(CPFLAGS)
         $(CP) $(RDIR).!RunImage  $(INSTDIR).!RunImage   $(CPFLAGS)
         $(CP) $(LDIR).!Sprites   $(INSTDIR).!Sprites    $(CPFLAGS)
         $(CP) $(LDIR).!Sprites22 $(INSTDIR).!Sprites22  $(CPFLAGS)
         $(CP) $(LDIR).Messages   $(INSTDIR).Messages    $(CPFLAGS)
         $(CP) $(RDIR).Shell      $(INSTDIR).Shell       $(CPFLAGS)
         $(CP) $(LDIR).ShellMess  $(INSTDIR).ShellMess   $(CPFLAGS)
         $(CP) Data.Acorn         $(INSTDIR).Data.Acorn  $(CPFLAGS)
         $(CP) Data.Random        $(INSTDIR).Data.Random $(CPFLAGS)
         $(CP) Data.RotSquare     $(INSTDIR).Data.RotSquare $(CPFLAGS)
         $(CP) Data.Slide         $(INSTDIR).Data.Slide  $(CPFLAGS)
         -attr -directories +wr ${INSTDIR}
         -attr -files +or +ow +wr -ww ${INSTDIR}
         @echo $(COMPONENT): installed

clean:
        $(RM) Data.Slide
        $(RM) crunched.!RunImage
        $(RM) $(RDIR).!RunImage
        $(RM) $(RDIR).Shell
        @echo $(COMPONENT): cleaned

#
# Static dependencies:
#
Data.Slide: SlideGen
        SlideGen

$(RDIR).!RunImage: crunched.!RunImage
        $(SQUISH) $(SQFLAGS) -keep bas.Keep -from crunched.!RunImage -to $@

crunched.!RunImage: bas.!RunImage
        crunch.!RunImage; BASIC

$(RDIR).Shell: bas.Shell
        $(CP) bas.Shell $@ $(CPFLAGS)

#---------------------------------------------------------------------------
# Dynamic dependencies:
