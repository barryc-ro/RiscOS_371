# Makefile for Debugger
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name         Description
# ----       ----         -----------
# 08-Jun-94  AMcC         Created.
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

TOKENISE = tokenise
TOKENS   = Hdr:Tokens

#
# Program specific options:
#
COMPONENT = Debugger
SOURCE    = s.Debugger
TARGET    = rm.${MACHINE}.Debugger
EXPORTS   = ${EXP_HDR}.Debugger

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
        $(RM) s.TokHelpSrc
        @echo ${COMPONENT}: cleaned

resources:
        ${MKDIR} ${RESDIR}.${COMPONENT}
        ${CP} Resources.${LOCALE}.Messages  ${RESDIR}.${COMPONENT}.Messages  ${CPFLAGS}
        @echo ${COMPONENT}: resource files copied

$(TARGET): $(SOURCE) TokHelpSrc
        ${MKDIR} rm.${MACHINE}
        $(AS) $(ASFLAGS) $(SOURCE)

${EXP_HDR}.Debugger: hdr.Debugger
        ${CP} hdr.Debugger $@ ${CPFLAGS}

TokHelpSrc: $(TOKENS) HelpSrc
        $(TOKENISE) $(TOKENS) HelpSrc $@

# Dynamic dependencies:
rm.Jordan.Debugger: Hdr:ListOpts
rm.Jordan.Debugger: Hdr:Macros
rm.Jordan.Debugger: Hdr:System
rm.Jordan.Debugger: Hdr:SWIs
rm.Jordan.Debugger: Hdr:CPU.Generic26
rm.Jordan.Debugger: Hdr:IO.GenericIO
rm.Jordan.Debugger: Hdr:RISCOS
rm.Jordan.Debugger: Hdr:Machine.<Machine>
rm.Jordan.Debugger: Hdr:ModHand
rm.Jordan.Debugger: Hdr:Services
rm.Jordan.Debugger: Hdr:FSNumbers
rm.Jordan.Debugger: Hdr:NewErrors
rm.Jordan.Debugger: Hdr:EnvNumbers
rm.Jordan.Debugger: Hdr:Proc
rm.Jordan.Debugger: Hdr:VduExt
rm.Jordan.Debugger: Hdr:Tokens
rm.Jordan.Debugger: Hdr:MsgTrans
rm.Jordan.Debugger: Hdr:Debugger
rm.Jordan.Debugger: Version
rm.Jordan.Debugger: Hdr:Debug
rm.Jordan.Debugger: TokHelpSrc
rm.Morris.Debugger: Hdr:ListOpts
rm.Morris.Debugger: Hdr:Macros
rm.Morris.Debugger: Hdr:System
rm.Morris.Debugger: Hdr:SWIs
rm.Morris.Debugger: Hdr:CPU.Generic26
rm.Morris.Debugger: Hdr:IO.GenericIO
rm.Morris.Debugger: Hdr:RISCOS
rm.Morris.Debugger: Hdr:Machine.<Machine>
rm.Morris.Debugger: Hdr:ModHand
rm.Morris.Debugger: Hdr:Services
rm.Morris.Debugger: Hdr:FSNumbers
rm.Morris.Debugger: Hdr:NewErrors
rm.Morris.Debugger: Hdr:EnvNumbers
rm.Morris.Debugger: Hdr:Proc
rm.Morris.Debugger: Hdr:VduExt
rm.Morris.Debugger: Hdr:Tokens
rm.Morris.Debugger: Hdr:MsgTrans
rm.Morris.Debugger: Hdr:Debugger
rm.Morris.Debugger: Version
rm.Morris.Debugger: Hdr:Debug
rm.Morris.Debugger: TokHelpSrc
