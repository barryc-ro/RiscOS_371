# Makefile for ArtWorks
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
COMPONENT  = ArtWorks
APP        = !AWViewer
RDIR       = Resources
LDIR       = ${RDIR}.${LOCALE}
README     = ReadMe


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

PICTURES =\
 Pictures.ACORN\
 Pictures.APPLE4\
 Pictures.BUTTERFLY2\
 Pictures.CLOWN\
 Pictures.CYCLAMEN\
 Pictures.DESISLAND\
 Pictures.FUNKYARROW\
 Pictures.FUNKYDF\
 Pictures.FUNKYSP\
 Pictures.FUNKYTF\
 Pictures.LADYFACE\
 Pictures.LAMP3\
 Pictures.MIDGET

FILES =\
 $(LDIR).$(README)\
 $(RDIR).!Boot\
 $(LDIR).!ReadMe\
 $(RDIR).!Run\
 $(RDIR).!RunImage\
 $(RDIR).!Sprites\
 $(RDIR).Grey\
 $(LDIR).LoadRMs\
 $(LDIR).Messages\
 $(RDIR).Primary\
 $(RDIR).Sprites\
 $(LDIR).StartUp\
 $(LDIR).Templates\
 $(RDIR).RMStore.AWRender\
 $(RDIR).RMStore.DitherExt\
 $(RDIR).RMStore.FontDraw\
 $(RDIR).RMStore.GDraw\
 $(RDIR).RMStore.ImageExtnd\
 $(PICTURES)

#
# GENERIC RULES
#                  
all: $(FILES)
          @echo $(COMPONENT): all build complete

install: $(FILES)
         ${MKDIR} ${INSTDIR}.${APP}
         |
         Set Alias$CPFD $(CP) %0.%1 $(INSTDIR).$(APP).%1 $(CPFLAGS)
         |
         CPFD $(RDIR) !Boot
         CPFD $(LDIR) !ReadMe
         CPFD $(RDIR) !Run
         CPFD $(RDIR) !RunImage
         CPFD $(RDIR) !Sprites
         CPFD $(RDIR) Grey
         CPFD $(LDIR) LoadRMs
         CPFD $(LDIR) Messages
         CPFD $(RDIR) Primary
         CPFD $(RDIR) Sprites
         CPFD $(LDIR) StartUp
         CPFD $(LDIR) Templates
         $(MKDIR) $(INSTDIR).$(APP).RMStore
         CPFD $(RDIR) RMStore.AWRender
         CPFD $(RDIR) RMStore.DitherExt
         CPFD $(RDIR) RMStore.FontDraw
         CPFD $(RDIR) RMStore.GDraw
         CPFD $(RDIR) RMStore.ImageExtnd
         |
         Set Alias$CPFD $(CP) %0.%1 $(INSTDIR).%1 $(CPFLAGS)
         |
         CPFD $(LDIR) $(README)
         CPFD Pictures ACORN
         CPFD Pictures APPLE4
         CPFD Pictures BUTTERFLY2
         CPFD Pictures CLOWN
         CPFD Pictures CYCLAMEN
         CPFD Pictures DESISLAND
         CPFD Pictures FUNKYARROW
         CPFD Pictures FUNKYDF
         CPFD Pictures FUNKYSP
         CPFD Pictures FUNKYTF
         CPFD Pictures LADYFACE
         CPFD Pictures LAMP3
         CPFD Pictures MIDGET
         |
         Unset Alias$CPFD
         |
         @echo $(COMPONENT): installed

clean:
         $(RM) $(RDIR).!RunImage
         @echo $(COMPONENT): cleaned

$(RDIR).!RunImage: bas.!RunImage
         ${SQUISH} ${SQFLAGS} -from bas.!RunImage -to $@

#---------------------------------------------------------------------------
# Dynamic dependencies:
