# Makefile for ARM
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
COMPONENT = ARM
SOURCE    = s.GetAll
TARGET    = rm.ARM

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
rm.ARM: Hdr:ListOpts
rm.ARM: Hdr:Macros
rm.ARM: Hdr:System
rm.ARM: Hdr:SWIs
rm.ARM: Hdr:CPU.Generic26
rm.ARM: Hdr:IO.GenericIO
rm.ARM: Hdr:RISCOS
rm.ARM: Hdr:ModHand
rm.ARM: Hdr:Services
rm.ARM: Hdr:MsgTrans
rm.ARM: Hdr:ResourceFS
rm.ARM: Hdr:NdrDebug
rm.ARM: Hdr:DDVMacros
rm.ARM: Hdr:Proc
rm.ARM: Hdr:CMOS
rm.ARM: Hdr:MEMM.ARM600
rm.ARM: Hdr:FSNumbers
rm.ARM: Hdr:NewErrors
rm.ARM: Version
rm.ARM: s.Front
rm.ARM: s.Errors
rm.ARM: s.Module
rm.ARM: s.Cache
rm.ARM: s.ARM810clk
rm.ARM: s.MsgTrans
