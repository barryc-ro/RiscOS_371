# Makefile for PDumperIW (Printer dumper for ImageWriters)
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
COMPONENT = PDumperIW
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
^.rm.PDumperIW: ^.Generic.s.Header
^.rm.PDumperIW: hdr:ListOpts
^.rm.PDumperIW: hdr:Macros
^.rm.PDumperIW: hdr:System
^.rm.PDumperIW: Hdr:SWIs
^.rm.PDumperIW: Hdr:CPU.Generic26
^.rm.PDumperIW: Hdr:IO.GenericIO
^.rm.PDumperIW: Hdr:RISCOS
^.rm.PDumperIW: hdr:FSNumbers
^.rm.PDumperIW: hdr:HighFSI
^.rm.PDumperIW: hdr:Modhand
^.rm.PDumperIW: hdr:NewErrors
^.rm.PDumperIW: hdr:PDriver
^.rm.PDumperIW: hdr:PDriverReg
^.rm.PDumperIW: hdr:PDumper
^.rm.PDumperIW: hdr:PDumperReg
^.rm.PDumperIW: hdr:Services
^.rm.PDumperIW: hdr:Sprite
^.rm.PDumperIW: hdr:ColourTran
^.rm.PDumperIW: hdr:Proc
^.rm.PDumperIW: hdr:MsgTrans
^.rm.PDumperIW: hdr:HostFS
^.rm.PDumperIW: hdr:NDRDebug
^.rm.PDumperIW: hdr:DDVMacros
^.rm.PDumperIW: hdr:HostDebug
^.rm.PDumperIW: s.Version
^.rm.PDumperIW: ^.Version
^.rm.PDumperIW: s.Macros
^.rm.PDumperIW: ^.Generic.s.Macros
^.rm.PDumperIW: s.Workspace
^.rm.PDumperIW: s.BranchCode
^.rm.PDumperIW: ^.Generic.s.BranchCode
^.rm.PDumperIW: s.24Bit
^.rm.PDumperIW: ^.Generic.s.24Bit
^.rm.PDumperIW: s.SetDriver
^.rm.PDumperIW: ^.Generic.s.SetDriver
^.rm.PDumperIW: s.OutputDump
^.rm.PDumperIW: ^.Generic.s.OutputDump
^.rm.PDumperIW: s.ColourSet
^.rm.PDumperIW: ^.Generic.s.ColourSet
^.rm.PDumperIW: s.StartPage
^.rm.PDumperIW: ^.Generic.s.SendExtra
^.rm.PDumperIW: s.EndPage
^.rm.PDumperIW: ^.Generic.s.EndPage
^.rm.PDumperIW: s.AbortJob
^.rm.PDumperIW: ^.Generic.s.AbortJob
^.rm.PDumperIW: s.StartJob
^.rm.PDumperIW: ^.Generic.s.StartJob
^.rm.PDumperIW: s.MiscOp
^.rm.PDumperIW: ^.Generic.s.MiscOp
