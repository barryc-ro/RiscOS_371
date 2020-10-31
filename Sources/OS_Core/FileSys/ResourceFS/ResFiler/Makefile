# Makefile for ResFiler
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
COMPONENT = ResFiler
SOURCE    = s.ResFiler
TARGET    = rm.ResFiler

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
        @echo ${COMPONENT}: resource files copied

${TARGET}: ${SOURCE}
        ${AS} ${ASFLAGS} ${SOURCE}

# Dynamic dependencies:
rm.ResFiler: Hdr:ListOpts
rm.ResFiler: Hdr:Macros
rm.ResFiler: Hdr:System
rm.ResFiler: Hdr:SWIs
rm.ResFiler: Hdr:CPU.Generic26
rm.ResFiler: Hdr:IO.GenericIO
rm.ResFiler: Hdr:RISCOS
rm.ResFiler: Hdr:ModHand
rm.ResFiler: Hdr:CMOS
rm.ResFiler: Hdr:FSNumbers
rm.ResFiler: Hdr:NewErrors
rm.ResFiler: Hdr:Wimp
rm.ResFiler: Hdr:WimpSpace
rm.ResFiler: Hdr:Messages
rm.ResFiler: Hdr:Sprite
rm.ResFiler: Hdr:VduExt
rm.ResFiler: Hdr:Proc
rm.ResFiler: Hdr:Services
rm.ResFiler: Hdr:Variables
rm.ResFiler: Hdr:MsgTrans
rm.ResFiler: Hdr:MsgMenus
rm.ResFiler: Hdr:ResourceFS
rm.ResFiler: Version
