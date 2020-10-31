# Makefile for ShellCLI
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
MKDIR   = cdir
AS      = aasm
CP      = copy
RM      = remove
CCFLAGS = -c -depend !Depend -IC:
ASFLAGS = -depend !Depend -Stamp -quit -module -To $@ -From
CPFLAGS = ~cfr~v

#
# Program specific options:
#
COMPONENT = ShellCLI
SOURCE    = s.ShellCLI
TARGET    = rm.ShellCLI
EXPORTS   = ${EXP_HDR}.Shell

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

clean:
        ${RM} ${TARGET}
        @echo ${COMPONENT}: cleaned

resources:
        ${MKDIR} ${RESDIR}.${COMPONENT}
        ${CP} Resources.${LOCALE}.Messages  ${RESDIR}.${COMPONENT}.Messages  ${CPFLAGS}
        @echo ${COMPONENT}: resource files copied

${TARGET}: ${SOURCE}
        ${AS} ${ASFLAGS} ${SOURCE}

${EXP_HDR}.Shell: hdr.Shell
        ${CP} hdr.Shell $@ ${CPFLAGS}

# Dynamic dependencies:
rm.ShellCLI: hdr:ListOpts
rm.ShellCLI: hdr:Macros
rm.ShellCLI: hdr:System
rm.ShellCLI: Hdr:SWIs
rm.ShellCLI: Hdr:CPU.Generic26
rm.ShellCLI: Hdr:IO.GenericIO
rm.ShellCLI: Hdr:RISCOS
rm.ShellCLI: hdr:ModHand
rm.ShellCLI: hdr:Wimp
rm.ShellCLI: hdr:EnvNumbers
rm.ShellCLI: hdr:Services
rm.ShellCLI: hdr:FSNumbers
rm.ShellCLI: hdr:NewErrors
rm.ShellCLI: hdr:MsgTrans
rm.ShellCLI: hdr:Proc
rm.ShellCLI: Version
