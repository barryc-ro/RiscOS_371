# Makefile for RTCAdjust
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
COMPONENT = RTCAdjust
SOURCE    = s.RTC
TARGET    = rm.${MACHINE}.RTCAdjust

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
        ${MKDIR} rm.${MACHINE}
        ${AS} ${ASFLAGS} ${SOURCE}

# Dynamic dependencies:
rm.Jordan.RTCAdjust: Hdr:ListOpts
rm.Jordan.RTCAdjust: Hdr:Macros
rm.Jordan.RTCAdjust: Hdr:System
rm.Jordan.RTCAdjust: Hdr:SWIs
rm.Jordan.RTCAdjust: Hdr:CPU.Generic26
rm.Jordan.RTCAdjust: Hdr:IO.GenericIO
rm.Jordan.RTCAdjust: Hdr:RISCOS
rm.Jordan.RTCAdjust: Hdr:CMOS
rm.Jordan.RTCAdjust: Hdr:ModHand
rm.Jordan.RTCAdjust: Hdr:Services
rm.Jordan.RTCAdjust: Hdr:Proc
rm.Jordan.RTCAdjust: Hdr:FSNumbers
rm.Jordan.RTCAdjust: Hdr:NewErrors
rm.Jordan.RTCAdjust: Hdr:IIC
rm.Jordan.RTCAdjust: Hdr:ExtraLong
rm.Jordan.RTCAdjust: Hdr:MsgTrans
rm.Morris.RTCAdjust: Hdr:ListOpts
rm.Morris.RTCAdjust: Hdr:Macros
rm.Morris.RTCAdjust: Hdr:System
rm.Morris.RTCAdjust: Hdr:SWIs
rm.Morris.RTCAdjust: Hdr:CPU.Generic26
rm.Morris.RTCAdjust: Hdr:IO.GenericIO
rm.Morris.RTCAdjust: Hdr:RISCOS
rm.Morris.RTCAdjust: Hdr:CMOS
rm.Morris.RTCAdjust: Hdr:ModHand
rm.Morris.RTCAdjust: Hdr:Services
rm.Morris.RTCAdjust: Hdr:Proc
rm.Morris.RTCAdjust: Hdr:FSNumbers
rm.Morris.RTCAdjust: Hdr:NewErrors
rm.Morris.RTCAdjust: Hdr:IIC
rm.Morris.RTCAdjust: Hdr:ExtraLong
rm.Morris.RTCAdjust: Hdr:MsgTrans
