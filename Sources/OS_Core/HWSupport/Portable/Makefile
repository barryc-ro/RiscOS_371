# Makefile for Portable (Morris based)
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name         Description
# ----       ----         -----------
# 22-Sep-94  RCM          Created.
# 06-Jan-95  AMcC         Added resources rule
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
COMPONENT = Portable
SOURCE    = s.GetAll
TARGET    = rm.${COMPONENT}
TARGETSA  = rm.${COMPONENT}SA
EXPORTS   = ${EXP_HDR}.${COMPONENT}
RDIR      = Resources
LDIR      = ${RDIR}.${LOCALE}

#
# Export Paths for Messages module
#
RESDIR = <resource$dir>.Resources2.${COMPONENT}

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
        ${CP} ${LDIR}.LCD       ${RESDIR}.LCD       ${CPFLAGS}
        ${CP} ${LDIR}.SelectLCD ${RESDIR}.SelectLCD ${CPFLAGS}
        @echo ${COMPONENT}: resource files copied to Messages module

clean:
        ${RM} ${TARGET}
        ${RM} ${TARGETSA}
        @echo ${COMPONENT}: cleaned

${TARGET}: ${SOURCE}
        ${AS} ${ASFLAGS} ${SOURCE}

${EXP_HDR}.${COMPONENT}: hdr.${COMPONENT}
        ${CP} hdr.${COMPONENT} $@ ${CPFLAGS}

#
# Makes a stand-alone version with messages bound in
#
standalone: ${TARGETSA}
        @echo ${COMPONENT}: standalone module built

${TARGETSA}: s.StandAlone ${LDIR}.Messages
        ${AS} ${ASFLAGS} s.StandAlone

# Dynamic dependencies:
rm.Portable: Hdr:ListOpts
rm.Portable: Hdr:Macros
rm.Portable: Hdr:System
rm.Portable: Hdr:SWIs
rm.Portable: Hdr:CPU.Generic26
rm.Portable: Hdr:IO.GenericIO
rm.Portable: Hdr:RISCOS
rm.Portable: Hdr:Machine.<Machine>
rm.Portable: Hdr:IO.IOMDL
rm.Portable: Hdr:KEYV
rm.Portable: Hdr:ModHand
rm.Portable: Hdr:Services
rm.Portable: Hdr:FSNumbers
rm.Portable: Hdr:CMOS
rm.Portable: Hdr:HighFSI
rm.Portable: Hdr:NewErrors
rm.Portable: Hdr:MsgTrans
rm.Portable: Hdr:Proc
rm.Portable: Hdr:PaletteV
rm.Portable: Hdr:Portable
rm.Portable: Hdr:ADFS
rm.Portable: Hdr:Variables
rm.Portable: Hdr:ScrBlank
rm.Portable: Hdr:PublicWS
rm.Portable: Hdr:Sound
rm.Portable: Hdr:Debug
rm.Portable: Hdr:DevNos
rm.Portable: Hdr:IIC
rm.Portable: Hdr:Messages
rm.Portable: Version
rm.Portable: s.Front
rm.Portable: s.Macros
rm.Portable: s.StPortable
rm.Portable: s.PowerCtrl
rm.Portable: s.HotKeys
rm.Portable: s.MicroCtrl
rm.Portable: s.LCDcontrol
rm.Portable: s.StateMC
