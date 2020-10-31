# Makefile for TCP/IP install
# see src directory for source stuff

#
# Program specific options:
#
COMPONENT  = !Protocols
RDIR       = Resources
LDIR       = ${RDIR}.${LOCALE}
INSTDIR    = ${INSTDIR}.TCP/IP

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
 $(RDIR).!Protocols.Protocols.!Ftp.!Run\
 $(LDIR).ReadMe


#
# GENERIC RULES
#                  

install: $(FILES) 
        $(MKDIR) $(INSTDIR)
        $(CP) $(RDIR).!Protocols   $(INSTDIR).!Protocols   $(CPFLAGS)
        $(CP) $(LDIR).ReadMe   $(INSTDIR).ReadMe   $(CPFLAGS)
        |
        -attr -directories +wr ${INSTDIR}
        -attr -files +or +ow +wr -ww ${INSTDIR}
        |
        @echo $(COMPONENT): installed

#---------------------------------------------------------------------------
# Dynamic dependencies:
