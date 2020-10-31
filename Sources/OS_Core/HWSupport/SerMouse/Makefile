# Makefile for SerMouse
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
COMPONENT = SerMouse
SOURCE    = s.GetAll
TARGET    = rm.SerMouse

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
rm.SerMouse: Hdr:ListOpts
rm.SerMouse: Hdr:Macros
rm.SerMouse: Hdr:System
rm.SerMouse: Hdr:SWIs
rm.SerMouse: Hdr:CPU.Generic26
rm.SerMouse: Hdr:IO.GenericIO
rm.SerMouse: Hdr:RISCOS
rm.SerMouse: Hdr:ModHand
rm.SerMouse: Hdr:Services
rm.SerMouse: Hdr:MsgTrans
rm.SerMouse: Hdr:ResourceFS
rm.SerMouse: Hdr:Buffer
rm.SerMouse: Hdr:HighFSI
rm.SerMouse: Hdr:CMOS
rm.SerMouse: Hdr:HostFS
rm.SerMouse: Hdr:NdrDebug
rm.SerMouse: Hdr:DDVMacros
rm.SerMouse: Hdr:Proc
rm.SerMouse: Hdr:Pointer
rm.SerMouse: Version
rm.SerMouse: s.Front
rm.SerMouse: s.Macros
rm.SerMouse: s.ModHead
rm.SerMouse: s.SerMouse
rm.SerMouse: s.Driver
rm.SerMouse: s.Tail
