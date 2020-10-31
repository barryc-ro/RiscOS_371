# Makefile for DDE Patch
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
COMPONENT  = DDE
RDIR       = Resources
LDIR       = ${RDIR}.${LOCALE}
INSTDIR    = ${INSTDIR}.DDE

# Generic options:
#
CP      = copy
MKDIR   = cdir
RM      = remove
WIPE    = -wipe
CPFLAGS = ~cfr~v
WFLAGS  = ~c~v

FILES  =\
 $(RDIR).MoveBoot\
 $(LDIR).ReadMe

ASSEMBLERFILES=\
 Assembler.!Installa.$(RDIR).!Boot\
 Assembler.!Installa.$(RDIR).!Run\
 Assembler.!Installa.$(LDIR).Templates\
 Assembler.!Installa.$(RDIR).!RunImage\
 Assembler.!Installa.$(RDIR).!Sprites\
 Assembler.!Installa.$(LDIR).!Help

CFILES=\
 C.$(LOCALE).Messages\
 C.!Installc.$(RDIR).!Boot\
 C.!Installc.$(RDIR).!Run\
 C.!Installc.$(LDIR).Templates\
 C.!Installc.$(RDIR).!RunImage\
 C.!Installc.$(RDIR).!Sprites\
 C.!Installc.$(LDIR).!Help


#
# GENERIC RULES
#                  
all: Assembler_all C_all
          @echo $(COMPONENT): all build complete

Assembler_all:
        @Dir assembler.!installa
        amu -f MakeFile
        squeeze $(RDIR).!RunImage
        @up 2

C_all:
        @Dir C.!installc
        amu -f MakeFile
        squeeze $(RDIR).!RunImage
        @up 2

Assembler_install: $(ASSEMBLERFILES)
        Set Alias$AssCPFD $(CP) Assembler.!installa.%0.%1 $(INSTDIR).Assembler.!Install.%1 $(CPFLAGS)
        |
        $(MKDIR) $(INSTDIR)
        $(MKDIR) $(INSTDIR).Assembler
        $(MKDIR) $(INSTDIR).Assembler.!Install
        AssCPFD $(RDIR) !Boot
        AssCPFD $(RDIR) !Run
        AssCPFD $(LDIR) Templates
        AssCPFD $(RDIR) !RunImage
        AssCPFD $(RDIR) !Sprites
        AssCPFD $(LDIR) !Help
        |
        Unset Alias$AssCPFD

C_install: $(CFILES)
        Set Alias$CCPFD $(CP) C.!installc.%0.%1 $(INSTDIR).C.!Install.%1 $(CPFLAGS)
        |
        $(MKDIR) $(INSTDIR)
        $(MKDIR) $(INSTDIR).C
        $(MKDIR) $(INSTDIR).C.!Install
        $(CP) C.$(LOCALE).Messages $(INSTDIR).C.Messages $(CPFLAGS)
        CCPFD $(RDIR) !Boot
        CCPFD $(RDIR) !Run
        CCPFD $(LDIR) Templates
        CCPFD $(RDIR) !RunImage
        CCPFD $(RDIR) !Sprites
        CCPFD $(LDIR) !Help
        |
        Unset Alias$CCPFD

install: $(FILES) Assembler_install C_install
        $(MKDIR) $(INSTDIR)
        $(CP) $(RDIR).MoveBoot $(INSTDIR).MoveBoot $(CPFLAGS)
        $(CP) $(LDIR).ReadMe   $(INSTDIR).ReadMe   $(CPFLAGS)
        |
        -attr -directories +wr ${INSTDIR}
        -attr -files +or +ow +wr -ww ${INSTDIR}
        |
        @echo $(COMPONENT): installed

clean:
        $(RM) assembler.!installa.$(RDIR).!RunImage
        $(RM) c.!installc.$(RDIR).!RunImage
        ${WIPE} assembler.!installa.o.* ${WFLAGS}
        ${WIPE} c.!installc.o.* ${WFLAGS}
        @echo $(COMPONENT): cleaned

#---------------------------------------------------------------------------
# Dynamic dependencies:
