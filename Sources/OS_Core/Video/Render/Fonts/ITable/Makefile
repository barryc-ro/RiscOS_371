# Makefile for ITable
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name         Description
# ----       ----         -----------
# 05Dec95    diz    	  Created
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
COMPONENT = ITable
SOURCE    = s.ITable
TARGET    = rm.ITable
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
rm.ITable: hdr:ListOpts
rm.ITable: hdr:Macros
rm.ITable: hdr:System
rm.ITable: Hdr:SWIs
rm.ITable: Hdr:CPU.Generic26
rm.ITable: Hdr:IO.GenericIO
rm.ITable: Hdr:RISCOS
rm.ITable: hdr:ModHand
rm.ITable: hdr:Proc
rm.ITable: hdr:Services
rm.ITable: hdr:FSNumbers
rm.ITable: Hdr:HighFSI
rm.ITable: hdr:NewErrors
rm.ITable: hdr:Variables
rm.ITable: hdr:VduExt
rm.ITable: hdr:Debug
rm.ITable: hdr:Sprite
rm.ITable: hdr:ColourTran
rm.ITable: hdr:Hourglass
rm.ITable: hdr:NDRDebug
rm.ITable: hdr:PublicWS
rm.ITable: hdr:HostFS
rm.ITable: hdr:PaletteV
rm.ITable: hdr:DDVMacros
rm.ITable: hdr.ITable
rm.ITable: Version
