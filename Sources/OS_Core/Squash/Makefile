# Makefile for Squash module
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
AS      = objasm
CC      = cc
CP      = copy
LD      = link
RM      = remove
WIPE    = -wipe
CCFLAGS = -c -depend !Depend -IC: -faf -zps1 -zM
ASFLAGS = -depend !Depend -Stamp -quit
CPFLAGS = ~cfr~v
WFLAGS  = ~c~v

#
# Program specific options:
#
COMPONENT = Squash
TARGET    = rm.Squash
EXPORTS   = ${EXP_HDR}.${COMPONENT}

OBJS =\
 compress.o\
 comp_ass.o\
 cssr.o\
 debug.o\
 mr_module.o\
 statics.o\
 trial.o\
 zcat_ass.o\
 zssr.o

#
# Rule patterns
#
.c.o:;      ${CC} ${CCFLAGS} -o $@ $<
.s.o:;      ${AS} ${ASFLAGS} $< $@

#
# Generic rules:
#
all:
  @echo testing

rom: ${TARGET}
        @echo ${COMPONENT}: rom module built

export: ${EXPORTS}
        @echo ${COMPONENT}: export complete

install_rom: ${TARGET}
        ${CP} ${TARGET} ${INSTDIR}.${COMPONENT} ${CPFLAGS}
        @echo ${COMPONENT}: rom module installed

clean:
        ${WIPE} o.* ${WFLAGS}
        ${RM} ${TARGET}
        @echo ${COMPONENT}: cleaned

resources:
        ${MKDIR} ${RESDIR}.${COMPONENT}
        ${CP} Resources.${LOCALE}.Messages  ${RESDIR}.${COMPONENT}.Messages  ${CPFLAGS}
        @echo ${COMPONENT}: resource files copied

${TARGET}: ${OBJS}
        ${LD} -o $@ -bin -base 0 ${OBJS}
        SetType $@ module

zcat_ass.o: zcat_ass12.s
        ${AS} ${ASFLAGS} s.zcat_ass12 $@

${EXP_HDR}.${COMPONENT}: hdr.${COMPONENT}
        ${CP} hdr.${COMPONENT} $@ ${CPFLAGS}

# Dynamic dependencies:
o.compress:	c.compress
o.compress:	C:h.kernel
o.compress:	h.debug
o.compress:	h.cssr
o.compress:	h.defs
o.compress:	h.zssr
o.compress:	h.defs
o.comp_ass: s.comp_ass
o.comp_ass: hdr:ListOpts
o.comp_ass: hdr:Macros
o.comp_ass: hdr:System
o.comp_ass: Hdr:SWIs
o.comp_ass: Hdr:CPU.Generic26
o.comp_ass: Hdr:IO.GenericIO
o.comp_ass: Hdr:RISCOS
o.comp_ass: hdr.debug
o.cssr:	c.cssr
o.cssr:	C:h.kernel
o.cssr:	h.debug
o.cssr:	h.cssr
o.cssr:	h.defs
o.debug: s.debug
o.debug: Hdr:ListOpts
o.debug: Hdr:Macros
o.debug: Hdr:System
o.debug: Hdr:SWIs
o.debug: Hdr:CPU.Generic26
o.debug: Hdr:IO.GenericIO
o.debug: Hdr:RISCOS
o.debug: Hdr:ModHand
o.debug: Hdr:HostFS
o.mr_module: s.mr_module
o.mr_module: Hdr:ListOpts
o.mr_module: Hdr:Macros
o.mr_module: Hdr:System
o.mr_module: Hdr:SWIs
o.mr_module: Hdr:CPU.Generic26
o.mr_module: Hdr:IO.GenericIO
o.mr_module: Hdr:RISCOS
o.mr_module: Hdr:ModHand
o.mr_module: Hdr:MsgTrans
o.mr_module: Hdr.MagicOff
o.mr_module: Hdr.StaticDecl
o.mr_module: Hdr.statics
o.mr_module: s.Version
o.mr_module: Hdr.debug
o.statics: s.statics
o.statics: Hdr:ListOpts
o.statics: Hdr:Macros
o.statics: Hdr:System
o.statics: Hdr:SWIs
o.statics: Hdr:CPU.Generic26
o.statics: Hdr:IO.GenericIO
o.statics: Hdr:RISCOS
o.statics: Hdr.MagicOff
o.statics: Hdr.statics
o.trial:	c.trial
o.trial:	C:h.kernel
o.trial:	h.debug
o.trial:	h.mr_module
o.zcat_ass: s.zcat_ass12
o.zcat_ass: s.zcat_ass
o.zcat_ass: hdr:ListOpts
o.zcat_ass: hdr:Macros
o.zcat_ass: hdr:System
o.zcat_ass: Hdr:SWIs
o.zcat_ass: Hdr:CPU.Generic26
o.zcat_ass: Hdr:IO.GenericIO
o.zcat_ass: Hdr:RISCOS
o.zssr:	c.zssr
o.zssr:	C:h.kernel
o.zssr:	h.debug
o.zssr:	h.zssr
o.zssr:	h.defs
