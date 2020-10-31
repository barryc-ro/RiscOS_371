# Makefile for DragASprit
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name         Description
# ----       ----         -----------
# 25-May-94  AMcC         Created.
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
COMPONENT = DragASprit
SOURCE    = s.Gets
TARGET    = rm.DragASprit
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
rm.DragASprit: Hdr:ListOpts
rm.DragASprit: Hdr:Macros
rm.DragASprit: Hdr:System
rm.DragASprit: Hdr:SWIs
rm.DragASprit: Hdr:CPU.Generic26
rm.DragASprit: Hdr:IO.GenericIO
rm.DragASprit: Hdr:RISCOS
rm.DragASprit: Hdr:ModHand
rm.DragASprit: Hdr:Services
rm.DragASprit: Hdr:Proc
rm.DragASprit: Hdr:Sprite
rm.DragASprit: Hdr:WimpSpace
rm.DragASprit: Hdr:Wimp
rm.DragASprit: Hdr:VduExt
rm.DragASprit: Hdr:FSNumbers
rm.DragASprit: Hdr:NewErrors
rm.DragASprit: Hdr:DragASprit
rm.DragASprit: Hdr:MsgTrans
rm.DragASprit: Hdr:ColourTran
rm.DragASprit: s.DebugOpts
rm.DragASprit: s.Support
rm.DragASprit: s.StartUp
rm.DragASprit: s.Drag
