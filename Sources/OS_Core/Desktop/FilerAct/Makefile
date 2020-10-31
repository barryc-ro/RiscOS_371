# Makefile for Filer Action
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name         Description
# ----       ----         -----------
# 25-May-94  AMcC         Created.
# 30-Aug-94  AMcC         Added rom_link rule.

#
# Paths
#
EXP_HDR = <export$dir>

#
# Generic options:
#
MKDIR   = cdir
AS      = objasm
CC      = cc
CP      = copy
LD      = link
RM      = remove
WIPE    = -wipe

DFLAGS  =
AFLAGS  = -depend !Depend -Stamp -quit
CFLAGS  = -c -depend !Depend -ffah ${INCLUDES} ${DFLAGS}
CPFLAGS = ~cfr~v
WFLAGS  = ~c~v

#
# Libraries
#
CLIB     = CLIB:o.stubs
RLIB     = RISC_OSLIB:o.risc_oslib
RSTUBS   = RISC_OSLIB:o.rstubs
ROMSTUBS = RISC_OSLIB:o.romstubs
ABSSYM   = RISC_OSLib:o.AbsSym

#
# Include files
#
INCLUDES = -IC:

# Note: the wrapper contains filer action specific code!
WRAPPER   = RISCOSLIB:s.ModuleWrap

#
# Program specific options:
#
COMPONENT = FilerAct
TARGET    = aof.FilerAct
EXPORTS   = ${EXP_HDR}.FilerAct

OBJS =\
 o.actionwind\
 o.Initialise\
 o.Buttons\
 o.allerrs\
 o.memmanage\
 o.listfiles\
 o.Chains\
 o.debug

APP_OBJS =\
 oa.actionwind\
 oa.Initialise\
 oa.Buttons\
 o.allerrs\
 oa.memmanage\
 oa.listfiles\
 oa.Chains\
 oa.debug

#
# Rule patterns
#
.SUFFIXES: .oa

.c.o:;      ${CC} ${CFLAGS} -zM -o $@ $<
.c.oa:;     ${CC} ${CFLAGS} -o $@ $<
.s.o:;      ${AS} ${AFLAGS} $< $@

#
# Test/development rules:
#
all: rm.FilerAct
        @echo ${COMPONENT}: relocatable module built

app: app.FilerAct
        @echo ${COMPONENT}: application built

test: app.FilerAct
        Set FilerAct$Path <Obey$Dir>.Resources.UK.
        Set Alias$Filer_Action <Obey$Dir>.app.FilerAct %%*0

reset:
        Set FilerAct$Path Resources:$.Resources.FilerAct.
        UnSet Alias$Filer_Action

#
# RISC OS ROM build rules:
#
rom: ${TARGET}
        @echo ${COMPONENT}: rom module built

export: ${EXPORTS}
        @echo ${COMPONENT}: export complete

install_rom: ${TARGET}
        ${CP} ${TARGET} ${INSTDIR}.${COMPONENT} ${CPFLAGS}
        @echo ${COMPONENT}: rom module installed

clean:
        ${WIPE} o.* ${WFLAGS}
        ${WIPE} oa.* ${WFLAGS}
        ${WIPE} app.* ${WFLAGS}
        ${WIPE} rm.* ${WFLAGS}
        ${WIPE} linked.* ${WFLAGS}
        ${WIPE} map.* ${WFLAGS}
        ${RM} ${TARGET}
        ${RM} s.ModuleWrap
        @echo ${COMPONENT}: cleaned

resources:
        ${MKDIR} ${RESDIR}.${COMPONENT}
        ${CP} Resources.${LOCALE}.Messages  ${RESDIR}.${COMPONENT}.Messages  ${CPFLAGS}
        ${CP} Resources.${LOCALE}.Templates ${RESDIR}.${COMPONENT}.Templates ${CPFLAGS}
        @echo ${COMPONENT}: resource files copied

${EXP_HDR}.FilerAct: hdr.FilerAct
        ${CP} hdr.FilerAct $@ ${CPFLAGS}
#
# ROM target (re-linked at ROM Image build time)
#
${TARGET}: ${OBJS} o.ModuleWrap ${ROMSTUBS}
        ${LD} -o $@ -aof ${OBJS} o.ModuleWrap ${ROMSTUBS}

#
# Final link for the ROM Image (using given base address)
#
rom_link:
        ${LD} -o linked.${COMPONENT} -map -bin -base ${ADDRESS} ${TARGET} ${ABSSYM} > map.${COMPONENT}
        truncate map.${COMPONENT} linked.${COMPONENT}
        ${CP} linked.${COMPONENT} ${LINKDIR}.${COMPONENT} ${CPFLAGS}
        @echo ${COMPONENT}: rom_link complete

