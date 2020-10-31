# Makefile for !SparkFS install

#
# Program specific options:
#
COMPONENT  = !SparkFS
RDIR       = Resources
LDIR       = ${RDIR}.${LOCALE}
INSTDIR    = ${INSTDIR}.SparkFS

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
 $(RDIR).!SparkFS.!Run \
 $(LDIR).ReadMe


#
# GENERIC RULES
#                  

install: $(FILES) 
        $(MKDIR) $(INSTDIR)
        $(CP) $(RDIR).!SparkFS   $(INSTDIR).!SparkFS   $(CPFLAGS)
        $(CP) $(LDIR).ReadMe   $(INSTDIR).ReadMe   $(CPFLAGS)
        |
        -attr -directories +wr ${INSTDIR}
        -attr -files +or +ow +wr -ww ${INSTDIR}
        |
        @echo $(COMPONENT): installed

#---------------------------------------------------------------------------
# Dynamic dependencies:
