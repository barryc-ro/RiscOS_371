# Makefile for Draw module
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
COMPONENT = DrawMod
SOURCE    = s.Draw
TARGET    = rm.${COMPONENT}
EXPORTS   = ${EXP_HDR}.Draw

#
# Export Paths for Messages module
#
RESDIR = <resource$dir>.Resources.${COMPONENT}

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
        ${MKDIR} ${RESDIR}
        ${CP} Resources.${LOCALE}.Messages ${RESDIR}.Messages ${CPFLAGS}
        @echo ${COMPONENT}: resource files copied

${TARGET}: ${SOURCE}
        ${AS} ${ASFLAGS} ${SOURCE}

${EXP_HDR}.Draw: hdr.Draw
        ${CP} hdr.Draw $@ ${CPFLAGS}

# Dynamic dependencies:
rm.DrawMod: Version
rm.DrawMod: hdr:ListOpts
rm.DrawMod: hdr:Macros
rm.DrawMod: hdr:System
rm.DrawMod: Hdr:SWIs
rm.DrawMod: Hdr:CPU.Generic26
rm.DrawMod: Hdr:IO.GenericIO
rm.DrawMod: Hdr:RISCOS
rm.DrawMod: hdr:PublicWS
rm.DrawMod: hdr:ModHand
rm.DrawMod: hdr:Services
rm.DrawMod: hdr:VduExt
rm.DrawMod: hdr:FSNumbers
rm.DrawMod: hdr:NewErrors
rm.DrawMod: hdr:Debug
rm.DrawMod: hdr:Draw
rm.DrawMod: hdr:Proc
rm.DrawMod: hdr:MsgTrans
rm.DrawMod: s.DrProcess
rm.DrawMod: s.DrOutput
rm.DrawMod: s.DrQFill
rm.DrawMod: s.DrArith
rm.DrawMod: s.DrInter
