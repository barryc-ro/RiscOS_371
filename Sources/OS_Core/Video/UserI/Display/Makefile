# Makefile for Display Manager
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
COMPONENT = Display
SOURCE    = s.GetAll
TARGET    = rm.Display

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
rm.Display: Hdr:ListOpts
rm.Display: Hdr:Macros
rm.Display: Hdr:System
rm.Display: Hdr:SWIs
rm.Display: Hdr:CPU.Generic26
rm.Display: Hdr:IO.GenericIO
rm.Display: Hdr:RISCOS
rm.Display: Hdr:ModHand
rm.Display: Hdr:Services
rm.Display: Hdr:Wimp
rm.Display: Hdr:WimpSpace
rm.Display: Hdr:MsgTrans
rm.Display: Hdr:MsgMenus
rm.Display: Hdr:ResourceFS
rm.Display: Hdr:NdrDebug
rm.Display: Hdr:HostFS
rm.Display: Hdr:DDVMacros
rm.Display: Hdr:Proc
rm.Display: Hdr:Messages
rm.Display: Hdr:Sprite
rm.Display: Hdr:VduExt
rm.Display: Hdr:FileTypes
rm.Display: Hdr:Variables
rm.Display: Hdr:FSNumbers
rm.Display: Hdr:NewErrors
rm.Display: Hdr:ScrModes
rm.Display: Hdr:ColourTran
rm.Display: Version
rm.Display: s.Front
rm.Display: s.Errors
rm.Display: s.Module
rm.Display: s.Icon
rm.Display: s.Window
rm.Display: s.Menu
rm.Display: s.Message
rm.Display: s.Mouse
rm.Display: s.Mode
rm.Display: s.MsgTrans
