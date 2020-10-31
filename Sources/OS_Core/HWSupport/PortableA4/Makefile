# Makefile for Portable
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
COMPONENT = Portable
SOURCE    = s.GetAll
TARGET    = rm.Portable
TARGETSA  = rm.PortableSA
EXPORTS   = ${EXP_HDR}.${COMPONENT}
RESOURCES = Resources.${LOCALE}.Messages

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

${TARGETSA}: s.StandAlone ${RESOURCES}
        ${AS} ${ASFLAGS} s.StandAlone

# Dynamic dependencies:
rm.Portable: Hdr:ListOpts
rm.Portable: Hdr:Macros
rm.Portable: Hdr:System
rm.Portable: Hdr:SWIs
rm.Portable: Hdr:CPU.Generic26
rm.Portable: Hdr:IO.GenericIO
rm.Portable: Hdr:RISCOS
rm.Portable: Hdr:CMOS
rm.Portable: Hdr:ModHand
rm.Portable: Hdr:Debug
rm.Portable: Hdr:FSNumbers
rm.Portable: Hdr:HighFSI
rm.Portable: Hdr:NewErrors
rm.Portable: Hdr:Services
rm.Portable: Hdr:Tokens
rm.Portable: Hdr:Proc
rm.Portable: Hdr:IO.IOEB
rm.Portable: Hdr:IO.IOC
rm.Portable: Hdr:MEMM.MEMC1
rm.Portable: Hdr:PaletteV
rm.Portable: Hdr:Portable
rm.Portable: Hdr:VduExt
rm.Portable: Hdr:ADFS
rm.Portable: Hdr:MsgTrans
rm.Portable: Hdr:DevNos
rm.Portable: Hdr:IIC
rm.Portable: Hdr:Variables
rm.Portable: Hdr:ScrBlank
rm.Portable: Hdr:PublicWS
rm.Portable: Hdr:Sound
rm.Portable: Version
rm.Portable: s.Header
rm.Portable: s.VduModes
rm.Portable: s.Module
rm.Portable: s.BMUstuff
rm.PortableSA: s.GetAll
rm.PortableSA: Hdr:ListOpts
rm.PortableSA: Hdr:Macros
rm.PortableSA: Hdr:System
rm.PortableSA: Hdr:SWIs
rm.PortableSA: Hdr:CPU.Generic26
rm.PortableSA: Hdr:IO.GenericIO
rm.PortableSA: Hdr:RISCOS
rm.PortableSA: Hdr:CMOS
rm.PortableSA: Hdr:ModHand
rm.PortableSA: Hdr:Debug
rm.PortableSA: Hdr:FSNumbers
rm.PortableSA: Hdr:HighFSI
rm.PortableSA: Hdr:NewErrors
rm.PortableSA: Hdr:Services
rm.PortableSA: Hdr:Tokens
rm.PortableSA: Hdr:Proc
rm.PortableSA: Hdr:IO.IOEB
rm.PortableSA: Hdr:IO.IOC
rm.PortableSA: Hdr:MEMM.MEMC1
rm.PortableSA: Hdr:PaletteV
rm.PortableSA: Hdr:Portable
rm.PortableSA: Hdr:VduExt
rm.PortableSA: Hdr:ADFS
rm.PortableSA: Hdr:MsgTrans
rm.PortableSA: Hdr:DevNos
rm.PortableSA: Hdr:IIC
rm.PortableSA: Hdr:Variables
rm.PortableSA: Hdr:ScrBlank
rm.PortableSA: Hdr:PublicWS
rm.PortableSA: Hdr:Sound
rm.PortableSA: Version
rm.PortableSA: s.Header
rm.PortableSA: s.VduModes
rm.PortableSA: s.Module
rm.PortableSA: s.BMUstuff
rm.PortableSA: Hdr:ResourceFS
rm.PortableSA: s.ResFiles
