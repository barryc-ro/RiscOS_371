# Makefile for Verify
#

#
# Program specific options:
#
COMPONENT  = Verify
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
 $(RDIR).!Sprites\
 $(RDIR).!Sprites22

#
# GENERIC RULES
#                  
all: $(FILES)
          @echo $(COMPONENT): all build complete

install: $(FILES)
         $(MKDIR) $(INSTDIR)
         Set Alias$CPFD $(CP) %0.%1 $(INSTDIR).%1 $(CPFLAGS)
         CPFD $(LDIR) !Help
         CPFD $(LDIR) !Run
         CPFD $(RDIR) !RunImage
         CPFD $(RDIR) !Sprites
         CPFD $(RDIR) !Sprites22
         Unset Alias$CPFD
         Access $(INSTDIR) /r
         Access $(INSTDIR).* LR/r
         @echo $(COMPONENT): installed

clean:
         @echo $(COMPONENT): cleaned

#---------------------------------------------------------------------------
# Dynamic dependencies:
