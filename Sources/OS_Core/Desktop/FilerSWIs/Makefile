# Makefile for FilerSWIs
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name         Description
# ----       ----         -----------
# 25-May-94  AMcC         Created.
#

#
# Generic options:
#
MKDIR   = cdir
AS      = aasm
CP      = copy
RM      = remove
CCFLAGS = -c -depend !Depend -IC:
ASFLAGS = -depend !Depend -Stamp -quit -module -To $@ -From
CPFLAGS = ~cfr~v

#
# Program specific options:
#
COMPONENT = FilerSWIs
SOURCE    = s.FilerSWIs
TARGET    = rm.FilerSWIs

#
# Generic rules:
#
rom: ${TARGET}
        @echo ${COMPONENT}: rom module built

export: 
        @echo ${COMPONENT}: export complete

install_rom: ${TARGET}
        ${CP} ${TARGET} ${INSTDIR}.${COMPONENT} ${CPFLAGS}
        @echo ${COMPONENT}: rom module installed

clean:
        ${RM} ${TARGET}
        @echo ${COMPONENT}: cleaned

${TARGET}: ${SOURCE}
        ${AS} ${ASFLAGS} ${SOURCE}

# Dynamic dependencies:
rm.FilerSWIs: Hdr:ListOpts
rm.FilerSWIs: Hdr:Macros
rm.FilerSWIs: Hdr:System
rm.FilerSWIs: Hdr:SWIs
rm.FilerSWIs: Hdr:CPU.Generic26
rm.FilerSWIs: Hdr:IO.GenericIO
rm.FilerSWIs: Hdr:RISCOS
rm.FilerSWIs: Hdr:FSNumbers
rm.FilerSWIs: Hdr:NewErrors
rm.FilerSWIs: Hdr:ModHand
rm.FilerSWIs: Hdr:Wimp
rm.FilerSWIs: Hdr:WimpSpace
rm.FilerSWIs: Hdr:Messages
rm.FilerSWIs: Hdr:Proc
rm.FilerSWIs: Hdr:FilerAct
rm.FilerSWIs: Hdr:MsgTrans
rm.FilerSWIs: Version
