# Makefile for International module
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
COMPONENT = Inter
SOURCE    = s.InterMod
TARGET    = rm.Inter

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
        ${RM} s.IntHelpTok
        ${RM} s.IntHelp
        @echo ${COMPONENT}: cleaned

resources:
        ${MKDIR} ${RESDIR}.Internatio
        ${CP} Resources.${LOCALE}.Messages  ${RESDIR}.Internatio.Messages  ${CPFLAGS}
        @echo ${COMPONENT}: resource files copied

${TARGET}: ${SOURCE} s.IntHelpTok
        ${AS} ${ASFLAGS} ${SOURCE}

s.IntHelpTok: ${TOKENS} s.IntHelp
        ${TOKENISE} ${TOKENS} s.IntHelp $@

s.IntHelp: IntHelpSrc IntHelpBody
        ${AS} -depend !Depend -Stamp -quit -To $@ -From IntHelpSrc

# Dynamic dependencies:
rm.Inter: s.InterBody
rm.Inter: Hdr:ListOpts
rm.Inter: Hdr:Macros
rm.Inter: Hdr:System
rm.Inter: Hdr:SWIs
rm.Inter: Hdr:CPU.Generic26
rm.Inter: Hdr:IO.GenericIO
rm.Inter: Hdr:RISCOS
rm.Inter: Hdr:CMOS
rm.Inter: Hdr:ModHand
rm.Inter: Hdr:Services
rm.Inter: Hdr:Proc
rm.Inter: Hdr:FSNumbers
rm.Inter: Hdr:NewErrors
rm.Inter: Hdr:MsgTrans
rm.Inter: Hdr:ResourceFS
rm.Inter: s.IntHelpTok
rm.Inter: Hdr:Tokens
rm.Inter: s.InterFonts
s.IntHelp: IntHelpBod
s.IntHelp: Hdr:ListOpts
s.IntHelp: Hdr:ModHand