rm.FilerAct: ${OBJS} o.ModuleWrap ${RSTUBS}
        ${LD} -o $@ -module ${OBJS} o.ModuleWrap ${RSTUBS}

# Application
#
app.FilerAct: ${APP_OBJS} ${CLIB} ${RLIB}
        ${LD} -o $@ ${APP_OBJS} ${CLIB} ${RLIB}

o.ModuleWrap: s.ModuleWrap
        ${AS} ${AFLAGS} s.ModuleWrap $@

s.ModuleWrap: ${WRAPPER}
        ${CP} ${WRAPPER} $@ ${CPFLAGS}

# Dynamic dependencies:
oa.actionwind:	c.actionwind
oa.actionwind:	C:h.swis
oa.actionwind:	C:h.kernel
oa.actionwind:	C:h.os
oa.actionwind:	C:h.wimp
oa.actionwind:	C:h.sprite
oa.actionwind:	C:h.wimpt
oa.actionwind:	C:h.werr
oa.actionwind:	C:h.win
oa.actionwind:	C:h.res
oa.actionwind:	C:h.resspr
oa.actionwind:	C:h.template
oa.actionwind:	C:h.msgs
oa.actionwind:	C:h.event
oa.actionwind:	C:h.menu
oa.actionwind:	C:h.dbox
oa.actionwind:	C:h.dboxquery
oa.actionwind:	C:h.flex
oa.actionwind:	C:h.heap
oa.actionwind:	C:h.bbc
oa.actionwind:	h.allerrs
oa.actionwind:	h.malloc+
oa.actionwind:	h.listfiles
oa.actionwind:	h.memmanage
oa.actionwind:	h.actionwind
oa.actionwind:	h.Initialise
oa.actionwind:	h.Buttons
oa.actionwind:	h.debug
oa.Initialise:	c.Initialise
oa.Initialise:	C:h.os
oa.Initialise:	C:h.kernel
oa.Initialise:	C:h.wimp
oa.Initialise:	C:h.sprite
oa.Initialise:	C:h.wimpt
oa.Initialise:	C:h.win
oa.Initialise:	C:h.event
oa.Initialise:	C:h.menu
oa.Initialise:	C:h.res
oa.Initialise:	C:h.template
oa.Initialise:	C:h.dbox
oa.Initialise:	C:h.dboxquery
oa.Initialise:	C:h.msgs
oa.Initialise:	C:h.menu
oa.Initialise:	h.allerrs
oa.Initialise:	C:h.string
oa.Initialise:	h.malloc+
oa.Initialise:	h.listfiles
oa.Initialise:	h.memmanage
oa.Initialise:	h.actionwind
oa.Initialise:	h.Initialise
oa.Initialise:	h.Buttons
oa.Initialise:	h.debug
oa.Buttons:	c.Buttons
oa.Buttons:	C:h.os
oa.Buttons:	C:h.kernel
oa.Buttons:	C:h.wimp
oa.Buttons:	C:h.sprite
oa.Buttons:	C:h.wimpt
oa.Buttons:	C:h.event
oa.Buttons:	C:h.menu
oa.Buttons:	C:h.dbox
oa.Buttons:	C:h.msgs
oa.Buttons:	h.malloc+
oa.Buttons:	h.listfiles
oa.Buttons:	h.memmanage
oa.Buttons:	h.allerrs
oa.Buttons:	h.actionwind
oa.Buttons:	h.Buttons
oa.Buttons:	h.debug
oa.memmanage:	c.memmanage
oa.memmanage:	C:h.kernel
oa.memmanage:	C:h.os
oa.memmanage:	C:h.wimp
oa.memmanage:	C:h.sprite
oa.memmanage:	h.chains
oa.memmanage:	h.allerrs
oa.memmanage:	C:h.msgs
oa.memmanage:	h.malloc+
oa.memmanage:	h.memmanage
oa.memmanage:	h.debug
oa.listfiles:	c.listfiles
oa.listfiles:	C:h.os
oa.listfiles:	C:h.kernel
oa.listfiles:	h.malloc+
oa.listfiles:	h.listfiles
oa.listfiles:	h.allerrs
oa.listfiles:	C:h.msgs
oa.listfiles:	h.debug
oa.Chains:	c.Chains
oa.Chains:	h.debug
oa.Chains:	h.chains
oa.debug:	c.debug
oa.debug:	C:h.os
oa.debug:	C:h.kernel
oa.debug:	h.debug
o.actionwind:	c.actionwind
o.actionwind:	C:h.swis
o.actionwind:	C:h.kernel
o.actionwind:	C:h.os
o.actionwind:	C:h.wimp
o.actionwind:	C:h.sprite
o.actionwind:	C:h.wimpt
o.actionwind:	C:h.werr
o.actionwind:	C:h.win
o.actionwind:	C:h.res
o.actionwind:	C:h.resspr
o.actionwind:	C:h.template
o.actionwind:	C:h.msgs
o.actionwind:	C:h.event
o.actionwind:	C:h.menu
o.actionwind:	C:h.dbox
o.actionwind:	C:h.dboxquery
o.actionwind:	C:h.flex
o.actionwind:	C:h.heap
o.actionwind:	C:h.bbc
o.actionwind:	h.allerrs
o.actionwind:	h.malloc+
o.actionwind:	h.listfiles
o.actionwind:	h.memmanage
o.actionwind:	h.actionwind
o.actionwind:	h.Initialise
o.actionwind:	h.Buttons
o.actionwind:	h.debug
o.Initialise:	c.Initialise
o.Initialise:	C:h.os
o.Initialise:	C:h.kernel
o.Initialise:	C:h.wimp
o.Initialise:	C:h.sprite
o.Initialise:	C:h.wimpt
o.Initialise:	C:h.win
o.Initialise:	C:h.event
o.Initialise:	C:h.menu
o.Initialise:	C:h.res
o.Initialise:	C:h.template
o.Initialise:	C:h.dbox
o.Initialise:	C:h.dboxquery
o.Initialise:	C:h.msgs
o.Initialise:	C:h.menu
o.Initialise:	h.allerrs
o.Initialise:	C:h.string
o.Initialise:	h.malloc+
o.Initialise:	h.listfiles
o.Initialise:	h.memmanage
o.Initialise:	h.actionwind
o.Initialise:	h.Initialise
o.Initialise:	h.Buttons
o.Initialise:	h.debug
o.Buttons:	c.Buttons
o.Buttons:	C:h.os
o.Buttons:	C:h.kernel
o.Buttons:	C:h.wimp
o.Buttons:	C:h.sprite
o.Buttons:	C:h.wimpt
o.Buttons:	C:h.event
o.Buttons:	C:h.menu
o.Buttons:	C:h.dbox
o.Buttons:	C:h.msgs
o.Buttons:	h.malloc+
o.Buttons:	h.listfiles
o.Buttons:	h.memmanage
o.Buttons:	h.allerrs
o.Buttons:	h.actionwind
o.Buttons:	h.Buttons
o.Buttons:	h.debug
o.allerrs: s.allerrs
o.memmanage:	c.memmanage
o.memmanage:	C:h.kernel
o.memmanage:	C:h.os
o.memmanage:	C:h.wimp
o.memmanage:	C:h.sprite
o.memmanage:	h.chains
o.memmanage:	h.allerrs
o.memmanage:	C:h.msgs
o.memmanage:	h.malloc+
o.memmanage:	h.memmanage
o.memmanage:	h.debug
o.listfiles:	c.listfiles
o.listfiles:	C:h.os
o.listfiles:	C:h.kernel
o.listfiles:	h.malloc+
o.listfiles:	h.listfiles
o.listfiles:	h.allerrs
o.listfiles:	C:h.msgs
o.listfiles:	h.debug
o.Chains:	c.Chains
o.Chains:	h.debug
o.Chains:	h.chains
o.debug:	c.debug
o.debug:	C:h.os
o.debug:	C:h.kernel
o.debug:	h.debug
o.ModuleWrap: s.ModuleWrap
o.ModuleWrap: s.AppName
o.ModuleWrap: Hdr:ListOpts
o.ModuleWrap: Hdr:Macros
o.ModuleWrap: Hdr:System
o.ModuleWrap: Hdr:SWIs
o.ModuleWrap: Hdr:CPU.Generic26
o.ModuleWrap: Hdr:IO.GenericIO
o.ModuleWrap: Hdr:RISCOS
o.ModuleWrap: Hdr:ModHand
o.ModuleWrap: Hdr:EnvNumbers
o.ModuleWrap: Hdr:Proc
o.ModuleWrap: Hdr:FSNumbers
o.ModuleWrap: Hdr:NewErrors
o.ModuleWrap: Hdr:Services
o.ModuleWrap: Hdr:ResourceFS
o.ModuleWrap: Hdr:MsgTrans
o.ModuleWrap: Hdr:Variables
o.ModuleWrap: Hdr:UpCall
