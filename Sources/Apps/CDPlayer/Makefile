# Makefile for CDPlayer
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name   Description
# ----       ----   -----------
# 12-Dec-94  AMcC   Created
# 08-Nar-95  AMcC   Added !Help file installation
#                   Commented out rules that would clean & rebuild cdplayer
#

#
# Program specific options:
#
COMPONENT  = CDPlayer
APP        = !${COMPONENT}
RDIR       = Resources
LDIR       = ${RDIR}.${LOCALE}
INSTDIR    = ${INSTDIR}.${APP}

# Generic options:
#
MKDIR   = cdir
CC      = cc
CP      = copy
LD      = link
RM      = remove
SQUEEZE = squeeze
WIPE    = -wipe

CFLAGS  = ${THROWBACK} -c -depend !Depend -fah -Wp ${INCLUDES} ${DFLAGS}
CPFLAGS = ~cfr~v
SQFLAGS = -nolist
WFLAGS  = ~c~v

#
# Libraries
#
CLIB = CLIB:o.stubs
RLIB = RISC_OSLib:o.risc_oslib

#
# Include files
#
INCLUDES = -IC:

DFLAGS   = 

FILES  =\
 $(RDIR).!Boot\
 $(LDIR).!Help\
 $(LDIR).!Run\
 $(RDIR).!sprites\
 $(RDIR).cdplayer\
 $(RDIR).config\
 $(RDIR).sprites\
 $(LDIR).Templates

OBJS = cdplayer.o

#
# Rule patterns
#
.c.o:;      ${CC} ${CFLAGS} -o $@ $<

#
# GENERIC RULES
#
all: $(FILES)
     @echo $(COMPONENT): all built

install: $(FILES)
         $(MKDIR) ${INSTDIR}; Access ${INSTDIR} /r
         $(CP) $(RDIR).!Boot      $(INSTDIR).!Boot       $(CPFLAGS)
         $(CP) $(LDIR).!Help      $(INSTDIR).!Help       $(CPFLAGS)
         $(CP) $(LDIR).!Run       $(INSTDIR).!Run        $(CPFLAGS)
         $(CP) $(RDIR).!sprites   $(INSTDIR).!sprites    $(CPFLAGS)
         $(CP) $(RDIR).cdplayer   $(INSTDIR).cdplayer    $(CPFLAGS)
         $(CP) $(RDIR).config     $(INSTDIR).config      $(CPFLAGS)
         $(CP) $(RDIR).sprites    $(INSTDIR).sprites     $(CPFLAGS)
         $(CP) $(LDIR).Templates  $(INSTDIR).Templates   $(CPFLAGS)
         Access ${INSTDIR}.* LR/r
         Access ${INSTDIR}.config WR/r
         @echo $(COMPONENT): installed

#clean:
#        ${RM} o.cdplayer
#        ${RM} ${RDIR}.cdplayer
#        @echo $(COMPONENT): cleaned

#
# Static dependencies:
#
#${RDIR}.cdplayer: ${OBJS}
#        ${LD} -o $@ ${OBJS} ${CLIB} ${RLIB}
#        ${SQUEEZE} $@

#---------------------------------------------------------------------------
# Dynamic dependencies:
