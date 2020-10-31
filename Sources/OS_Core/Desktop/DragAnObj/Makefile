# Makefile for DragAnObj
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name         Description
# ----       ----         -----------
# 28-Nov-94  AMcC         Created.
#

#
# Paths
#
EXP_HDR = <export$dir>

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
COMPONENT = DragAnObj
SOURCE    = s.DragAnObj
TARGET    = rm.DragAnObj
EXPORTS   = ${EXP_HDR}.${COMPONENT}

#
# Generic rules:
#
rom: ${TARGET}
        @echo ${COMPONENT}: rom module built

export: ${EXPORTS}
        @echo ${COMPONENT}: export complete

install_rom: ${TARGET}
        ${CP} ${TARGET} ${INSTDIR}.${COMPONENT} ${CPFLAGS}
        @echo ${COMPONENT}: rom module installed

clean:
        ${RM} ${TARGET}
        @echo ${COMPONENT}: cleaned

${TARGET}: ${SOURCE}
        ${AS} ${ASFLAGS} ${SOURCE}

${EXP_HDR}.${COMPONENT}: hdr.${COMPONENT}
        ${CP} hdr.${COMPONENT} $@ ${CPFLAGS}

# Dynamic dependencies:
rm.DragAnObj: hdr:ListOpts
rm.DragAnObj: hdr:Macros
rm.DragAnObj: hdr:System
rm.DragAnObj: Hdr:SWIs
rm.DragAnObj: Hdr:CPU.Generic26
rm.DragAnObj: Hdr:IO.GenericIO
rm.DragAnObj: Hdr:RISCOS
rm.DragAnObj: hdr:ModHand
rm.DragAnObj: hdr:Services
rm.DragAnObj: hdr:Switcher
rm.DragAnObj: hdr:Proc
rm.DragAnObj: hdr:Wimp
rm.DragAnObj: hdr:Sprite
rm.DragAnObj: hdr:DragASprit
