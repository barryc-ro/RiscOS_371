# Makefile for SpriteUtil
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
COMPONENT = SpriteUtil
SOURCE    = s.SpriteUtil
TARGET    = rm.SpriteUtil

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
        ${RM} s.TokHelpSrc
        @echo ${COMPONENT}: cleaned

resources:
        ${MKDIR} ${RESDIR}.${COMPONENT}
        ${CP} Resources.${LOCALE}.Messages  ${RESDIR}.${COMPONENT}.Messages  ${CPFLAGS}
        @echo ${COMPONENT}: resource files copied

${TARGET}: ${SOURCE} s.TokHelpSrc
        ${AS} ${ASFLAGS} ${SOURCE}

s.TokHelpSrc: ${TOKENS} HelpSrc
        ${TOKENISE} ${TOKENS} HelpSrc $@

# Dynamic dependencies:
rm.SpriteUtil: Hdr:ListOpts
rm.SpriteUtil: Hdr:Macros
rm.SpriteUtil: Hdr:System
rm.SpriteUtil: Hdr:SWIs
rm.SpriteUtil: Hdr:CPU.Generic26
rm.SpriteUtil: Hdr:IO.GenericIO
rm.SpriteUtil: Hdr:RISCOS
rm.SpriteUtil: Hdr:ModHand
rm.SpriteUtil: Hdr:Proc
rm.SpriteUtil: Hdr:Tokens
rm.SpriteUtil: Hdr:MsgTrans
rm.SpriteUtil: Hdr:Sprite
rm.SpriteUtil: Version
rm.SpriteUtil: s.TokHelpSrc
rm.SpriteUtil: s.MsgCode
