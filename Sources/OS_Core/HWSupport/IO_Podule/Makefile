# MakeFile for IO Podule
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
MKDIR    = cdir
AS       = aasm
CP       = copy
MODGEN   = modgen
RM       = remove
TOKENISE = tokenise

AFLAGS   = -depend !Depend -stamp -closeexec -quit
CPFLAGS  = ~cfr~v

TOKENS   = Hdr:Tokens

#
# Program specific options:
#
IMAGE  = rom.IO_Podule
MODULE = rm.IO_Podule
LOADER = rm.Loader

all: ${IMAGE}

clean:
        ${RM} ${IMAGE}
        ${RM} ${MODULE}
        ${RM} ${LOADER}
        @echo ${COMPONENT}: cleaned

${IMAGE}: MakeROM ${MODULE} ${LOADER}
        MakeROM

${MODULE}: s.IO_Podule
        ${AS} s.IO_Podule $@ -module ${AFLAGS}

${LOADER}: s.Loader
        ${AS} s.Loader $@ ${AFLAGS}

#---------------------------------------------------------------------------
# Dynamic dependencies:
