# Makefile for Tutorials
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name   Description
# ----       ----   -----------
# 18-Nov-94  AMcC   Updated for Black build
# 09-Dec-94  AMcC   Install StarComms in tutorial directory
#

#
# COMPONENT specific options:
#
COMPONENT  = Tutorials
APP        = !${COMPONENT}
LDIR       = ${LOCALE}

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

FILES=\
 $(LDIR).DrawTutor.Horse\
 $(LDIR).DrawTutor.LakeView\
 $(LDIR).DrawTutor.Map\
 $(LDIR).DrawTutor.MapText\
 $(LDIR).DrawTutor.Sign\
 $(LDIR).PaintTutor.Flower\
 $(LDIR).ReadMe\
 $(LDIR).StarComms\
 $(LDIR).WelcomeGde.DrawDemo

#
# GENERIC RULES
#                  
all: $(FILES)
          @echo $(COMPONENT): all build complete

install: $(FILES)
         Set Alias$CPFD $(CP) %0.%1 $(INSTDIR).%1 $(CPFLAGS)
         |
         $(MKDIR) $(INSTDIR).DrawTutor
         CPFD  $(LDIR) DrawTutor.Horse
         CPFD  $(LDIR) DrawTutor.LakeView
         CPFD  $(LDIR) DrawTutor.Map
         CPFD  $(LDIR) DrawTutor.MapText
         CPFD  $(LDIR) DrawTutor.Sign
         $(MKDIR) $(INSTDIR).PaintTutor
         CPFD  $(LDIR) PaintTutor.Flower
         CPFD  $(LDIR) ReadMe
         CPFD  $(LDIR) StarComms
         $(MKDIR) $(INSTDIR).WelcomeGde
         CPFD  $(LDIR) WelcomeGde.DrawDemo
         |
         Unset Alias$CPFD
         |
         -attr -directories +wr ${INSTDIR}
         -attr -files -ol +or +ow +wr -ww ${INSTDIR}
         |
         @echo $(COMPONENT): installed

clean:
         @echo $(COMPONENT): cleaned

#---------------------------------------------------------------------------
# Dynamic dependencies:
