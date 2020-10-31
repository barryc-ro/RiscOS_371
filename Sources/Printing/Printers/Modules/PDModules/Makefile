# Makefile for PDModules (Printer Driver Modules - Dot Matrix & PostScript)
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name         Description
# ----       ----         -----------
# 04-Jul-94  AMcC         Created.
#

#
# Program specific options:
#
COMPONENT = PDModules
TARGETS   = rm.PDriverDP \
            rm.PDriverPS

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
# Generic rules:
#
all: ${TARGETS}
        @echo ${COMPONENT}: all built (disc)

rom: ${TARGETS}
        @echo ${COMPONENT}: all built (rom)

export: ${EXPORTS}
        @echo ${COMPONENT}: export complete

install: ${TARGETS}
        ${CP} rm.PDriverDP ${INSTDIR}.PDriverDP ${CPFLAGS}
        ${CP} rm.PDriverPS ${INSTDIR}.PDriverPS ${CPFLAGS}
        Access ${INSTDIR}.PDriverDP lr/r
        Access ${INSTDIR}.PDriverPS lr/r
        @echo ${COMPONENT}: installed (disc)

install_rom: ${TARGETS}
        ${CP} rm.PDriverDP ${INSTDIR}.PDriverDP ${CPFLAGS}
        ${CP} rm.PDriverPS ${INSTDIR}.PDriverPS ${CPFLAGS}
        @echo ${COMPONENT}: installed (rom)

clean:
        ${RM} rm.PDriverDP
        ${RM} rm.PDriverPS
        @echo ${COMPONENT}: cleaned

rm.PDriverDP: s.PrinterDP
        ${AS} ${ASFLAGS} -To $@ -From s.PrinterDP

rm.PDriverPS: s.PrinterPS
        ${AS} ${ASFLAGS} -To $@ -From s.PrinterPS

