# Makefile for Global Assembler Header files
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name   Description
# ----       ----   -----------
# 26-May-94  AMcC   Created.
# 28-Jul-94  AMcC   removed build rules for h.swis (done by RISC_OSLib)
# 11-Aug-94  AMcC   Don't create an Arthur directory in Export.Hdr.Global
# 19-Oct-94  AMcC   Export ImageSize hdrs
# 31-Oct-94  AMcC   Export IO.IOMDL (IOMD for Morris)    
#

#
# Paths
#
HDRDIR = <hdr$dir>.Global

# Generic options:
#
MKDIR    = cdir
AS       = aasm
CP       = copy
RM       = remove
TOKENISE = tokenise

CFLAGS   = -c -depend !Depend -IC:
AFLAGS   = -depend !Depend -stamp -quit
CPFLAGS  = ~cfr~v

TOKENS   = Hdr:Tokens

#
# Program specific options:
#
COMPONENT = HdrSrc

EXPORTS   = \
 ${HDRDIR}.CMOS \
 ${HDRDIR}.CPU.ARM600 \
 ${HDRDIR}.CPU.Generic26 \
 ${HDRDIR}.DDVMacros \
 ${HDRDIR}.Debug \
 ${HDRDIR}.DevNos \
 ${HDRDIR}.ExtraLong \
 ${HDRDIR}.FDC.FDC711 \
 ${HDRDIR}.FileTypes \
 ${HDRDIR}.FSNumbers \
 ${HDRDIR}.Heap \
 ${HDRDIR}.ImageSize.2048K \
 ${HDRDIR}.ImageSize.4096K \
 ${HDRDIR}.IO.GenericIO \
 ${HDRDIR}.IO.IOC \
 ${HDRDIR}.IO.IOC-A1 \
 ${HDRDIR}.IO.IOEB \
 ${HDRDIR}.IO.IOMD \
 ${HDRDIR}.IO.IOMDL \
 ${HDRDIR}.KEYV \
 ${HDRDIR}.ListOpts \
 ${HDRDIR}.MEMM.ARM600 \
 ${HDRDIR}.MEMM.MEMC1 \
 ${HDRDIR}.Machine.Jordan \
 ${HDRDIR}.Machine.Morris \
 ${HDRDIR}.Macros \
 ${HDRDIR}.Messages \
 ${HDRDIR}.NdrDebug \
 ${HDRDIR}.NewErrors \
 ${HDRDIR}.PaletteV \
 ${HDRDIR}.PDriverReg \
 ${HDRDIR}.PDumperReg \
 ${HDRDIR}.PoduleReg \
 ${HDRDIR}.Pointer \
 ${HDRDIR}.Proc \
 ${HDRDIR}.Services \
 ${HDRDIR}.Sprite \
 ${HDRDIR}.Symbols \
 ${HDRDIR}.System \
 ${HDRDIR}.SWIs \
 ${HDRDIR}.Tokens \
 ${HDRDIR}.UpCall \
 ${HDRDIR}.VIDC.VIDC1a \
 ${HDRDIR}.VIDC.VIDC20

#
# Derived hdr files
#
FILETYPES = derived.FileTypes
SWIS      = derived.SWIs

#
# Generic rules:
#
all: ${FILETYPES} ${SWIS}
        @echo all derived hdrs are up to date

export: ${EXPORTS} Dirs
        @echo ${COMPONENT}: export complete

Dirs:
        ${MKDIR} <build$dir>.Export
        ${MKDIR} <build$dir>.Export.Hdr
        ${MKDIR} <build$dir>.Export.Hdr.Global
        ${MKDIR} <build$dir>.Export.Hdr.Interface
        ${MKDIR} ${HDRDIR}.CPU
        ${MKDIR} ${HDRDIR}.FDC
        ${MKDIR} ${HDRDIR}.IO
        ${MKDIR} ${HDRDIR}.ImageSize
        ${MKDIR} ${HDRDIR}.Machine
        ${MKDIR} ${HDRDIR}.MEMM
        ${MKDIR} ${HDRDIR}.VIDC

clean:
         @echo ${COMPONENT}: NOT cleaning derived headers

#clean:
#        ${RM} ${SWIS}
#        ${RM} ${FILETYPES}
#        @echo ${COMPONENT}: cleaned

#
# Rules for deriving headers:
#
${FILETYPES}: Register.ISV-Types s.DoTypes
        ${AS} ${AFLAGS} -from s.DoTypes -to $@ 
        settype $@ text

${SWIS}: Register.ISV-SWIs s.DoSWIs
        ${AS} ${AFLAGS} -from s.DoSWIs -to $@ 
        settype $@ text

#
# Rules for exporting:
#
${HDRDIR}.SWIs: ${SWIS};                       ${CP} ${SWIS} $@ ${CPFLAGS}
${HDRDIR}.FileTypes: ${FILETYPES};             ${CP} ${FILETYPES} $@ ${CPFLAGS}

# Registration headers:
${HDRDIR}.FSNumbers: Register.FSNumbers;       ${CP} Register.FSNumbers $@ ${CPFLAGS}
${HDRDIR}.PDriverReg: Register.PDriverReg;     ${CP} Register.PDriverReg $@ ${CPFLAGS}
${HDRDIR}.PDumperReg: Register.PDumperReg;     ${CP} Register.PDumperReg $@ ${CPFLAGS}
${HDRDIR}.PoduleReg: Register.PoduleReg;       ${CP} Register.PoduleReg $@ ${CPFLAGS}
${HDRDIR}.NewErrors: Register.NewErrors;       ${CP} Register.NewErrors $@ ${CPFLAGS}
${HDRDIR}.Services: Register.Services;         ${CP} Register.Services $@ ${CPFLAGS}
${HDRDIR}.UpCall: Register.UpCall;             ${CP} Register.UpCall $@ ${CPFLAGS}

