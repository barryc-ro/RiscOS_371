# Makefile for Kernel
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
ASFLAGS = -depend !Depend -Stamp -quit -To $@ -From
CPFLAGS = ~cfr~v

TOKENISE = tokenise
TOKENS   = Hdr:Tokens

#
# Program specific options:
#
COMPONENT = Kernel
SOURCE    = s.GetAll
TARGET    = rm.${MACHINE}.Kernel
EXPORTS   = ${EXP_HDR}.EnvNumbers \
            ${EXP_HDR}.ModHand \
            ${EXP_HDR}.PublicWS \
            ${EXP_HDR}.RISCOS \
            ${EXP_HDR}.Variables \
            ${EXP_HDR}.VduExt

#
# Generic rules:
#
rom: ${TARGET}
        @echo ${COMPONENT}: rom module built

install_rom: ${TARGET}
        ${CP} ${TARGET} ${INSTDIR}.${COMPONENT} ${CPFLAGS}
        @echo ${COMPONENT}: rom module installed

clean:
        ${RM} ${TARGET}
        ${RM} TMOSHelp
        @echo ${COMPONENT}: cleaned

export: ${EXPORTS}
        @echo ${COMPONENT}: export complete

resources:
        ${MKDIR} ${RESDIR}.${COMPONENT}
        ${CP} Resources.${LOCALE}.Messages  ${RESDIR}.${COMPONENT}.Messages  ${CPFLAGS}
        @echo ${COMPONENT}: resource files copied

${TARGET}: ${SOURCE} s.TMOSHelp
        ${MKDIR} rm.${MACHINE}
        ${AS} ${ASFLAGS} ${SOURCE}
        stamp $@

s.TMOSHelp: ${TOKENS} HelpStrs
        ${TOKENISE} ${TOKENS} HelpStrs $@

#
# Exported interface headers
#
${EXP_HDR}.EnvNumbers: hdr.EnvNumbers
        ${CP} hdr.EnvNumbers $@ ${CPFLAGS}

${EXP_HDR}.ModHand: hdr.ModHand
        ${CP} hdr.ModHand $@ ${CPFLAGS}

${EXP_HDR}.PublicWS: hdr.PublicWS
        ${CP} hdr.PublicWS $@ ${CPFLAGS}

${EXP_HDR}.RISCOS: hdr.RISCOS
        ${CP} hdr.RISCOS $@ ${CPFLAGS}

${EXP_HDR}.VduExt: hdr.VduExt
        ${CP} hdr.VduExt $@ ${CPFLAGS}

${EXP_HDR}.Variables: hdr.Variables
        ${CP} hdr.Variables $@ ${CPFLAGS}

