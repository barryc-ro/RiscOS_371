# Makefile for Obey
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name         Description
# ----       ----         -----------
# 08-Jun-94  AMcC         Created.
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

TOKENISE = tokenise
TOKENS   = Hdr:Tokens

#
# Program specific options:
#
COMPONENT = Obey
SOURCE    = s.Obey
TARGET    = rm.Obey

#
# Generic rules:
#
rom: $(TARGET)
        @echo ${COMPONENT}: rom module built

export: ${EXPORTS}
        @echo ${COMPONENT}: export complete

install_rom: $(TARGET)
        $(CP) $(TARGET) $(INSTDIR).$(COMPONENT) $(CPFLAGS)
        @echo ${COMPONENT}: rom module installed

clean:
        $(RM) $(TARGET)
        @echo ${COMPONENT}: cleaned

resources:
        ${MKDIR} ${RESDIR}.${COMPONENT}
        ${CP} Resources.${LOCALE}.Messages  ${RESDIR}.${COMPONENT}.Messages  ${CPFLAGS}
        @echo ${COMPONENT}: resource files copied

$(TARGET): $(SOURCE)
        $(AS) $(ASFLAGS) $(SOURCE)

# Dynamic dependencies:
rm.Obey: hdr:ListOpts
rm.Obey: hdr:Macros
rm.Obey: hdr:System
rm.Obey: Hdr:SWIs
rm.Obey: Hdr:CPU.Generic26
rm.Obey: Hdr:IO.GenericIO
rm.Obey: Hdr:RISCOS
rm.Obey: hdr:ModHand
rm.Obey: hdr:Services
rm.Obey: hdr:UpCall
rm.Obey: hdr:FSNumbers
rm.Obey: hdr:HighFSI
rm.Obey: hdr:NewErrors
rm.Obey: hdr:EnvNumbers
rm.Obey: hdr:NdrDebug
rm.Obey: hdr:MsgTrans
rm.Obey: Version
