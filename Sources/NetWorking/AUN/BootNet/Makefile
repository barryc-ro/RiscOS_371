# Makefile for BootNet
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name    Description
# ----       ----    -----------
# 25-May-94  AMcC    Created.
# 21-Feb-95  AMcC    Resources now copied to AUNMsgs 
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
COMPONENT = BootNet
SOURCE    = s.Module
TARGET    = rm.BootNet
RESDIR    = ^.AUNMsgs.Resources.${Locale}.Resources.${COMPONENT}

#
# AUN build rules:
#
all: ${TARGET}

#
# RISC OS ROM build rules:
#
rom: ${TARGET}
        @echo ${COMPONENT}: rom module built

export: ${EXPORTS}
        @echo ${COMPONENT}: export complete

install_rom: ${TARGET}
        ${CP} ${TARGET} ${INSTDIR}.${COMPONENT} ${CPFLAGS}
        @echo ${COMPONENT}: rom module installed

resources:
        @echo ${COMPONENT}: Resources in AUNMsgs

clean:
        ${RM} ${TARGET}
        ${RM} HelpTokens
        @echo ${COMPONENT}: cleaned

${TARGET}: ${SOURCE} HelpTokens
        ${AS} ${ASFLAGS} ${SOURCE}

HelpTokens: ${TOKENS} HelpTexts
        ${TOKENISE} ${TOKENS} HelpTexts $@

# Dynamic dependencies:
rm.BootNet: Hdr:ListOpts
rm.BootNet: Hdr:Macros
rm.BootNet: Hdr:System
rm.BootNet: Hdr:SWIs
rm.BootNet: Hdr:CPU.Generic26
rm.BootNet: Hdr:IO.GenericIO
rm.BootNet: Hdr:RISCOS
rm.BootNet: Hdr:CMOS
rm.BootNet: Hdr:ModHand
rm.BootNet: Hdr:Debug
rm.BootNet: Hdr:Tokens
rm.BootNet: Hdr:FSNumbers
rm.BootNet: Hdr:NewErrors
rm.BootNet: Hdr:MsgTrans
rm.BootNet: Time+Date
rm.BootNet: Commands
rm.BootNet: HelpTokens
