# Makefile for Task Window
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
COMPONENT = TaskWindow
SOURCE    = s.Taskman
TARGET    = rm.TaskWindow
EXPORTS   = ${EXP_HDR}.TaskWindow

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

${EXP_HDR}.TaskWindow: hdr.TaskWindow
        ${CP} hdr.TaskWindow $@ ${CPFLAGS}

# Dynamic dependencies:
rm.Task: Hdr:ListOpts
rm.Task: Hdr:Macros
rm.Task: Hdr:System
rm.Task: Hdr:SWIs
rm.Task: Hdr:CPU.Generic26
rm.Task: Hdr:IO.GenericIO
rm.Task: Hdr:RISCOS
rm.Task: Hdr:Proc
rm.Task: Hdr:ModHand
rm.Task: Hdr:Wimp
rm.Task: Hdr:WimpSpace
rm.Task: Hdr:EnvNumbers
rm.Task: Hdr:Messages
rm.Task: Hdr:Services
rm.Task: Hdr:UpCall
rm.Task: Hdr:FSNumbers
rm.Task: Hdr:NewErrors
rm.Task: Hdr:Variables
rm.Task: Hdr:MsgTrans
rm.Task: Version
rm.Task: "s.Messages"
rm.Task: Hdr:NDRDebug
rm.Task: "s.Redirect"
rm.Task: Hdr:PublicWS
rm.TaskWindow: Hdr:ListOpts
rm.TaskWindow: Hdr:Macros
rm.TaskWindow: Hdr:System
rm.TaskWindow: Hdr:SWIs
rm.TaskWindow: Hdr:CPU.Generic26
rm.TaskWindow: Hdr:IO.GenericIO
rm.TaskWindow: Hdr:RISCOS
rm.TaskWindow: Hdr:Proc
rm.TaskWindow: Hdr:ModHand
rm.TaskWindow: Hdr:Wimp
rm.TaskWindow: Hdr:WimpSpace
rm.TaskWindow: Hdr:EnvNumbers
rm.TaskWindow: Hdr:Messages
rm.TaskWindow: Hdr:Services
rm.TaskWindow: Hdr:UpCall
rm.TaskWindow: Hdr:FSNumbers
rm.TaskWindow: Hdr:NewErrors
rm.TaskWindow: Hdr:Variables
rm.TaskWindow: Hdr:MsgTrans
rm.TaskWindow: Hdr:FPEmulator
rm.TaskWindow: Version
rm.TaskWindow: "s.Messages"
rm.TaskWindow: Hdr:NDRDebug
rm.TaskWindow: "s.Redirect"
rm.TaskWindow: Hdr:PublicWS