# Machine/hardware specific headers:
${HDRDIR}.Machine.Jordan: hdr.Machine.Jordan;  ${CP} hdr.Machine.Jordan $@ ${CPFLAGS}
${HDRDIR}.Machine.Morris: hdr.Machine.Morris;  ${CP} hdr.Machine.Morris $@ ${CPFLAGS}
${HDRDIR}.ImageSize.2048K: hdr.ImageSize.2048K; ${CP} hdr.ImageSize.2048K $@ ${CPFLAGS}
${HDRDIR}.ImageSize.4096K: hdr.ImageSize.4096K; ${CP} hdr.ImageSize.4096K $@ ${CPFLAGS}
${HDRDIR}.CPU.ARM600: hdr.CPU.ARM600;          ${CP} hdr.CPU.ARM600 $@ ${CPFLAGS}
${HDRDIR}.CPU.Generic26: hdr.CPU.Generic26;    ${CP} hdr.CPU.Generic26 $@ ${CPFLAGS}
${HDRDIR}.FDC.FDC711: hdr.FDC.FDC711;          ${CP} hdr.FDC.FDC711 $@ ${CPFLAGS}
${HDRDIR}.IO.GenericIO: hdr.IO.GenericIO;      ${CP} hdr.IO.GenericIO $@ ${CPFLAGS}
${HDRDIR}.IO.IOC: hdr.IO.IOC;                  ${CP} hdr.IO.IOC $@ ${CPFLAGS}
${HDRDIR}.IO.IOC-A1: hdr.IO.IOC-A1;            ${CP} hdr.IO.IOC-A1 $@ ${CPFLAGS}
${HDRDIR}.IO.IOEB: hdr.IO.IOEB;                ${CP} hdr.IO.IOEB $@ ${CPFLAGS}
${HDRDIR}.IO.IOMD: hdr.IO.IOMD;                ${CP} hdr.IO.IOMD $@ ${CPFLAGS}
${HDRDIR}.IO.IOMDL: hdr.IO.IOMDL;              ${CP} hdr.IO.IOMDL $@ ${CPFLAGS}
${HDRDIR}.MEMM.ARM600: hdr.MEMM.ARM600;        ${CP} hdr.MEMM.ARM600 $@ ${CPFLAGS}
${HDRDIR}.MEMM.MEMC1: hdr.MEMM.MEMC1;          ${CP} hdr.MEMM.MEMC1 $@ ${CPFLAGS}
${HDRDIR}.VIDC.VIDC1a: hdr.VIDC.VIDC1a;        ${CP} hdr.VIDC.VIDC1a $@ ${CPFLAGS}
${HDRDIR}.VIDC.VIDC20: hdr.VIDC.VIDC20;        ${CP} hdr.VIDC.VIDC20 $@ ${CPFLAGS}

# Macros:
${HDRDIR}.DDVMacros: hdr.DDVMacros;            ${CP} hdr.DDVMacros $@ ${CPFLAGS}
${HDRDIR}.Debug: hdr.Debug;                    ${CP} hdr.Debug $@ ${CPFLAGS}
${HDRDIR}.ExtraLong: hdr.ExtraLong;            ${CP} hdr.ExtraLong $@ ${CPFLAGS}
${HDRDIR}.Macros: hdr.Macros;                  ${CP} hdr.Macros $@ ${CPFLAGS}
${HDRDIR}.NdrDebug: hdr.NdrDebug;              ${CP} hdr.NdrDebug $@ ${CPFLAGS}
${HDRDIR}.Proc: hdr.Proc;                      ${CP} hdr.Proc $@ ${CPFLAGS}

# The rest:
${HDRDIR}.CMOS: hdr.CMOS;                      ${CP} hdr.CMOS $@ ${CPFLAGS}
${HDRDIR}.DevNos: hdr.DevNos;                  ${CP} hdr.DevNos $@ ${CPFLAGS}
${HDRDIR}.Heap: hdr.Heap;                      ${CP} hdr.Heap $@ ${CPFLAGS}
${HDRDIR}.KEYV: hdr.KEYV;                      ${CP} hdr.KEYV $@ ${CPFLAGS}
${HDRDIR}.ListOpts: hdr.ListOpts;              ${CP} hdr.ListOpts $@ ${CPFLAGS}
${HDRDIR}.Messages: hdr.Messages;              ${CP} hdr.Messages $@ ${CPFLAGS}
${HDRDIR}.PaletteV: hdr.PaletteV;              ${CP} hdr.PaletteV $@ ${CPFLAGS}
${HDRDIR}.Pointer: hdr.Pointer;                ${CP} hdr.Pointer $@ ${CPFLAGS}
${HDRDIR}.Sprite: hdr.Sprite;                  ${CP} hdr.Sprite $@ ${CPFLAGS}
${HDRDIR}.Symbols: hdr.Symbols;                ${CP} hdr.Symbols $@ ${CPFLAGS}
${HDRDIR}.System: hdr.System;                  ${CP} hdr.System $@ ${CPFLAGS}
${HDRDIR}.Tokens: hdr.Tokens;                  ${CP} hdr.Tokens $@ ${CPFLAGS}

# Dynamic dependencies:
derived.FileTypes: Hdr:ListOpts
derived.FileTypes: register.ISV-Types
derived.SWIs: Hdr:ListOpts
derived.SWIs: register.ISV-SWIs
