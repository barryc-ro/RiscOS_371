# Makefile for Joystick
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
# Program specific options:
#
COMPONENT = Joystick
SOURCE    = s.Front
TARGET    = rm.Joystick
EXPORTS   = ${EXP_HDR}.${COMPONENT}
RDIR      = Resources
LDIR      = ${RDIR}.${LOCALE}


#
# Export Paths for Messages module
#
RESDIR  = <resource$dir>.Resources2.${COMPONENT}

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
# Generic rules:
#
rom: ${TARGET}
        @echo ${COMPONENT}: rom module built

export: ${EXPORTS}
        @echo ${COMPONENT}: export complete

install_rom: ${TARGET}
        ${CP} ${TARGET} ${INSTDIR}.${COMPONENT} ${CPFLAGS}
        @echo ${COMPONENT}: rom module installed

resources:
        ${MKDIR} ${RESDIR}
        ${CP} ${LDIR}.Messages  ${RESDIR}.Messages  ${CPFLAGS}
        @echo ${COMPONENT}: resource files copied to Messages module

clean:
        ${RM} ${TARGET}
        @echo ${COMPONENT}: cleaned

${TARGET}: ${SOURCE}
        ${AS} ${ASFLAGS} ${SOURCE}

${EXP_HDR}.${COMPONENT}: hdr.${COMPONENT}
        ${CP} hdr.${COMPONENT} $@ ${CPFLAGS}

# Dynamic dependencies:
rm.Joystick: Hdr:ListOpts
rm.Joystick: Hdr:Macros
rm.Joystick: Hdr:System
rm.Joystick: Hdr:SWIs
rm.Joystick: Hdr:CPU.Generic26
rm.Joystick: Hdr:IO.GenericIO
rm.Joystick: Hdr:RISCOS
rm.Joystick: Hdr:ModHand
rm.Joystick: Hdr:MsgTrans
rm.Joystick: Hdr:NdrDebug
rm.Joystick: Hdr:Podule
rm.Joystick: Version
rm.Joystick: s.ModHead
rm.Joystick: s.ticky
rm.Joystick: s.SWI
rm.Joystick: s.Service
rm.Joystick: s.Tail