# Dynamic dependencies:
rm.PDriverDP: Version
rm.PDriverDP: s.Core.PDriver
rm.PDriverDP: Hdr:ListOpts
rm.PDriverDP: Hdr:Macros
rm.PDriverDP: Hdr:System
rm.PDriverDP: Hdr:SWIs
rm.PDriverDP: Hdr:CPU.Generic26
rm.PDriverDP: Hdr:IO.GenericIO
rm.PDriverDP: Hdr:RISCOS
rm.PDriverDP: Hdr:ModHand
rm.PDriverDP: Hdr:Services
rm.PDriverDP: Hdr:Symbols
rm.PDriverDP: Hdr:FSNumbers
rm.PDriverDP: Hdr:HighFSI
rm.PDriverDP: Hdr:NewErrors
rm.PDriverDP: Hdr:Variables
rm.PDriverDP: Hdr:PDriver
rm.PDriverDP: Hdr:VduExt
rm.PDriverDP: Hdr:ColourTran
rm.PDriverDP: Hdr:Draw
rm.PDriverDP: Hdr:Sprite
rm.PDriverDP: Hdr:SprExtend
rm.PDriverDP: Hdr:Font
rm.PDriverDP: Hdr:PDumper
rm.PDriverDP: Hdr:Proc
rm.PDriverDP: Hdr:MsgTrans
rm.PDriverDP: Hdr:PaletteV
rm.PDriverDP: hdr:HostFS
rm.PDriverDP: hdr:NDRDebug
rm.PDriverDP: s.Core.Constants
rm.PDriverDP: s.PDriverDP.Constants
rm.PDriverDP: hdr:Wimp
rm.PDriverDP: s.Core.Workspace
rm.PDriverDP: s.PDriverDP.GlobalWS
rm.PDriverDP: s.PDriverDP.JobWS
rm.PDriverDP: s.Core.Header
rm.PDriverDP: s.PDriverDP.Macros
rm.PDriverDP: hdr:DDVMacros
rm.PDriverDP: s.Core.SWIs
rm.PDriverDP: s.Core.Colour
rm.PDriverDP: s.Core.Vdu5
rm.PDriverDP: s.Core.JobManager
rm.PDriverDP: s.Core.Intercept
rm.PDriverDP: s.Core.Wrch
rm.PDriverDP: s.Core.ColTrans
rm.PDriverDP: s.Core.Draw
rm.PDriverDP: s.Core.Sprite
rm.PDriverDP: s.Core.OSByte
rm.PDriverDP: s.Core.FontSWI
rm.PDriverDP: s.Core.JPEGSWI
rm.PDriverDP: s.Core.Device
rm.PDriverDP: s.PDriverDP.Configure
rm.PDriverDP: s.PDriverDP.ManageJob
rm.PDriverDP: s.PDriverDP.PageBox
rm.PDriverDP: s.PDriverDP.Colour
rm.PDriverDP: s.PDriverDP.Plot
rm.PDriverDP: s.PDriverDP.Draw
rm.PDriverDP: s.PDriverDP.Sprite
rm.PDriverDP: s.PDriverDP.TranSprite
rm.PDriverDP: s.PDriverDP.Vdu5
rm.PDriverDP: s.PDriverDP.Font
rm.PDriverDP: s.PDriverDP.JPEG
rm.PDriverDP: s.PDriverDP.ScreenDump
rm.PDriverDP: s.PDriverDP.Picture
rm.PDriverDP: s.PDriverDP.Private
rm.PDriverDP: s.PDriverDP.Private2
rm.PDriverDP: s.PDriverDP.MiscOp
rm.PDriverDP: s.Core.Error
rm.PDriverDP: s.Core.MsgCode
rm.PDriverPS: Version
rm.PDriverPS: s.Core.PDriver
rm.PDriverPS: Hdr:ListOpts
rm.PDriverPS: Hdr:Macros
rm.PDriverPS: Hdr:System
rm.PDriverPS: Hdr:SWIs
rm.PDriverPS: Hdr:CPU.Generic26
rm.PDriverPS: Hdr:IO.GenericIO
rm.PDriverPS: Hdr:RISCOS
rm.PDriverPS: Hdr:ModHand
rm.PDriverPS: Hdr:Services
rm.PDriverPS: Hdr:Symbols
rm.PDriverPS: Hdr:FSNumbers
rm.PDriverPS: Hdr:HighFSI
rm.PDriverPS: Hdr:NewErrors
rm.PDriverPS: Hdr:Variables
rm.PDriverPS: Hdr:PDriver
rm.PDriverPS: Hdr:VduExt
rm.PDriverPS: Hdr:ColourTran
rm.PDriverPS: Hdr:Draw
rm.PDriverPS: Hdr:Sprite
rm.PDriverPS: Hdr:SprExtend
rm.PDriverPS: Hdr:Font
rm.PDriverPS: Hdr:PDumper
rm.PDriverPS: Hdr:Proc
rm.PDriverPS: Hdr:MsgTrans
rm.PDriverPS: Hdr:PaletteV
rm.PDriverPS: hdr:HostFS
rm.PDriverPS: hdr:NDRDebug
rm.PDriverPS: s.Core.Constants
rm.PDriverPS: s.PDriverPS.Constants
rm.PDriverPS: s.Core.Workspace
rm.PDriverPS: s.PDriverPS.GlobalWS
rm.PDriverPS: s.PDriverPS.JobWS
rm.PDriverPS: s.Core.Header
rm.PDriverPS: s.PDriverPS.Macros
rm.PDriverPS: hdr:DDVMacros
rm.PDriverPS: s.Core.SWIs
rm.PDriverPS: s.Core.Colour
rm.PDriverPS: s.Core.Vdu5
rm.PDriverPS: s.Core.JobManager
rm.PDriverPS: s.Core.Intercept
rm.PDriverPS: s.Core.Wrch
rm.PDriverPS: s.Core.ColTrans
rm.PDriverPS: s.Core.Draw
rm.PDriverPS: s.Core.Sprite
rm.PDriverPS: s.Core.OSByte
rm.PDriverPS: s.Core.FontSWI
rm.PDriverPS: s.Core.JPEGSWI
rm.PDriverPS: s.Core.Device
rm.PDriverPS: s.PDriverPS.Configure
rm.PDriverPS: s.PDriverPS.ManageJob
rm.PDriverPS: s.PDriverPS.PageBox
rm.PDriverPS: Hdr:Territory
rm.PDriverPS: Hdr:MakePSFont
rm.PDriverPS: s.PDriverPS.Colour
rm.PDriverPS: s.PDriverPS.Plot
rm.PDriverPS: s.PDriverPS.Draw
rm.PDriverPS: s.PDriverPS.Sprite
rm.PDriverPS: s.PDriverPS.TranSprite
rm.PDriverPS: s.PDriverPS.Vdu5
rm.PDriverPS: s.PDriverPS.Font
rm.PDriverPS: s.PDriverPS.JPEG
rm.PDriverPS: s.PDriverPS.ScreenDump
rm.PDriverPS: s.PDriverPS.Picture
rm.PDriverPS: s.PDriverPS.Private
rm.PDriverPS: s.PDriverPS.MiscOp
rm.PDriverPS: s.Core.Error
rm.PDriverPS: s.Core.MsgCode
