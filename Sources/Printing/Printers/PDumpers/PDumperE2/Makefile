# Makefile for PDumperE2
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name         Description
# ----       ----         -----------
# 27-May-94  AMcC         Created.
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
COMPONENT = PDumperE2
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
