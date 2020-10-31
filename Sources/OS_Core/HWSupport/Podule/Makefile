# Makefile for Podule {Expansion cards}
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name         Description
# ----       ----         -----------
# 25-May-94  AMcC         Created.
# 28-Jun-94  AMcC         Added extra development rules.
# 30-Aug-94  AMcC         Added resources: target
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
MODGEN   = modgen
RM      = remove
CCFLAGS = -c -depend !Depend -IC:
ASFLAGS = -depend !Depend -Stamp -quit -module -To $@ -From
CPFLAGS = ~cfr~v

TOKENISE = tokenise
TOKENS   = Hdr:Tokens

#
# Program specific options:
#
COMPONENT = Podule
SOURCE    = s.GetAll
TARGET    = rm.Podule
EXPORTS   = ${EXP_HDR}.${COMPONENT}

MESSAGESMOD = rm.PoduleMsgs
MESSAGES  = Resources.${LOCALE}.Messages
RESPATH   = Resources.Podule.Messages
MODNAME   = PoduleManagerMessages
MODHELP   = PoduleManagerMessages

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

resources:
        ${MKDIR} ${RESDIR}.${COMPONENT}
        ${CP} ${MESSAGES} ${RESDIR}.${COMPONENT}.Messages  ${CPFLAGS}
        @echo ${COMPONENT}: resource files copied

clean:
        ${RM} ${TARGET}
        ${RM} ${MESSAGESMOD}
        ${RM} s.HelpTokens
        ${RM} setversion
        @echo ${COMPONENT}: cleaned

${TARGET}: ${SOURCE} s.HelpTokens
        ${AS} ${ASFLAGS} ${SOURCE}

s.HelpTokens: ${TOKENS} HelpTexts
        ${TOKENISE} ${TOKENS} HelpTexts $@

${EXP_HDR}.${COMPONENT}: hdr.${COMPONENT}
        ${CP} hdr.${COMPONENT} $@ ${CPFLAGS}


# 
# Generate a Messages module
# Note: need to set alias to ensure that <Version> is expanded
#
msgmod: ${MESSAGESMOD}
        @echo ${COMPONENT}: messages module built

${MESSAGESMOD}: ${MESSAGES} setversion
        setversion
        set alias$modgen_ver ${MODGEN} $@ ${MODNAME} ${MODHELP} <Version> ${MESSAGES} ${RESPATH}
        modgen_ver
        unset alias$modgen
        unset Version

setversion: Time+Date
        ${AS} ${ASFLAGS} utils.getversion
        settype setversion obey

#
# Extra Development rules:
#
install: ${TARGET}
        Access ${TARGET} R/r
        ${CP} ${TARGET} ${INSTDIR}.${COMPONENT} ${CPFLAGS}
        @echo ${COMPONENT}: ${TARGET} installed

maketime:
        MakeTime

version:
        Version



# Dynamic dependencies:
setversion: Time+Date
rm.Podule: Hdr:ListOpts
rm.Podule: Hdr:Macros
rm.Podule: Hdr:System
rm.Podule: Hdr:SWIs
rm.Podule: Hdr:CPU.Generic26
rm.Podule: Hdr:IO.GenericIO
rm.Podule: Hdr:RISCOS
rm.Podule: Hdr:CMOS
rm.Podule: Hdr:ModHand
rm.Podule: Hdr:Debug
rm.Podule: Hdr:Podule
rm.Podule: Hdr:FSNumbers
rm.Podule: Hdr:HighFSI
rm.Podule: Hdr:NewErrors
rm.Podule: Hdr:Services
rm.Podule: Hdr:Tokens
rm.Podule: Hdr:Proc
rm.Podule: Hdr:Symbols
rm.Podule: Hdr:MsgTrans
rm.Podule: Time+Date
rm.Podule: s.Module
rm.Podule: s.Interface
rm.Podule: s.Commands
rm.Podule: s.Errors
rm.Podule: s.ROMExtend
rm.Podule: HelpTexts
rm.Podule: s.MsgCode
