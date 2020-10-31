# Makefile for PDumperLJ (Printer dumper for LaserJets)
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
COMPONENT = PDumperLJ
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
^.rm.PDumperLJ: ^.Generic.s.Header
^.rm.PDumperLJ: hdr:ListOpts
^.rm.PDumperLJ: hdr:Macros
^.rm.PDumperLJ: hdr:System
^.rm.PDumperLJ: Hdr:SWIs
^.rm.PDumperLJ: Hdr:CPU.Generic26
^.rm.PDumperLJ: Hdr:IO.GenericIO
^.rm.PDumperLJ: Hdr:RISCOS
^.rm.PDumperLJ: hdr:FSNumbers
^.rm.PDumperLJ: hdr:HighFSI
^.rm.PDumperLJ: hdr:Modhand
^.rm.PDumperLJ: hdr:NewErrors
^.rm.PDumperLJ: hdr:PDriver
^.rm.PDumperLJ: hdr:PDriverReg
^.rm.PDumperLJ: hdr:PDumper
^.rm.PDumperLJ: hdr:PDumperReg
^.rm.PDumperLJ: hdr:Services
^.rm.PDumperLJ: hdr:Sprite
^.rm.PDumperLJ: hdr:ColourTran
^.rm.PDumperLJ: hdr:Proc
^.rm.PDumperLJ: hdr:MsgTrans
^.rm.PDumperLJ: hdr:HostFS
^.rm.PDumperLJ: hdr:NDRDebug
^.rm.PDumperLJ: hdr:DDVMacros
^.rm.PDumperLJ: hdr:HostDebug
^.rm.PDumperLJ: s.Version
^.rm.PDumperLJ: ^.Version
^.rm.PDumperLJ: s.Macros
^.rm.PDumperLJ: ^.Generic.s.Macros
^.rm.PDumperLJ: s.Workspace
^.rm.PDumperLJ: s.BranchCode
^.rm.PDumperLJ: ^.Generic.s.BranchCode
^.rm.PDumperLJ: s.24Bit
^.rm.PDumperLJ: ^.Generic.s.24Bit
^.rm.PDumperLJ: s.SetDriver
^.rm.PDumperLJ: ^.Generic.s.SetDriver
^.rm.PDumperLJ: s.OutputDump
^.rm.PDumperLJ: ^.Generic.s.OutputDump
^.rm.PDumperLJ: s.ColourSet
^.rm.PDumperLJ: ^.Generic.s.ColourSet
^.rm.PDumperLJ: s.StartPage
^.rm.PDumperLJ: ^.Generic.s.SendExtra
^.rm.PDumperLJ: s.EndPage
^.rm.PDumperLJ: s.AbortJob
^.rm.PDumperLJ: ^.Generic.s.AbortJob
^.rm.PDumperLJ: s.StartJob
^.rm.PDumperLJ: s.MiscOp
^.rm.PDumperLJ: ^.Generic.s.MiscOp
