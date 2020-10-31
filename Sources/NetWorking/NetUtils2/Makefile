# Makefile for NetUtils2
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

TOKENISE = tokenise
TOKENS   = Hdr:Tokens

#
# Program specific options:
#
COMPONENT = NetUtils2
SOURCE    = s.NetUtils2
TARGET    = rm.NetUtils2

#
# Generic rules:
#
rom: $(TARGET)
        @echo ${COMPONENT}: rom module built

install_rom: $(TARGET)
        $(CP) $(TARGET) $(INSTDIR).$(COMPONENT) $(CPFLAGS)
        @echo ${COMPONENT}: rom module installed

clean:
        $(RM) $(TARGET)
        @echo ${COMPONENT}: cleaned

$(TARGET): $(SOURCE)
        $(AS) $(ASFLAGS) $(SOURCE)

# Dynamic dependencies:
rm.NetUtils2: Hdr:ListOpts
rm.NetUtils2: Hdr:Macros
rm.NetUtils2: Hdr:System
rm.NetUtils2: Hdr:SWIs
rm.NetUtils2: Hdr:CPU.Generic26
rm.NetUtils2: Hdr:IO.GenericIO
rm.NetUtils2: Hdr:RISCOS
rm.NetUtils2: Hdr:ModHand
rm.NetUtils2: Hdr:NdrDebug
rm.NetUtils2: Version
