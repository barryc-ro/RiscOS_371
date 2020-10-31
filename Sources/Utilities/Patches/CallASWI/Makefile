# Makefile for CallASWI
#

#
# Program specific options:
#
COMPONENT  = CallASWI
RDIR       = Resources
LDIR       = ${RDIR}.${LOCALE}
INSTDIR    = ${INSTDIR}.CallASWI

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
 CallASWI \
 $(LDIR).ReadMe


#
# GENERIC RULES
#                  
all: $(Files)
          @echo $(COMPONENT): all build complete

CallASWI: Version s.CallASWI
        ${AS} ${ASFLAGS} -To $@ -From s.CallASWI

install: $(FILES) 
        $(MKDIR) $(INSTDIR)
        $(CP) CallASWI   $(INSTDIR).CallASWI   $(CPFLAGS)
        $(CP) $(LDIR).ReadMe   $(INSTDIR).ReadMe   $(CPFLAGS)
        |
        -attr -directories +wr ${INSTDIR}
        -attr -files +or +ow +wr -ww ${INSTDIR}
        |
        @echo $(COMPONENT): installed

#---------------------------------------------------------------------------
# Dynamic dependencies:
CallASWI: Hdr:ListOpts
CallASWI: Hdr:Macros
CallASWI: Hdr:System
CallASWI: Hdr:SWIs
CallASWI: Hdr:CPU.Generic26
CallASWI: Hdr:IO.GenericIO
CallASWI: Hdr:RISCOS
CallASWI: Version
