# Makefile for Broadcast
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name         Description
# ----       ----         -----------
# 25-Aug-94  AMcC         Created.
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
COMPONENT   = Broadcast
SOURCE      = NewOS
SOURCE200   = OldOS
TARGET      = rm.Broadcast
TARGET200   = rm.Broadc200

#
# Rules:
#
all: ${TARGET}
        @echo ${COMPONENT}: ${TARGET} built

all200: ${TARGET200}
        @echo ${COMPONENT}: ${TARGET200} built

#
# Generic Build rules:
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
        ${RM} ${TARGET200}
        @echo ${COMPONENT}: cleaned

#
# Assemble the module
#
${TARGET}: ${SOURCE}
        ${AS} ${SOURCE} $@ ${AFLAGS} -module

${TARGET200}: ${SOURCE200}
        ${AS} ${SOURCE200} $@ ${AFLAGS} -module

maketime:
        MakeTime

version:
        Version

#---------------------------------------------------------------------------
# Dynamic dependencies:
rm.Broadc200: s.Module
rm.Broadc200: Hdr:ListOpts
rm.Broadc200: Hdr:Macros
rm.Broadc200: Hdr:System
rm.Broadc200: Hdr:SWIs
rm.Broadc200: Hdr:CPU.Generic26
rm.Broadc200: Hdr:IO.GenericIO
rm.Broadc200: Hdr:RISCOS
rm.Broadc200: Hdr:ModHand
rm.Broadc200: Hdr:Services
rm.Broadc200: Hdr:FSNumbers
rm.Broadc200: Hdr:HighFSI
rm.Broadc200: Hdr:LowFSI
rm.Broadc200: Hdr:Econet
rm.Broadc200: Hdr:NewErrors
rm.Broadc200: Hdr:CMOS
rm.Broadc200: Hdr:MsgTrans
rm.Broadc200: Hdr:Symbols
rm.Broadc200: Time+Date
rm.Broadc200: s.Memory
rm.Broadc200: s.Load
rm.Broadc200: s.Client
rm.Broadc200: s.Server
rm.Broadc200: s.Event
rm.Broadcast: s.Module
rm.Broadcast: Hdr:ListOpts
rm.Broadcast: Hdr:Macros
rm.Broadcast: Hdr:System
rm.Broadcast: Hdr:SWIs
rm.Broadcast: Hdr:CPU.Generic26
rm.Broadcast: Hdr:IO.GenericIO
rm.Broadcast: Hdr:RISCOS
rm.Broadcast: Hdr:ModHand
rm.Broadcast: Hdr:Services
rm.Broadcast: Hdr:FSNumbers
rm.Broadcast: Hdr:HighFSI
rm.Broadcast: Hdr:LowFSI
rm.Broadcast: Hdr:Econet
rm.Broadcast: Hdr:NewErrors
rm.Broadcast: Hdr:CMOS
rm.Broadcast: Hdr:MsgTrans
rm.Broadcast: Hdr:Symbols
rm.Broadcast: Time+Date
rm.Broadcast: s.Debug
rm.Broadcast: s.Memory
rm.Broadcast: s.Load
rm.Broadcast: s.Client
rm.Broadcast: s.Server
rm.Broadcast: s.Event
