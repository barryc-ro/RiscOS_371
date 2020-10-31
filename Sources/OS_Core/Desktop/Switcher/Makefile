# Makefile for Task Manager
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name         Description
# ----       ----         -----------
# 25-May-94  AMcC         Created.
# 18-Oct-94  AMcC         Templates copied to Resources as 'Templates' not 'Template3D'
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
COMPONENT = Switcher
SOURCE    = s.Switcher
TARGET    = rm.Switcher
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

resources:
        ${MKDIR} ${RESDIR}.${COMPONENT}
        ${CP} Resources.${LOCALE}.Messages   ${RESDIR}.${COMPONENT}.Messages ${CPFLAGS}
        ${CP} Resources.${LOCALE}.Templates ${RESDIR}.${COMPONENT}.Templates ${CPFLAGS}
        @echo ${COMPONENT}: resource files copied

${TARGET}: ${SOURCE}
        ${AS} ${ASFLAGS} ${SOURCE}

${EXP_HDR}.${COMPONENT}: hdr.${COMPONENT}
        ${CP} hdr.${COMPONENT} $@ ${CPFLAGS}

# Dynamic dependencies:
rm.Switcher: Version
rm.Switcher: Hdr:ListOpts
rm.Switcher: Hdr:Macros
rm.Switcher: Hdr:System
rm.Switcher: Hdr:SWIs
rm.Switcher: Hdr:CPU.Generic26
rm.Switcher: Hdr:IO.GenericIO
rm.Switcher: Hdr:RISCOS
rm.Switcher: Hdr:CMOS
rm.Switcher: Hdr:ModHand
rm.Switcher: Hdr:Services
rm.Switcher: Hdr:VduExt
rm.Switcher: Hdr:FSNumbers
rm.Switcher: Hdr:HighFSI
rm.Switcher: Hdr:FileTypes
rm.Switcher: Hdr:NewErrors
rm.Switcher: Hdr:Sprite
rm.Switcher: Hdr:Variables
rm.Switcher: Hdr:Wimp
rm.Switcher: Hdr:WimpSpace
rm.Switcher: Hdr:Messages
rm.Switcher: Hdr:Proc
rm.Switcher: Hdr:MsgTrans
rm.Switcher: Hdr:ResourceFS
rm.Switcher: Hdr:Hourglass
rm.Switcher: Hdr:Font
rm.Switcher: Hdr:FileCore
rm.Switcher: Hdr:Switcher
rm.Switcher: Hdr:UpCall
rm.Switcher: Hdr:MsgMenus
rm.Switcher: Hdr:DragASprit
rm.Switcher: Hdr:Portable
rm.Switcher: Hdr:NDRDebug
