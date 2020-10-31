# Makefile for DOSFS
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name         Description
# ----       ----         -----------
# 25-May-94  AMcC         Created.
# 30-Aug-94  AMcC         Added rom_link rule

# For objasm 3.00 (comment out if using earlier assembler)
APCS_NONE = -apcs none

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
CMHG    = cmhg
CP      = copy
LD      = link
RM      = remove
WIPE    = -wipe

AFLAGS  = -depend !Depend -Stamp -quit
CFLAGS  = -c -depend !Depend -ffah -zps1 -zM ${INCLUDES} ${DFLAGS}
CPFLAGS = ~cfr~v
WFLAGS  = ~c~v

#
# Libraries
#
CLIB      = CLIB:o.stubs
RLIB      = RISCOSLIB:o.risc_oslib
RSTUBS    = RISCOSLIB:o.rstubs
ROMSTUBS  = RISCOSLIB:o.romstubs
ROMCSTUBS = RISCOSLIB:o.romcstubs
ABSSYM    = RISC_OSLib:o.AbsSym

#
# Include files
#
INCLUDES = -IC:

# DFLAGS should be NULL for any non-debugging release
DFLAGS    =
#DFLAGS    = -dTRACE -dTUBE=0

#
# Program specific options:
#
COMPONENT = DOSFS
TARGET    = aof.DOSFS
EXPORTS   = ${EXP_HDR}.DOSFS

OBJS =\
 o.DOSFS\
 o.DOSFSops\
 o.DOSFSctl\
 o.DOSnaming\
 o.FSerrors\
 o.TIMEconv\
 o.wcompare\
 o.debug\
 o.MsgTrans\
 o.Statics\
 o.StaticDefs\
 o.init

#
# Rule patterns
#
.c.o:;      ${CC} ${CFLAGS} -o $@ $<
.s.o:;      ${AS} ${AFLAGS} $< $@

#
# build a relocatable module:
#
all: rm.DOSFS

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
        ${WIPE} rm.* ${WFLAGS}
        ${WIPE} linked.* ${WFLAGS}
        ${WIPE} map.* ${WFLAGS}
        ${RM} ${TARGET}
        ${RM} h.DOSFShdr
        @echo ${COMPONENT}: cleaned

resources:
        ${MKDIR} ${RESDIR}.${COMPONENT}
        ${CP} Resources.${LOCALE}.Messages  ${RESDIR}.${COMPONENT}.Messages  ${CPFLAGS}
        @echo ${COMPONENT}: resource files copied

#
# ROM target (re-linked at ROM Image build time)
#
${TARGET}: cmhg.DOSFShdr ${OBJS} ${ROMCSTUBS}
        ${CMHG} cmhg.DOSFShdr o.DOSFShdr
        ${LD} -o $@ -aof o.DOSFShdr ${OBJS} ${ROMCSTUBS}

#
# Final link for the ROM Image (using given base address)
#
rom_link:
        ${LD} -o linked.${COMPONENT} -map -bin -base ${ADDRESS} ${TARGET} ${ABSSYM} > map.${COMPONENT}
        truncate map.${COMPONENT} linked.${COMPONENT}
        ${CP} linked.${COMPONENT} ${LINKDIR}.${COMPONENT} ${CPFLAGS}
        @echo ${COMPONENT}: rom_link complete

rm.DOSFS: cmhg.DOSFShdr ${OBJS} ${CLIB}
        ${CMHG} cmhg.DOSFShdr o.DOSFShdr
        ${LD} -o $@ -module o.DOSFShdr ${OBJS} ${CLIB}

${EXP_HDR}.DOSFS: hdr.DOSFS
        ${CP} hdr.DOSFS $@ ${CPFLAGS}

# Static dependencies:

# recreate h.DOSFShdr if necessary
o.DOSFS: h.DOSFShdr
h.DOSFShdr: cmhg.DOSFShdr
        ${CMHG} cmhg.DOSFShdr o.DOSFShdr h.DOSFShdr
        ${RM} o.DOSFShdr

# DOSFS C Support functions (defines C register definitions)
# Workaround required when using Objasm 3.00
o.DOSFSctl: s.DOSFSctl
        ${AS} ${AFLAGS} ${APCS_NONE} s.DOSFSctl $@