# Dynamic dependencies:
rm.Jordan.Kernel: Hdr:ListOpts
rm.Jordan.Kernel: Hdr:Macros
rm.Jordan.Kernel: Hdr:System
rm.Jordan.Kernel: Hdr:SWIs
rm.Jordan.Kernel: Hdr:CPU.Generic26
rm.Jordan.Kernel: Hdr:IO.GenericIO
rm.Jordan.Kernel: Hdr:RISCOS
rm.Jordan.Kernel: Hdr:Machine.<Machine>
rm.Jordan.Kernel: Hdr:CPU.ARM600
rm.Jordan.Kernel: Hdr:IO.IOMD
rm.Jordan.Kernel: Hdr:IO.IOMD
rm.Jordan.Kernel: Hdr:MEMM.ARM600
rm.Jordan.Kernel: Hdr:VIDC.VIDC20
rm.Jordan.Kernel: Version
rm.Jordan.Kernel: Hdr:CMOS
rm.Jordan.Kernel: Hdr:Heap
rm.Jordan.Kernel: Hdr:PublicWS
rm.Jordan.Kernel: Hdr:KernelWS
rm.Jordan.Kernel: Hdr:Services
rm.Jordan.Kernel: Hdr:FSNumbers
rm.Jordan.Kernel: Hdr:HighFSI
rm.Jordan.Kernel: Hdr:NewErrors
rm.Jordan.Kernel: Hdr:Proc
rm.Jordan.Kernel: Hdr:Sprite
rm.Jordan.Kernel: Hdr:KeyWS
rm.Jordan.Kernel: Hdr:RS423
rm.Jordan.Kernel: Hdr:ModHand
rm.Jordan.Kernel: Hdr:Variables
rm.Jordan.Kernel: Hdr:EnvNumbers
rm.Jordan.Kernel: Hdr:UpCall
rm.Jordan.Kernel: Hdr:Sound
rm.Jordan.Kernel: Hdr:Podule
rm.Jordan.Kernel: Hdr:VduExt
rm.Jordan.Kernel: Hdr:Buffer
rm.Jordan.Kernel: Hdr:Font
rm.Jordan.Kernel: Hdr:DevNos
rm.Jordan.Kernel: Hdr:Territory
rm.Jordan.Kernel: Hdr:Portable
rm.Jordan.Kernel: Hdr:MsgTrans
rm.Jordan.Kernel: Hdr:PaletteV
rm.Jordan.Kernel: Hdr:Wimp
rm.Jordan.Kernel: Hdr:ColourTran
rm.Jordan.Kernel: Hdr:Debug
rm.Jordan.Kernel: s.PMF.DEF
rm.Jordan.Kernel: s.Kernel
rm.Jordan.Kernel: TestSrc.Begin
rm.Jordan.Kernel: TestSrc.ExtIO
rm.Jordan.Kernel: TestSrc.ExtCmd
rm.Jordan.Kernel: TestSrc.Mem1IOMD
rm.Jordan.Kernel: TestSrc.Mem2
rm.Jordan.Kernel: TestSrc.Mem3
rm.Jordan.Kernel: TestSrc.Mem4
rm.Jordan.Kernel: TestSrc.Mem5
rm.Jordan.Kernel: TestSrc.Vidc
rm.Jordan.Kernel: TestSrc.Ioc
rm.Jordan.Kernel: TestSrc.Cmos
rm.Jordan.Kernel: TestSrc.Arm3
rm.Jordan.Kernel: s.NewIRQs
rm.Jordan.Kernel: s.Oscli
rm.Jordan.Kernel: s.SysComms
rm.Jordan.Kernel: s.MosDict
rm.Jordan.Kernel: s.TMOSHelp
rm.Jordan.Kernel: s.HeapMan
rm.Jordan.Kernel: s.ModHand
rm.Jordan.Kernel: s.Unsqueeze
rm.Jordan.Kernel: s.ArthurSWIs
rm.Jordan.Kernel: s.ChangeDyn
rm.Jordan.Kernel: s.Arthur2
rm.Jordan.Kernel: s.Utility
rm.Jordan.Kernel: s.MoreComms
rm.Jordan.Kernel: s.Convrsions
rm.Jordan.Kernel: s.MoreSWIs
rm.Jordan.Kernel: s.ExtraSWIs
rm.Jordan.Kernel: s.HeapSort
rm.Jordan.Kernel: s.Arthur3
rm.Jordan.Kernel: s.SWINaming
rm.Jordan.Kernel: s.TickEvents
rm.Jordan.Kernel: s.KbdResPC
rm.Jordan.Kernel: s.NewReset
rm.Jordan.Kernel: s.MsgCode
rm.Jordan.Kernel: s.Middle
rm.Jordan.Kernel: s.Super1
rm.Jordan.Kernel: s.ARM600
rm.Jordan.Kernel: s.MemInfo
rm.Jordan.Kernel: s.vdu.VduDriver
rm.Jordan.Kernel: s.vdu.VduDecl
rm.Jordan.Kernel: s.vdu.VduGrafDec
rm.Jordan.Kernel: s.vdu.VduModes
rm.Jordan.Kernel: s.vdu.VduSWIs
rm.Jordan.Kernel: s.vdu.VduPalette
rm.Jordan.Kernel: s.Vdu.VduPal20
rm.Jordan.Kernel: s.vdu.VduPlot
rm.Jordan.Kernel: s.vdu.VduGrafA
rm.Jordan.Kernel: s.vdu.VduGrafB
rm.Jordan.Kernel: s.vdu.VduGrafC
rm.Jordan.Kernel: s.vdu.VduGrafD
rm.Jordan.Kernel: s.vdu.VduGrafE
rm.Jordan.Kernel: s.vdu.VduGrafF
rm.Jordan.Kernel: s.vdu.VduGrafG
rm.Jordan.Kernel: s.vdu.VduGrafH
rm.Jordan.Kernel: s.vdu.VduGrafI
rm.Jordan.Kernel: s.vdu.VduGrafJ
rm.Jordan.Kernel: s.vdu.VduGrafK
rm.Jordan.Kernel: s.vdu.VduGrafL
rm.Jordan.Kernel: s.vdu.VduWrch
rm.Jordan.Kernel: s.vdu.Vdu23
rm.Jordan.Kernel: s.vdu.VduPointer
rm.Jordan.Kernel: s.vdu.Vdu5
rm.Jordan.Kernel: s.vdu.VduCurSoft
rm.Jordan.Kernel: s.vdu.VduTTX
rm.Jordan.Kernel: s.vdu.VduFontL1
rm.Jordan.Kernel: s.PMF.osinit
rm.Jordan.Kernel: s.PMF.oseven
rm.Jordan.Kernel: s.PMF.osbyte
rm.Jordan.Kernel: s.PMF.osword
rm.Jordan.Kernel: s.PMF.realtime
rm.Jordan.Kernel: s.PMF.convdate
rm.Jordan.Kernel: s.PMF.i2cutils
rm.Jordan.Kernel: s.PMF.oswrch
rm.Jordan.Kernel: s.PMF.buffer
rm.Jordan.Kernel: s.PMF.key
rm.Jordan.Kernel: s.PMF.mouse
rm.Morris.Kernel: Hdr:ListOpts
rm.Morris.Kernel: Hdr:Macros
rm.Morris.Kernel: Hdr:System
rm.Morris.Kernel: Hdr:SWIs
rm.Morris.Kernel: Hdr:CPU.Generic26
rm.Morris.Kernel: Hdr:IO.GenericIO
rm.Morris.Kernel: Hdr:RISCOS
rm.Morris.Kernel: Hdr:Machine.<Machine>
rm.Morris.Kernel: Hdr:ImageSize.<ImageSize>
rm.Morris.Kernel: Hdr:CPU.ARM600
rm.Morris.Kernel: Hdr:IO.IOMDL
rm.Morris.Kernel: Hdr:IO.IOMD
rm.Morris.Kernel: Hdr:MEMM.ARM600
rm.Morris.Kernel: Hdr:VIDC.VIDC20
rm.Morris.Kernel: Version
rm.Morris.Kernel: Hdr:CMOS
rm.Morris.Kernel: Hdr:Heap
rm.Morris.Kernel: Hdr:PublicWS
rm.Morris.Kernel: Hdr:KernelWS
rm.Morris.Kernel: Hdr:Services
rm.Morris.Kernel: Hdr:FSNumbers
rm.Morris.Kernel: Hdr:HighFSI
rm.Morris.Kernel: Hdr:NewErrors
rm.Morris.Kernel: Hdr:Proc
rm.Morris.Kernel: Hdr:Sprite
rm.Morris.Kernel: Hdr:KeyWS
rm.Morris.Kernel: Hdr:RS423
rm.Morris.Kernel: Hdr:ModHand
rm.Morris.Kernel: Hdr:Variables
rm.Morris.Kernel: Hdr:EnvNumbers
rm.Morris.Kernel: Hdr:UpCall
rm.Morris.Kernel: Hdr:Sound
rm.Morris.Kernel: Hdr:Pointer
rm.Morris.Kernel: Hdr:Podule
rm.Morris.Kernel: Hdr:VduExt
rm.Morris.Kernel: Hdr:Buffer
rm.Morris.Kernel: Hdr:Font
rm.Morris.Kernel: Hdr:DevNos
rm.Morris.Kernel: Hdr:Territory
rm.Morris.Kernel: Hdr:Portable
rm.Morris.Kernel: Hdr:MsgTrans
rm.Morris.Kernel: Hdr:PaletteV
rm.Morris.Kernel: Hdr:Wimp
rm.Morris.Kernel: Hdr:ColourTran
rm.Morris.Kernel: Hdr:Debug
rm.Morris.Kernel: s.PMF.DEF
rm.Morris.Kernel: s.Copro15ops
rm.Morris.Kernel: s.Kernel
rm.Morris.Kernel: TestSrc.Begin
rm.Morris.Kernel: s.Morris
rm.Morris.Kernel: TestSrc.ExtIO
rm.Morris.Kernel: TestSrc.ExtCmd
rm.Morris.Kernel: TestSrc.Mem1IOMD
rm.Morris.Kernel: TestSrc.Mem2
rm.Morris.Kernel: TestSrc.Mem3
rm.Morris.Kernel: TestSrc.Mem4
rm.Morris.Kernel: TestSrc.Mem5
rm.Morris.Kernel: TestSrc.Vidc
rm.Morris.Kernel: TestSrc.Ioc
rm.Morris.Kernel: TestSrc.Cmos
rm.Morris.Kernel: TestSrc.Arm3
rm.Morris.Kernel: s.NewIRQs
rm.Morris.Kernel: s.Oscli
rm.Morris.Kernel: s.SysComms
rm.Morris.Kernel: s.MosDict
rm.Morris.Kernel: s.TMOSHelp
rm.Morris.Kernel: s.HeapMan
rm.Morris.Kernel: s.ModHand
rm.Morris.Kernel: s.Unsqueeze
rm.Morris.Kernel: s.ArthurSWIs
rm.Morris.Kernel: s.ChangeDyn
rm.Morris.Kernel: s.Arthur2
rm.Morris.Kernel: s.Utility
rm.Morris.Kernel: s.MoreComms
rm.Morris.Kernel: s.Convrsions
rm.Morris.Kernel: s.MoreSWIs
rm.Morris.Kernel: s.ExtraSWIs
rm.Morris.Kernel: s.HeapSort
rm.Morris.Kernel: s.Arthur3
rm.Morris.Kernel: s.SWINaming
rm.Morris.Kernel: s.TickEvents
rm.Morris.Kernel: s.KbdResPC
rm.Morris.Kernel: s.NewReset
rm.Morris.Kernel: s.MsgCode
rm.Morris.Kernel: s.Middle
rm.Morris.Kernel: s.Super1
rm.Morris.Kernel: s.ARM600
rm.Morris.Kernel: s.MemInfo
rm.Morris.Kernel: s.vdu.VduDriver
rm.Morris.Kernel: s.vdu.VduDecl
rm.Morris.Kernel: s.vdu.VduGrafDec
rm.Morris.Kernel: s.vdu.VduModes
rm.Morris.Kernel: s.vdu.VduSWIs
rm.Morris.Kernel: s.vdu.VduPalette
rm.Morris.Kernel: s.Vdu.VduPal20
rm.Morris.Kernel: s.vdu.VduPlot
rm.Morris.Kernel: s.vdu.VduGrafA
rm.Morris.Kernel: s.vdu.VduGrafB
rm.Morris.Kernel: s.vdu.VduGrafC
rm.Morris.Kernel: s.vdu.VduGrafD
rm.Morris.Kernel: s.vdu.VduGrafE
rm.Morris.Kernel: s.vdu.VduGrafF
rm.Morris.Kernel: s.vdu.VduGrafG
rm.Morris.Kernel: s.vdu.VduGrafH
rm.Morris.Kernel: s.vdu.VduGrafI
rm.Morris.Kernel: s.vdu.VduGrafJ
rm.Morris.Kernel: s.vdu.VduGrafK
rm.Morris.Kernel: s.vdu.VduGrafL
rm.Morris.Kernel: s.vdu.VduWrch
rm.Morris.Kernel: s.vdu.Vdu23
rm.Morris.Kernel: s.vdu.VduPointer
rm.Morris.Kernel: s.vdu.Vdu5
rm.Morris.Kernel: s.vdu.VduCurSoft
rm.Morris.Kernel: s.vdu.VduTTX
rm.Morris.Kernel: s.vdu.VduFontL1
rm.Morris.Kernel: s.PMF.osinit
rm.Morris.Kernel: s.PMF.oseven
rm.Morris.Kernel: s.PMF.osbyte
rm.Morris.Kernel: s.PMF.osword
rm.Morris.Kernel: s.PMF.realtime
rm.Morris.Kernel: s.PMF.convdate
rm.Morris.Kernel: s.PMF.i2cutils
rm.Morris.Kernel: s.PMF.oswrch
rm.Morris.Kernel: s.PMF.buffer
rm.Morris.Kernel: s.PMF.key
rm.Morris.Kernel: s.PMF.mouse
rm.Morris.Kernel: s.AMBControl.AMB
rm.Morris.Kernel: s.AMBControl.Options
rm.Morris.Kernel: s.AMBControl.Workspace
rm.Morris.Kernel: s.AMBControl.main
rm.Morris.Kernel: s.AMBControl.allocate
rm.Morris.Kernel: s.AMBControl.deallocate
rm.Morris.Kernel: s.AMBControl.growshrink
rm.Morris.Kernel: s.AMBControl.mapslot
rm.Morris.Kernel: s.AMBControl.mapsome
rm.Morris.Kernel: s.AMBControl.readinfo
rm.Morris.Kernel: s.AMBControl.growp
rm.Morris.Kernel: s.AMBControl.shrinkp
rm.Morris.Kernel: s.AMBControl.service
rm.Morris.Kernel: s.AMBControl.Memory
rm.Morris.Kernel: s.AMBControl.memmap
