# Makefile for SCSIFS
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name         Description
# ----       ----         -----------
# 25-May-94  AMcC         Created.
#

#
# Paths
#
EXP_HDR = <export$dir>

#
# Generic options:
#
MKDIR    = cdir
AS       = aasm
CP       = copy
RM       = remove
TOKENISE = tokenise

CFLAGS   = -c -depend !Depend -IC:
AFLAGS   = -depend !Depend -Stamp -quit -module
CPFLAGS  = ~cfr~v

TOKENS   = Hdr:Tokens

#
# Program specific options:
#
COMPONENT = SCSIFS
SOURCE    = s.Hdr_fst
TARGET    = rm.SCSIFS
EXPORTS   = ${EXP_HDR}.${COMPONENT}

#
# Generic rules:
#
all: ${TARGET}
        @echo ${COMPONENT}: all built

export: ${EXPORTS}
        @echo ${COMPONENT}: export complete

install: ${TARGET}
        ${CP} ${TARGET} ${INSTDIR}.${COMPONENT} ${CPFLAGS}
        @echo ${COMPONENT}: installed

clean:
        ${RM} ${TARGET}
        ${RM} TokenHelp
        @echo ${COMPONENT}: cleaned

${TARGET}: ${SOURCE} TokenHelp
        ${AS} ${AFLAGS} -To $@ -From ${SOURCE}

TokenHelp: ${TOKENS} HelpText
        ${TOKENISE} ${TOKENS} HelpText $@

${EXP_HDR}.${COMPONENT}: hdr.${COMPONENT}
        ${CP} hdr.${COMPONENT} $@ ${CPFLAGS}

# Dynamic dependencies:
