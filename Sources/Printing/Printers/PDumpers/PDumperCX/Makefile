# Makefile for PDumperCX
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name         Description
# ----       ----         -----------
# 24-Jul-95  MJS         Created.
#

#
# Generic options:
#
MKDIR   = cdir
AS      = aasm
CP      = copy
RM      = remove
CCFLAGS = -c -depend !Depend -IC:
ASFLAGS = -depend !Depend -Stamp -quit -module
CPFLAGS = ~cfr~v

#
# Program specific options:
#
COMPONENT = PDumperCX
SOURCE    = s.Header
TARGET    = ^.rm.${COMPONENT}

#
# Generic rules:
#
all: ${TARGET}
        @echo ${COMPONENT}: all built

${TARGET}: ${SOURCE}
        ${AS} ${ASFLAGS} -To $@ -From ${SOURCE}

# Dynamic dependencies:
^.rm.PDumperE2: ^.Generic.s.Header
^.rm.PDumperE2: hdr:ListOpts
^.rm.PDumperE2: hdr:Macros
^.rm.PDumperE2: hdr:System
^.rm.PDumperE2: Hdr:SWIs
^.rm.PDumperE2: Hdr:CPU.Generic26
^.rm.PDumperE2: Hdr:IO.GenericIO
^.rm.PDumperE2: Hdr:RISCOS
^.rm.PDumperE2: hdr:FSNumbers
^.rm.PDumperE2: hdr:HighFSI
^.rm.PDumperE2: hdr:Modhand
^.rm.PDumperE2: hdr:NewErrors
^.rm.PDumperE2: hdr:PDriver
^.rm.PDumperE2: hdr:PDriverReg
^.rm.PDumperE2: hdr:PDumper
^.rm.PDumperE2: hdr:PDumperReg
^.rm.PDumperE2: hdr:Services
^.rm.PDumperE2: hdr:Sprite
^.rm.PDumperE2: hdr:ColourTran
^.rm.PDumperE2: hdr:Proc
^.rm.PDumperE2: hdr:MsgTrans
^.rm.PDumperE2: hdr:HostFS
^.rm.PDumperE2: hdr:NDRDebug
^.rm.PDumperE2: hdr:DDVMacros
^.rm.PDumperE2: hdr:HostDebug
^.rm.PDumperE2: s.Version
^.rm.PDumperE2: ^.Version
^.rm.PDumperE2: s.Macros
^.rm.PDumperE2: ^.Generic.s.Macros
^.rm.PDumperE2: s.Workspace
^.rm.PDumperE2: s.BranchCode
^.rm.PDumperE2: ^.Generic.s.BranchCode
^.rm.PDumperE2: s.24Bit
^.rm.PDumperE2: ^.Generic.s.24Bit
^.rm.PDumperE2: s.SetDriver
^.rm.PDumperE2: ^.Generic.s.SetDriver
^.rm.PDumperE2: s.OutputDump
^.rm.PDumperE2: ^.Generic.s.OutputDump
^.rm.PDumperE2: s.ColourSet
^.rm.PDumperE2: ^.Generic.s.ColourSet
^.rm.PDumperE2: s.StartPage
^.rm.PDumperE2: ^.Generic.s.SendExtra
^.rm.PDumperE2: s.EndPage
^.rm.PDumperE2: ^.Generic.s.EndPage
^.rm.PDumperE2: s.AbortJob
^.rm.PDumperE2: ^.Generic.s.AbortJob
^.rm.PDumperE2: s.StartJob
^.rm.PDumperE2: s.MiscOp
^.rm.PDumperE2: ^.Generic.s.MiscOp
^.rm.PDumperCX: ^.Generic.s.Header
^.rm.PDumperCX: hdr:ListOpts
^.rm.PDumperCX: hdr:Macros
^.rm.PDumperCX: hdr:System
^.rm.PDumperCX: Hdr:SWIs
^.rm.PDumperCX: Hdr:CPU.Generic26
^.rm.PDumperCX: Hdr:IO.GenericIO
^.rm.PDumperCX: Hdr:RISCOS
^.rm.PDumperCX: hdr:FSNumbers
^.rm.PDumperCX: hdr:HighFSI
^.rm.PDumperCX: hdr:Modhand
^.rm.PDumperCX: hdr:NewErrors
^.rm.PDumperCX: hdr:PDriver
^.rm.PDumperCX: hdr:PDriverReg
^.rm.PDumperCX: hdr:PDumper
^.rm.PDumperCX: hdr:PDumperReg
^.rm.PDumperCX: hdr:Services
^.rm.PDumperCX: hdr:Sprite
^.rm.PDumperCX: hdr:ColourTran
^.rm.PDumperCX: hdr:Proc
^.rm.PDumperCX: hdr:MsgTrans
^.rm.PDumperCX: hdr:HostFS
^.rm.PDumperCX: hdr:NDRDebug
^.rm.PDumperCX: hdr:DDVMacros
^.rm.PDumperCX: hdr:HostDebug
^.rm.PDumperCX: s.Version
^.rm.PDumperCX: ^.Version
^.rm.PDumperCX: s.Macros
^.rm.PDumperCX: ^.Generic.s.Macros
^.rm.PDumperCX: s.Workspace
^.rm.PDumperCX: s.BranchCode
^.rm.PDumperCX: ^.Generic.s.BranchCode
^.rm.PDumperCX: s.24Bit
^.rm.PDumperCX: ^.Generic.s.24Bit
^.rm.PDumperCX: s.SetDriver
^.rm.PDumperCX: ^.Generic.s.SetDriver
^.rm.PDumperCX: s.OutputDump
^.rm.PDumperCX: ^.Generic.s.OutputDump
^.rm.PDumperCX: s.ColourSet
^.rm.PDumperCX: ^.Generic.s.ColourSet
^.rm.PDumperCX: s.StartPage
^.rm.PDumperCX: ^.Generic.s.SendExtra
^.rm.PDumperCX: s.EndPage
^.rm.PDumperCX: ^.Generic.s.EndPage
^.rm.PDumperCX: s.AbortJob
^.rm.PDumperCX: ^.Generic.s.AbortJob
^.rm.PDumperCX: s.StartJob
^.rm.PDumperCX: s.MiscOp
^.rm.PDumperCX: ^.Generic.s.MiscOp
