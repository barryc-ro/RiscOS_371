# Makefile for PipeFS
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
COMPONENT = PipeFS
SOURCE    = s.PipeFS
TARGET    = rm.PipeFS

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
rm.PipeFS: Hdr:ListOpts
rm.PipeFS: Hdr:Macros
rm.PipeFS: Hdr:System
rm.PipeFS: Hdr:SWIs
rm.PipeFS: Hdr:CPU.Generic26
rm.PipeFS: Hdr:IO.GenericIO
rm.PipeFS: Hdr:RISCOS
rm.PipeFS: Hdr:ModHand
rm.PipeFS: Hdr:Services
rm.PipeFS: Hdr:CMOS
rm.PipeFS: Hdr:Proc
rm.PipeFS: Hdr:FSNumbers
rm.PipeFS: Hdr:HighFSI
rm.PipeFS: Hdr:LowFSi
rm.PipeFS: Hdr:NewErrors
rm.PipeFS: Hdr:Variables
rm.PipeFS: Hdr:Wimp
rm.PipeFS: Hdr:UpCall
rm.PipeFS: Hdr:MsgTrans
rm.PipeFS: Version
rm.PipeFS: Hdr:NDRDebug
