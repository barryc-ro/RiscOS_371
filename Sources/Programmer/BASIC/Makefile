# Makefile for BASIC
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name   Description
# ----       ----   -----------
# 08-Jun-94  AMcC   Created.
# 08-Nov-94  AMcC   Updated to install BASIC64 (non ROM)

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
COMPONENT = BASIC
EXPORTS   = ${EXP_HDR}.BASICTrans
TARGETS   = rm.BASIC105 \
            rm.BASICTrans

#
# Generic rules:
#
all: rm.BASIC64
        @echo ${COMPONENT}: BASIC64 module built

rom: ${TARGETS}
        @echo ${COMPONENT}: rom module built

export: ${EXPORTS}
        @echo ${COMPONENT}: export complete

install: rm.BASIC64
        ${CP} rm.BASIC64 ${INSTDIR}.BASIC64 ${CPFLAGS}
        Access ${INSTDIR}.BASIC64 WR/r
        @echo ${COMPONENT}: BASIC64 installed (Disc)

install_rom: ${TARGETS}
        ${CP} rm.BASIC105 ${INSTDIR}.BASIC105 ${CPFLAGS}
        ${CP} rm.BASICTrans ${INSTDIR}.BASICTrans ${CPFLAGS}
        @echo ${COMPONENT}: rom module installed

clean:
        ${RM} rm.BASIC64
        ${RM} rm.BASIC105
        ${RM} rm.BASICTrans
        @echo ${COMPONENT}: cleaned

resources:
        ${MKDIR} ${RESDIR}.${COMPONENT}
        ${CP} Resources.${LOCALE}.Messages  ${RESDIR}.${COMPONENT}.Messages  ${CPFLAGS}
        @echo ${COMPONENT}: resource files copied

rm.BASIC105: ModuleAB
        ${AS} ${ASFLAGS} ModuleAB

rm.BASIC64: ModuleAB64
        ${AS} ${ASFLAGS} ModuleAB64

rm.BASICTrans: TransSrc
        ${AS} ${ASFLAGS} TransSrc

${EXP_HDR}.BASICTrans: hdr.BASICTrans
        ${CP} hdr.BASICTrans $@ ${CPFLAGS}

# Dynamic dependencies:
rm.BASIC105: BASIC
rm.BASIC105: Fp
rm.BASIC105: Fp2
rm.BASIC105: Expr
rm.BASIC105: Factor
rm.BASIC105: Funct
rm.BASIC105: Stmt
rm.BASIC105: Stmt2
rm.BASIC105: Array
rm.BASIC105: Assembler
rm.BASIC105: Lexical
rm.BASIC105: Command
rm.BASIC105: ErrorMsgs
rm.BASICTrans: Hdr:ListOpts
rm.BASICTrans: Hdr:Macros
rm.BASICTrans: Hdr:System
rm.BASICTrans: Hdr:SWIs
rm.BASICTrans: Hdr:CPU.Generic26
rm.BASICTrans: Hdr:IO.GenericIO
rm.BASICTrans: Hdr:RISCOS
rm.BASICTrans: Hdr:CMOS
rm.BASICTrans: Hdr:ModHand
rm.BASICTrans: Hdr:Services
rm.BASICTrans: Hdr:Proc
rm.BASICTrans: Hdr:FSNumbers
rm.BASICTrans: Hdr:NewErrors
rm.BASICTrans: Hdr:MsgTrans
rm.BASIC64: BASIC
rm.BASIC64: Fp
rm.BASIC64: Fp2
rm.BASIC64: Expr
rm.BASIC64: Factor
rm.BASIC64: Funct
rm.BASIC64: Stmt
rm.BASIC64: Stmt2
rm.BASIC64: Array
rm.BASIC64: Assembler
rm.BASIC64: Lexical
rm.BASIC64: Command
rm.BASIC64: ErrorMsgs
