# Makefile for ansilib install

#
# Program specific options:
#
COMPONENT  = ansilib
RDIR       = Resources
LDIR       = ${RDIR}.${LOCALE}
INSTDIR    = ${INSTDIR}.ansilib

# Generic options:
#
CP      = copy
MKDIR   = cdir
AS      = aasm
RM      = remove
WIPE    = -wipe
CPFLAGS = ~cfr~v
WFLAGS  = ~c~v
ASFLAGS = -depend !Depend -Stamp -quit -module

FILES  =\
 $(RDIR).ansilib \
 $(LDIR).ReadMe


#
# GENERIC RULES
#                  

install: $(FILES) 
        $(MKDIR) $(INSTDIR)
        $(CP) $(RDIR).ansilib   $(INSTDIR).ansilib   $(CPFLAGS)
        $(CP) $(LDIR).ReadMe   $(INSTDIR).ReadMe   $(CPFLAGS)
        |
        -attr -directories +wr ${INSTDIR}
        -attr -files +or +ow +wr -ww ${INSTDIR}
        |
        @echo $(COMPONENT): installed

#---------------------------------------------------------------------------
# Dynamic dependencies:
