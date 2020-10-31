# Makefile for International Keyboard
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name         Description
# ----       ----         -----------
# 25-May-94  AMcC         Created.
# 23-Aug-94  AMcC         Updated to build International Version (from Opal)
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
COMPONENT = IntKey
SOURCE    = ${LOCALE}.Source.IntKeyMod
TARGET    = rm.IntKey

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
        set IKHG$Country ${LOCALE}
        ${AS} ${ASFLAGS} ${SOURCE}
        unset IKHG$Country

# Dynamic dependencies:
rm.IntKey: Source.IntKeyBody
rm.IntKey: Hdr:ListOpts
rm.IntKey: Hdr:Macros
rm.IntKey: Hdr:System
rm.IntKey: Hdr:SWIs
rm.IntKey: Hdr:CPU.Generic26
rm.IntKey: Hdr:IO.GenericIO
rm.IntKey: Hdr:RISCOS
rm.IntKey: Hdr:ModHand
rm.IntKey: Hdr:Services
rm.IntKey: Hdr:Proc
rm.IntKey: !IKHG.Source.Chars.Latin1
rm.IntKey: <Locale>.Source.KeyStruct
rm.IntKey: UK.Source.UKPCKbd
