# Makefile for Econet
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name         Description
# ----       ----         -----------
# 28-Jun-94  AMcC         Created.
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
MODGEN   = modgen
RM       = remove
TOKENISE = tokenise

AFLAGS   = -depend !Depend -stamp -closeexec -quit
CPFLAGS  = ~cfr~v

TOKENS   = Hdr:Tokens

#
# Program specific options:
#
COMPONENT   = Econet
SOURCE      = NewOS
SOURCE200   = OldOS
TARGET      = rm.Econet
TARGET200   = rm.Econet200
HDR         = hdr.${COMPONENT}
EXPORTS     = ${EXP_HDR}.Econet

MESSAGESMOD = rm.EconetMsgs
MESSAGES    = Resources.${LOCALE}.Messages
RESPATH     = Resources.Econet.Messages
MODNAME     = EconetMessages
MODHELP     = EconetMessages

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

install_rom: $(TARGET)
        $(CP) $(TARGET) $(INSTDIR).$(COMPONENT) $(CPFLAGS)
        @echo ${COMPONENT}: rom module installed

install: ${TARGET}
        ${CP} ${TARGET} ${INSTDIR}.${COMPONENT} ${CPFLAGS}
        @echo ${COMPONENT}: module installed

clean:
        ${RM} ${TARGET}
        ${RM} ${TARGET200}
        ${RM} ${MESSAGESMOD}
        ${RM} setversion
        @echo ${COMPONENT}: cleaned

resources:
        ${MKDIR} ${RESDIR}.${COMPONENT}
        ${CP} Resources.${LOCALE}.Messages ${RESDIR}.${COMPONENT}.Messages ${CPFLAGS}
        @echo ${COMPONENT}: resource files copied

#
# Assemble the Econet module
#
${TARGET}: ${SOURCE}
        ${AS} ${SOURCE} $@ ${AFLAGS} -module

${TARGET200}: ${SOURCE200}
        ${AS} ${SOURCE200} $@ ${AFLAGS} -module

#
# Export hdr files
#
${EXP_HDR}.Econet: hdr.Econet
        ${CP} hdr.Econet $@ ${CPFLAGS}

# 
# Generate an Econet Messages module
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
        ${AS} utils.getversion $@ ${AFLAGS}
        settype setversion obey

maketime:
        MakeTime

version:
        Version

#---------------------------------------------------------------------------
# Dynamic dependencies:
rm.Econet200: s.Module
rm.Econet200: Hdr:ListOpts
rm.Econet200: Hdr:Macros
rm.Econet200: Hdr:System
rm.Econet200: Hdr:SWIs
rm.Econet200: Hdr:CPU.Generic26
rm.Econet200: Hdr:IO.GenericIO
rm.Econet200: Hdr:RISCOS
rm.Econet200: Hdr:CPU.ARM600
rm.Econet200: Hdr:IO.IOC-A1
rm.Econet200: Hdr:IO.IOC
rm.Econet200: Hdr:VIDC.VIDC1A
rm.Econet200: Hdr:MEMM.MEMC1
rm.Econet200: Hdr:Symbols
rm.Econet200: Hdr:FSNumbers
rm.Econet200: Hdr:CMOS
rm.Econet200: Hdr:ModHand
rm.Econet200: Hdr:HostFS
rm.Econet200: Hdr:Debug
rm.Econet200: Hdr:Econet
rm.Econet200: Hdr:Services
rm.Econet200: Hdr:NewErrors
rm.Econet200: Hdr:Tokens
rm.Econet200: Hdr:MsgTrans
rm.Econet200: Hdr:Portable
rm.Econet200: Hdr:Podule
rm.Econet200: Hdr:PoduleReg
rm.Econet200: s.Macros
rm.Econet200: Time+Date
rm.Econet200: s.Memory
rm.Econet200: s.Interface
rm.Econet200: s.Commands
rm.Econet200: s.Receive
rm.Econet200: s.Transmit
rm.Econet200: s.Background
setversion: Time+Date
rm.Econet: s.Module
rm.Econet: Hdr:ListOpts
rm.Econet: Hdr:Macros
rm.Econet: Hdr:System
rm.Econet: Hdr:SWIs
rm.Econet: Hdr:CPU.Generic26
rm.Econet: Hdr:IO.GenericIO
rm.Econet: Hdr:RISCOS
rm.Econet: Hdr:CPU.ARM600
rm.Econet: Hdr:IO.IOC-A1
rm.Econet: Hdr:IO.IOC
rm.Econet: Hdr:VIDC.VIDC1A
rm.Econet: Hdr:MEMM.MEMC1
rm.Econet: Hdr:Symbols
rm.Econet: Hdr:FSNumbers
rm.Econet: Hdr:CMOS
rm.Econet: Hdr:ModHand
rm.Econet: Hdr:HostFS
rm.Econet: Hdr:Debug
rm.Econet: Hdr:Econet
rm.Econet: Hdr:Services
rm.Econet: Hdr:NewErrors
rm.Econet: Hdr:Tokens
rm.Econet: Hdr:MsgTrans
rm.Econet: Hdr:Portable
rm.Econet: Hdr:Podule
rm.Econet: Hdr:PoduleReg
rm.Econet: s.Macros
rm.Econet: Time+Date
rm.Econet: s.Memory
rm.Econet: s.Interface
rm.Econet: s.Commands
rm.Econet: s.Receive
rm.Econet: s.Transmit
rm.Econet: s.Background