# Dynamic dependencies:
o.DOSFS:	c.DOSFS
o.DOSFS:	C:h.kernel
o.DOSFS:	C:h.swis
o.DOSFS:	C:h.ctype
o.DOSFS:	h.ASCII
o.DOSFS:	h.DOSFS
o.DOSFS:	h.DOSshape
o.DOSFS:	h.ASCII
o.DOSFS:	h.DOSFSctl
o.DOSFS:	h.debug
o.DOSFS:	h.DOSFShdr
o.DOSFS:	h.ADFSshape
o.DOSFS:	h.DOSshape
o.DOSFS:	h.FSerrors
o.DOSFS:	C:h.kernel
o.DOSFS:	h.DOSmapping
o.DOSFS:	h.DOSnaming
o.DOSFS:	h.DOSFSops
o.DOSFS:	h.MultiFS
o.DOSFS:	h.wcompare
o.DOSFS:	h.BOOTBLOCK
o.DOSFS:	h.DOSshape
o.DOSFS:	h.TIMEconv
o.DOSFS:	h.ASCII
o.DOSFS:	h.MsgTrans
o.DOSFS:	h.Statics
o.DOSFSops:	c.DOSFSops
o.DOSFSops:	C:h.kernel
o.DOSFSops:	C:h.swis
o.DOSFSops:	h.ASCII
o.DOSFSops:	h.debug
o.DOSFSops:	h.DOSFS
o.DOSFSops:	h.DOSshape
o.DOSFSops:	h.ASCII
o.DOSFSops:	h.DOSFSctl
o.DOSFSops:	h.DOSshape
o.DOSFSops:	h.FSerrors
o.DOSFSops:	C:h.kernel
o.DOSFSops:	h.wcompare
o.DOSFSops:	h.DOSnaming
o.DOSFSops:	h.DOSFSops
o.DOSFSops:	h.MultiFS
o.DOSFSops:	h.TIMEconv
o.DOSFSops:	h.ASCII
o.DOSFSops:	h.DOSmapping
o.DOSFSops:	h.ADFSshape
o.DOSFSops:	h.Statics
o.DOSFSctl: s.DOSFSctl
o.DOSFSctl: "Hdr:listopts"
o.DOSFSctl: "Hdr:macros"
o.DOSFSctl: "Hdr:system"
o.DOSFSctl: Hdr:SWIs
o.DOSFSctl: Hdr:CPU.Generic26
o.DOSFSctl: Hdr:IO.GenericIO
o.DOSFSctl: Hdr:RISCOS
o.DOSFSctl: "Hdr:modhand"
o.DOSFSctl: "Hdr:wimp"
o.DOSFSctl: "Hdr:hostfs"
o.DOSFSctl: "Hdr:NdrDebug"
o.DOSFSctl: "Hdr:DDVMacros"
o.DOSFSctl: "s.MFSmacros"
o.DOSnaming:	c.DOSnaming
o.DOSnaming:	C:h.kernel
o.DOSnaming:	h.ASCII
o.DOSnaming:	h.debug
o.DOSnaming:	h.ADFSshape
o.DOSnaming:	h.DOSshape
o.DOSnaming:	h.ASCII
o.DOSnaming:	h.TIMEconv
o.DOSnaming:	h.ASCII
o.DOSnaming:	h.DOSnaming
o.DOSnaming:	h.wcompare
o.DOSnaming:	h.FSerrors
o.DOSnaming:	C:h.kernel
o.DOSnaming:	h.DOSFS
o.DOSnaming:	h.DOSshape
o.FSerrors:	c.FSerrors
o.FSerrors:	C:h.kernel
o.FSerrors:	C:h.swis
o.FSerrors:	h.ASCII
o.FSerrors:	h.DOSFSctl
o.FSerrors:	h.debug
o.FSerrors:	h.FSerrors
o.FSerrors:	C:h.kernel
o.FSerrors:	h.MsgTrans
o.TIMEconv:	c.TIMEconv
o.TIMEconv:	C:h.kernel
o.TIMEconv:	C:h.swis
o.TIMEconv:	h.debug
o.TIMEconv:	h.TIMEconv
o.TIMEconv:	h.ASCII
o.TIMEconv:	h.FSerrors
o.TIMEconv:	C:h.kernel
o.TIMEconv:	h.DOSFSctl
o.TIMEconv:	h.DOSshape
o.TIMEconv:	h.ASCII
o.TIMEconv:	h.ADFSshape
o.wcompare:	c.wcompare
o.wcompare:	h.ASCII
o.wcompare:	h.wcompare
o.debug:	c.debug
o.debug:	C:h.kernel
o.debug:	C:h.swis
o.debug:	h.debug
o.MsgTrans:	c.MsgTrans
o.MsgTrans:	C:h.kernel
o.MsgTrans:	C:h.swis
o.MsgTrans:	h.MsgTrans
o.MsgTrans:	h.debug
o.Statics:	c.Statics
o.Statics:	h.DOSFS
o.Statics:	h.DOSshape
o.Statics:	h.ASCII
o.Statics:	h.DOSshape
o.Statics:	h.MultiFS
o.Statics:	h.Statics
o.StaticDefs: s.StaticDefs
o.init: s.init
