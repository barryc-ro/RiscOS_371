# Makefile for ARPlayer
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name   Description
# ----       ----   -----------
# 17-Nov-94  AMcC   Updated for Black build
#

#
# Program specific options:
#
COMPONENT  = ARPlayer
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
 $(RDIR).!Boot\
 $(LDIR).!Run\
 $(RDIR).!State\
 $(RDIR).!RunImage\
 $(RDIR).!Sprites\
 $(RDIR).!Sprites22\
 $(RDIR).Dummy\
 $(LDIR).messages\
 $(RDIR).ReplaySpt\
 $(LDIR).Template2D\
 $(LDIR).Templates

#
# GENERIC RULES
#                  
all: $(FILES)
        @echo $(COMPONENT): all build complete

install: $(FILES)
        Set Alias$CPFD $(CP) %0.%1 $(INSTDIR).%1 $(CPFLAGS)
        Set Alias$CPFDL CPFD %*0|MAccess $(INSTDIR).%1 LR/r
        |
        $(MKDIR) $(INSTDIR); Access $(INSTDIR) /r
        |
        CPFDL $(LDIR) !Help
        CPFDL $(RDIR) !Boot
        CPFDL $(LDIR) !Run
        CPFD  $(RDIR) !State
        CPFDL $(RDIR) !RunImage
        CPFDL $(RDIR) !Sprites
        CPFDL $(RDIR) !Sprites22
        CPFDL $(RDIR) Dummy
        CPFDL $(LDIR) Messages
        CPFDL $(RDIR) ReplaySpt
        CPFDL $(LDIR) Template2D
        CPFDL $(LDIR) Templates
        |
        Unset Alias$CPFDL
        Unset Alias$CPFD
        |
        @echo $(COMPONENT): installed

clean:
         @echo $(COMPONENT): cleaned

#---------------------------------------------------------------------------
# Dynamic dependencies:
