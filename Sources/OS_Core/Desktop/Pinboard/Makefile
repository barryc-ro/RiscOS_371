# Makefile for Pinboard
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
COMPONENT = Pinboard
SOURCE    = s.Pinboard
TARGET    = rm.Pinboard

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

resources:
        ${MKDIR} ${RESDIR}.${COMPONENT}
        ${CP} Resources.${LOCALE}.Messages  ${RESDIR}.${COMPONENT}.Messages  ${CPFLAGS}
        ${CP} Resources.${LOCALE}.Templates ${RESDIR}.${COMPONENT}.Templates ${CPFLAGS}
        @echo ${COMPONENT}: resource files copied

${TARGET}: ${SOURCE}
        ${AS} ${ASFLAGS} ${SOURCE}

# Dynamic dependencies:
rm.Pinboard: hdr:ListOpts
rm.Pinboard: hdr:Macros
rm.Pinboard: hdr:System
rm.Pinboard: Hdr:SWIs
rm.Pinboard: Hdr:CPU.Generic26
rm.Pinboard: Hdr:IO.GenericIO
rm.Pinboard: Hdr:RISCOS
rm.Pinboard: hdr:ModHand
rm.Pinboard: hdr:Services
rm.Pinboard: hdr:VduExt
rm.Pinboard: hdr:FSNumbers
rm.Pinboard: hdr:NewErrors
rm.Pinboard: hdr:Territory
rm.Pinboard: hdr:Variables
rm.Pinboard: hdr:Proc
rm.Pinboard: hdr:Sprite
rm.Pinboard: hdr:Wimp
rm.Pinboard: hdr:WimpSpace
rm.Pinboard: hdr:Messages
rm.Pinboard: hdr:FilerAct
rm.Pinboard: hdr:CMOS
rm.Pinboard: hdr:MsgTrans
rm.Pinboard: hdr:MsgMenus
rm.Pinboard: hdr:ResourceFS
rm.Pinboard: hdr:ColourTran
rm.Pinboard: hdr:DragASprit
rm.Pinboard: hdr:Hourglass
rm.Pinboard: hdr:HostFS
rm.Pinboard: hdr:NdrDebug
rm.Pinboard: hdr:Switcher
rm.Pinboard: Version
rm.Pinboard: s.ModHead
rm.Pinboard: s.StartLoop
rm.Pinboard: s.Messages
rm.Pinboard: s.Help
rm.Pinboard: s.Iconize
rm.Pinboard: s.Save
rm.Pinboard: s.Backdrop
rm.Pinboard: s.Icons
rm.Pinboard: s.Buffered
rm.Pinboard: s.Mouse
rm.Pinboard: s.Drag
rm.Pinboard: s.Menu
rm.Pinboard: s.MenuSelect
rm.Pinboard: s.Tail
