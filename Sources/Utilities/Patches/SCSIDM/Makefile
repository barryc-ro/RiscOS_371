# Makefile for SCSIDM install
# see src directory for source stuff

#
# Program specific options:
#
COMPONENT  = SCSIDM
RDIR       = Resources
LDIR       = ${RDIR}.${LOCALE}
INSTDIR    = ${INSTDIR}.SCSIDM

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
 $(RDIR).ScsiDM \
 $(LDIR).ReadMe


#
# GENERIC RULES
#                  

install: $(FILES) 
        $(MKDIR) $(INSTDIR)
        $(CP) $(RDIR).ScsiDM   $(INSTDIR).ScsiDM   $(CPFLAGS)
        $(CP) $(LDIR).ReadMe   $(INSTDIR).ReadMe   $(CPFLAGS)
        |
        -attr -directories +wr ${INSTDIR}
        -attr -files +or +ow +wr -ww ${INSTDIR}
        |
        @echo $(COMPONENT): installed

#---------------------------------------------------------------------------
# Dynamic dependencies:
