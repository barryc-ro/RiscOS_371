# Makefile for PDriver (Printer driver)
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name         Description
# ----       ----         -----------
# 27-May-94  AMcC         Created.
#

#
# Paths
#
EXP_HDR = <export$dir>

#
# Program specific options:
#
COMPONENT  = PDriver
EXPORTS    = ${EXP_HDR}.PDriver
LDIR       = ${LOCALE}
# MODULE version has extra (standalone) code to install its Messages in Resources:
MODULE     = rm.${COMPONENT}
ROM_MODULE = rom.${COMPONENT}

#
# Generic options:
#
MKDIR   = cdir
AS      = aasm
CP      = copy
RM      = remove
CCFLAGS = -c -depend !Depend -IC:
ASFLAGS = -depend !Depend -Stamp -quit -module
CPFLAGS = ~cfr~v

#
# Generic rules:
#
all: ${MODULE}
        @echo ${COMPONENT}: all built (disc)

rom: ${ROM_MODULE}
        @echo ${COMPONENT}: all built (rom)

export: ${EXPORTS}
        @echo ${COMPONENT}: export complete

install: ${MODULE}
        ${CP} ${MODULE} ${INSTDIR}.${COMPONENT} ${CPFLAGS}
        Access ${INSTDIR}.${COMPONENT} lr/r
        @echo ${COMPONENT}: installed (disc)

install_rom: ${ROM_MODULE}
        ${CP} ${ROM_MODULE} ${INSTDIR}.${COMPONENT} ${CPFLAGS}
        @echo ${COMPONENT}: installed (rom)

resources:
        ${MKDIR} ${RESDIR}.PDrivers
        ${CP} ${LDIR}.Messages ${RESDIR}.PDrivers.Messages ${CPFLAGS}
        @echo ${COMPONENT}: resource files will be included in Messages module

clean:
        ${RM} ${MODULE}
        ${RM} ${ROM_MODULE}
        @echo ${COMPONENT}: cleaned

#
# Include 'StandAlone' code to install/de-install Messages
#
${MODULE}: s.StandAlone
        ${AS} ${ASFLAGS} -From s.StandAlone -To $@

#
# Messages will be included in Messages module
#
${ROM_MODULE}: s.PDriver
        ${AS} ${ASFLAGS} -From s.PDriver -To $@

${EXP_HDR}.PDriver: hdr.PDriver
        ${CP} hdr.PDriver $@ ${CPFLAGS}

# Dynamic dependencies:
rm.PDriver: s.PDriver
rm.PDriver: hdr:ListOpts
rm.PDriver: hdr:Macros
rm.PDriver: hdr:System
rm.PDriver: Hdr:SWIs
rm.PDriver: Hdr:CPU.Generic26
rm.PDriver: Hdr:IO.GenericIO
rm.PDriver: Hdr:RISCOS
rm.PDriver: hdr:Services
rm.PDriver: hdr:FSNumbers
rm.PDriver: hdr:ModHand
rm.PDriver: hdr:NewErrors
rm.PDriver: hdr:MsgTrans
rm.PDriver: hdr:Proc
rm.PDriver: hdr:HostFS
rm.PDriver: hdr:NDRDebug
rm.PDriver: hdr:DDVMacros
rm.PDriver: hdr:ResourceFS
rm.PDriver: Version
rm.PDriver: s.MsgCode
rom.PDriver: hdr:ListOpts
rom.PDriver: hdr:Macros
rom.PDriver: hdr:System
rom.PDriver: Hdr:SWIs
rom.PDriver: Hdr:CPU.Generic26
rom.PDriver: Hdr:IO.GenericIO
rom.PDriver: Hdr:RISCOS
rom.PDriver: hdr:Services
rom.PDriver: hdr:FSNumbers
rom.PDriver: hdr:ModHand
rom.PDriver: hdr:NewErrors
rom.PDriver: hdr:MsgTrans
rom.PDriver: hdr:Proc
rom.PDriver: hdr:HostFS
rom.PDriver: hdr:NDRDebug
rom.PDriver: hdr:DDVMacros
rom.PDriver: hdr:ResourceFS
rom.PDriver: Version
rom.PDriver: s.MsgCode
