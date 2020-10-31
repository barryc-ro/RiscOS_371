# Makefile for Replay (AREncode)
#

#
# Program specific options:
#
INSTDIR    = ${INSTDIR}
LDIR       = ${LOCALE}

# Generic options:
#
MKDIR   = cdir
CP      = copy
RM      = remove
WIPE    = -wipe

CPFLAGS = ~cfr~v
WFLAGS  = ~c~v



FILES = !ReadMe

#
# GENERIC RULES
#                  
all: ${FILES}
        @echo $(COMPONENT): all build complete

install: ${FILES}
        ${MKDIR} ${INSTDIR}
        |
        ${CP} !ReadMe ${INSTDIR}.!ReadMe $(CPFLAGS)
        $(CP) !AREncode $(INSTDIR).!AREncode $(CPFLAGS)
        $(CP) !ARWork $(INSTDIR).!ARWork $(CPFLAGS)
        |
        Access ${INSTDIR} /r
        Access ${INSTDIR}.* WR/r
        |
        @echo $(COMPONENT): installed

clean:
        @echo $(COMPONENT): cleaned

#---------------------------------------------------------------------------
# Dynamic dependencies:
