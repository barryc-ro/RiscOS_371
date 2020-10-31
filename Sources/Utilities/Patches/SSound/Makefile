# Makefile for SSound install

#
# Program specific options:
#
COMPONENT  = SSound
RDIR       = Resources
LDIR       = ${RDIR}.${LOCALE}
INSTDIR    = ${INSTDIR}.SSound

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
 $(RDIR).SSound \
 $(LDIR).ReadMe


#
# GENERIC RULES
#                  

install: $(FILES) 
        $(MKDIR) $(INSTDIR)
        $(CP) $(RDIR).SSound   $(INSTDIR).SSound   $(CPFLAGS)
        $(CP) $(LDIR).ReadMe   $(INSTDIR).ReadMe   $(CPFLAGS)
        |
        -attr -directories +wr ${INSTDIR}
        -attr -files +or +ow +wr -ww ${INSTDIR}
        |
        @echo $(COMPONENT): installed

#---------------------------------------------------------------------------
# Dynamic dependencies:
