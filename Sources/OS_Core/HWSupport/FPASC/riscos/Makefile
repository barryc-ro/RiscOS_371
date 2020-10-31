# Makefile for Floating Point Accelerator Support Code (FPASC)
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name     Description
# ----       ----     -----------
# 25-May-94  AMcC     Created.
# 17-Aug-94  AMcC     Removed Specific machine names.
#                     If building for old series machines, comment out A600
#                     target and uncomment ARM2/3 target.

#
# Paths
#
EXP_HDR = <export$dir>

#
# Generic options:
#
MKDIR   = cdir
AS      = armasm
CP      = copy
LD      = link
RM      = remove
WIPE    = -wipe
CCFLAGS = -c -depend !Depend -IC:
ASFLAGS = -depend !Depend -apcs 3/26bit
CPFLAGS = ~cfr~v
WFLAGS  = ~c~v

#
# Program specific options:
#
COMPONENT = FPEmulator
TARGET    = rm.${MACHINE}.FPEmulator
EXPORTS   = ${EXP_HDR}.FPEmulator

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
        ${WIPE} o.* ${WFLAGS}
        @echo ${COMPONENT}: cleaned

resources:
        ${MKDIR} ${RESDIR}.${COMPONENT}
        ${CP} Resources.${LOCALE}.Messages  ${RESDIR}.${COMPONENT}.Messages  ${CPFLAGS}
        @echo ${COMPONENT}: resource files copied

# ARM600
#
${TARGET}: o.fpe
        ${MKDIR} rm.${MACHINE}
        ${LD} -bin -o $@ o.fpe
        settype $@ Module

o.fpe: s.fpemedusa
        ${AS} -I Hdr:t.^ ${ASFLAGS} s.fpemedusa $@

# ARM2/3
#
#${TARGET}: o.fpe400
#        ${MKDIR} rm.${MACHINE}
#        ${LD} -bin -o $@ o.fpe400
#        settype $@ Module
#
#o.fpe: s.fpe400
#        ${AS} -I Hdr:t.^ ${ASFLAGS} s.fpe400 $@

${EXP_HDR}.FPEmulator: hdr.FPEmulator
        ${CP} hdr.FPEmulator $@ ${CPFLAGS}

# Dynamic dependencies:
o.fpe: s.fpemedusa
o.fpe: ^.coresrc.s.main
o.fpe: ^.coresrc.^.coresrc.s.defaults
o.fpe: ^.coresrc.^.vensrc.riscos.options
o.fpe: Hdr:t.^.ListOpts
o.fpe: Hdr:t.^.Macros
o.fpe: Hdr:t.^.Proc
o.fpe: Hdr:t.^.Services
o.fpe: Hdr:t.^.ModHand
o.fpe: ^.coresrc.^.vensrc.riscos.FPEMacros
o.fpe: ^.coresrc.^.vensrc.riscos.Version
o.fpe: Hdr:t.^.SWIs
o.fpe: Hdr:t.^.RISCOS
o.fpe: ^.coresrc.^.coresrc.s.regnames
o.fpe: ^.coresrc.^.coresrc.s.armdefs
o.fpe: ^.coresrc.^.coresrc.s.fpadefs
o.fpe: ^.coresrc.^.coresrc.s.wsdefs
o.fpe: ^.coresrc.^.coresrc.^.vensrc.riscos.ctxtws
o.fpe: ^.coresrc.^.coresrc.^.vensrc.riscos.globalws
o.fpe: ^.coresrc.^.vensrc.riscos.start
o.fpe: ^.coresrc.^.coresrc.s.toplevel
o.fpe: ^.coresrc.^.coresrc.^.coresrc.s.macros
o.fpe: ^.coresrc.^.coresrc.^.coresrc.s.fpaundef
o.fpe: ^.coresrc.^.coresrc.^.coresrc.s.fpeundef
o.fpe: ^.coresrc.^.coresrc.^.coresrc.s.ldst
o.fpe: ^.coresrc.^.coresrc.^.coresrc.s.rounding
o.fpe: ^.coresrc.^.coresrc.^.coresrc.s.nans
o.fpe: ^.coresrc.^.coresrc.^.coresrc.s.arith
o.fpe: ^.coresrc.^.coresrc.^.coresrc.s.transhw
o.fpe: ^.coresrc.^.coresrc.^.coresrc.s.transsw
o.fpe: ^.coresrc.^.coresrc.^.coresrc.s.interf
o.fpe: ^.coresrc.^.vensrc.riscos.end
