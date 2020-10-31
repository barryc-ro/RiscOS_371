# Makefile for C and RISC_OS Headers, Libraries and Stubs
#
#---------------------------------------------------------------------------------------------
# Library             Exported as             Macro        Runs in   Type          Use
#---------------------------------------------------------------------------------------------
# lib.stubs           CLib:o.stubs            ${CLIB}       RAM      C_Stubs
# lib.risc_oslib      RISC_OSLib:o.risc_oslib ${RLIB}
# lib.rstubs          RISC_OSLib:o.rstubs     ${RSTUBS}     RAM      RISC_OSStubs
# lib.romcstubs       RISC_OSLib:o.romcstubs  ${ROMCSTUBS}  ROM      C_Stubs       Module_Only
# lib.romstubs        RISC_OSLib:o.romstubs   ${ROMSTUBS}   ROM      RISC_OSStubs  Module_Only
# lib.romastubs                                             ROM      RISC_OSStubs  Apps_Only
# lib.ansilib
# lib.arthurlib
# lib.clib
# lib.riscoslibm
#---------------------------------------------------------------------------------------------
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name         Description
# ----       ----         -----------
# 20-Jul-94  AMcC         Created.
# 28-Sep-94  AMcC         Now exports some internal headers for Edit
#

#
# Paths
#
EXP_HDR = <export$dir>
LIBDIR  = <Lib$Dir>

#
# Generic options:
#
AS      = aasm
CC      = cc
CMHG    = cmhg
CP      = copy
LD      = link
LIBFILE = libfile
MKDIR   = cdir
OBJASM  = objasm
RM      = remove
WIPE    = -wipe

AFLAGS  = -depend !Depend -Stamp -quit
CFLAGS  = -c -depend !Depend ${INCLUDES} -DDDE -fK
CPFLAGS = ~cfr~v
WFLAGS  = ~c~r~v

# create a new library, add symbol table
LIBFLAGS = -c -o

#
# Include files
#
INCLUDES = 

STK_EXTN =

DFLAGS =\
 -DFIELDNUM\
 -DBIG_WINDOWS\
 -DSETOPTIONS\
 -DALLOW_OLD_PATTERNS\
 -DSET_MISC_OPTIONS

# Shared C Library flags
CSFLAGS =\
 -I@,^.clib\
 -DSHARED_C_LIBRARY\
 -DUROM

VSFLAGS =\
 -DLIB_SHARED="\"Shared \""\
 -DLIB_APCS="\"R\""

VLFLAGS =\
 -DLIB_SHARED="\"\""\
 -DLIB_APCS="\"R\""

VPATH = @ kernel clib rlib

.SUFFIXES:  .o .o_rl .m_o_rl .rm_o .rm_o_rl
#
# Rule patterns
#
.c.o:;        ${CC} ${CFLAGS} -fah -o $@ $<
.c.o_rl:;     ${CC} ${CFLAGS} ${DFLAGS} -o $@ $<
.c.m_o_rl:;   ${CC} ${CFLAGS} -ffah ${DFLAGS} -zM -o $@ $<
.c.rm_o:;     ${CC} ${CFLAGS} -ffah ${DFLAGS} -zm1 ${CSFLAGS} -o $@ $<
.c.rm_o_rl:;  ${CC} ${CFLAGS} -ffah ${DFLAGS} -zm1 ${CSFLAGS} ${STK_EXTN} -o $@ $<
.s.o:;        ${OBJASM} ${AFLAGS} $< $@
.s.o_rl:;     ${OBJASM} ${AFLAGS} $< $@
.s.m_o_rl:;   ${OBJASM} ${AFLAGS} $< $@
.s.rm_o:;     ${OBJASM} ${AFLAGS} $< $@
.s.rm_o_rl:;  ${OBJASM} ${AFLAGS} $< $@

#
# Libraries
#
CLIB      = CLIB:o.stubs
RLIB      = RISCOSLIB:o.risc_oslib
RSTUBS    = RISCOSLIB:o.rstubs
ROMSTUBS  = RISCOSLIB:o.romstubs
ROMCSTUBS = RISCOSLIB:o.romcstubs
ABSSYM    = RISC_OSLib:o.abssym
C_ABSSYM  = RISC_OSLib:o.c_abssym
A_ABSSYM  = RISC_OSLib:o.a_abssym

#
# Program specific options:
#
HEADERS =\
 CLIB:h.assert \
 CLIB:h.ctype \
 CLIB:h.errno \
 CLIB:h.float \
 CLIB:h.kernel \
 CLIB:h.limits \
 CLIB:h.locale \
 CLIB:h.math \
 CLIB:h.setjmp \
 CLIB:h.signal \
 CLIB:h.stdarg \
 CLIB:h.stddef \
 CLIB:h.stdio \
 CLIB:h.stdlib \
 CLIB:h.string \
 CLIB:h.swis \
 CLIB:h.time \
 CLIB:h.varargs \
 RISC_OSLib:h.akbd \
 RISC_OSLib:h.alarm \
 RISC_OSLib:h.baricon \
 RISC_OSLib:h.bbc \
 RISC_OSLib:h.colourmenu \
 RISC_OSLib:h.colourpick \
 RISC_OSLib:h.colourtran \
 RISC_OSLib:h.coords \
 RISC_OSLib:h.ctl \
 RISC_OSLib:h.dbox \
 RISC_OSLib:h.dboxfile \
 RISC_OSLib:h.dboxquery \
 RISC_OSLib:h.dboxtcol \
 RISC_OSLib:h.dragasprit \
 RISC_OSLib:h.drawfdiag \
 RISC_OSLib:h.drawferror \
 RISC_OSLib:h.drawfobj \
 RISC_OSLib:h.drawftypes \
 RISC_OSLib:h.drawmod \
 RISC_OSLib:h.event \
 RISC_OSLib:h.fileicon \
 RISC_OSLib:h.flex \
 RISC_OSLib:h.font \
 RISC_OSLib:h.heap \
 RISC_OSLib:h.help \
 RISC_OSLib:h.magnify \
 RISC_OSLib:h.menu \
 RISC_OSLib:h.msgs \
 RISC_OSLib:h.msgtrans \
 RISC_OSLib:h.os \
 RISC_OSLib:h.pointer \
 RISC_OSLib:h.print \
 RISC_OSLib:h.res \
 RISC_OSLib:h.resspr \
 RISC_OSLib:h.saveas \
 RISC_OSLib:h.sprite \
 RISC_OSLib:h.template \
 RISC_OSLib:h.trace \
 RISC_OSLib:h.txt \
 RISC_OSLib:h.txtedit \
 RISC_OSLib:h.txtopt \
 RISC_OSLib:h.txtscrap \
 RISC_OSLib:h.txtwin \
 RISC_OSLib:h.typdat \
 RISC_OSLib:h.visdelay \
 RISC_OSLib:h.werr \
 RISC_OSLib:h.wimp \
 RISC_OSLib:h.wimpt \
 RISC_OSLib:h.win \
 RISC_OSLib:h.xferrecv \
 RISC_OSLib:h.xfersend

# Unfortunately these need to be exported to build Edit
INTERNAL_HEADERS =\
 RISC_OSLib:h.EditIntern.message \
 RISC_OSLib:h.EditIntern.txtar \
 RISC_OSLib:h.EditIntern.txtfile \
 RISC_OSLib:h.EditIntern.txtoptmenu

LIBRARIES =\
 Clib:o.ansilib \
 CLib:o.stubs \
 RISC_OSLib:o.risc_oslib \
 RISC_OSLib:o.riscoslibm \
 RISC_OSLib:o.rstubs \
 RISC_OSLib:o.romstubs \
 RISC_OSLib:o.romastubs \
 RISC_OSLib:o.romcstubs

EXPORTED_LIBS =\
 Clib:o.ansilib \
 CLib:o.stubs \
 RISC_OSLib:o.risc_oslib \
 RISC_OSLib:o.rstubs \
 RISC_OSLib:o.romstubs \
 RISC_OSLib:o.romcstubs

MODWRAP   = RISC_OSLib:s.modulewrap

COMPONENT = RISC_OSLib
TARGET    = aof.RISC_OSLib
EXPORTS   = ${MODWRAP} \
            ${EXPORTED_LIBS} \
            ${HEADERS} \
            ${INTERNAL_HEADERS}

#
# Objects for Clib:o.ansilib
#
ANSI_OBJS =\
 o.alloc o.armprof o.armsys o.clib o.ctype o.error o.fpprintf \
 o.kernel o.locale o.math o.memcpy o.overmgr o.printf o.scanf \
 o.signal o.sort o.stdio o.stdlib o.string o.swiv o.time

RM_OBJS =\
 rm_o.k_modbody \
 rm_o.cl_modbody \
 rm_o.alloc \
 rm_o.armsys \
 rm_o.bsearch_a \
 rm_o.ctype \
 rm_o.error \
 rm_o.fpprintf \
 rm_o.locale \
 rm_o.math \
 rm_o.memcpy \
 rm_o.printf \
 rm_o.scanf \
 rm_o.signal \
 rm_o.sort \
 rm_o.stdio \
 rm_o.stdlib \
 rm_o.string \
 rm_o.time \
 rm_o.swiv \
 rm_o.cl_spare

#
# Objects for lib.clib (relocatable module)
#
CLIB_MOD_OBJS =\
 rm_o.cl_rmhdr \
 rm_o.initmodule \
 ${RM_OBJS}

#
# Objects for ROM shared library
#
ROM_OBJS =\
 rm_o.cl_rmhdr \
 rm_o_rl.initmodule \
 ${RM_OBJS} \
 rm_o_rl.rl_modbody \
 rm_o_rl.akbd \
 rm_o_rl.alarm \
 rm_o_rl.baricon \
 rm_o_rl.bastxt \
 rm_o_rl.bbc \
 rm_o_rl.colourmenu \
 rm_o_rl.colourtran \
 rm_o_rl.dbox \
 rm_o_rl.dboxfile \
 rm_o_rl.dboxquery \
 rm_o_rl.dboxtcol \
 rm_o_rl.dragasprit \
 rm_o_rl.drawmod \
 rm_o_rl.event \
 rm_o_rl.fileicon \
 rm_o_rl.flex \
 rm_o_rl.font \
 rm_o_rl.heap \
 rm_o_rl.magnify \
 rm_o_rl.menu \
 rm_o_rl.msgs \
 rm_o_rl.os \
 rm_o_rl.pointer \
 rm_o_rl.poll \
 rm_o_rl.res \
 rm_o_rl.resspr \
 rm_o_rl.saveas \
 rm_o_rl.sprite \
 rm_o_rl.swi \
 rm_o_rl.template \
 rm_o_rl.txt \
 rm_o_rl.txt1 \
 rm_o_rl.txt3 \
 rm_o_rl.txtar \
 rm_o_rl.txtedit \
 rm_o_rl.txtfile \
 rm_o_rl.txtfind \
 rm_o_rl.txtmisc \
 rm_o_rl.txtoptmenu \
 rm_o_rl.txtscrap \
 rm_o_rl.txtundo \
 rm_o_rl.txtwin \
 rm_o_rl.visdelay \
 rm_o_rl.werr \
 rm_o_rl.wimp \
 rm_o_rl.wimpt \
 rm_o_rl.win \
 rm_o_rl.xferrecv \
 rm_o_rl.xfersend \
 rm_o_rl.help \
 rm_o_rl.print \
 rm_o_rl.txtopt \
 rm_o_rl.txtregexp \
 rm_o_rl.rl_spare

#
# Objects for RISCOSLIB:o.risc_oslib
#
RLIB_OBJS =\
 o_rl.akbd o_rl.alarm o_rl.baricon o_rl.bastxt o_rl.bbc o_rl.colourmenu \
 o_rl.colourtran o_rl.coords o_rl.ctl o_rl.dbox o_rl.dboxfile o_rl.dboxquery \
 o_rl.dboxtcol o_rl.dragasprit o_rl.drawcheck o_rl.drawfdiag o_rl.drawfiles \
 o_rl.drawfobj o_rl.drawmod o_rl.drawtextc o_rl.event o_rl.fileicon o_rl.flex \
 o_rl.font o_rl.heap o_rl.help o_rl.magnify o_rl.menu o_rl.msgs o_rl.os \
 o_rl.pointer o_rl.poll o_rl.print o_rl.res o_rl.resspr o_rl.saveas o_rl.sprite \
 o_rl.swi o_rl.template o_rl.trace o_rl.txt o_rl.txt1 o_rl.txt3 o_rl.txtar \
 o_rl.txtedit o_rl.txtfile o_rl.txtfind o_rl.txtmisc o_rl.txtopt o_rl.txtoptmenu \
 o_rl.txtregexp o_rl.txtscrap o_rl.txtundo o_rl.txtwin o_rl.visdelay \
 o_rl.werr o_rl.wimp o_rl.wimpt o_rl.win o_rl.xferrecv o_rl.xfersend

#
# Objects for RISCOSLIB:o.riscoslibm
#
RLIB_MOD_OBJS =\
 m_o_rl.akbd m_o_rl.alarm m_o_rl.baricon m_o_rl.bastxt m_o_rl.bbc \
 m_o_rl.colourmenu m_o_rl.colourtran m_o_rl.coords m_o_rl.ctl m_o_rl.dbox \
 m_o_rl.dboxfile m_o_rl.dboxquery  m_o_rl.dboxtcol m_o_rl.dragasprit \
 m_o_rl.drawcheck m_o_rl.drawfdiag m_o_rl.drawfiles m_o_rl.drawfobj m_o_rl.drawmod \
 m_o_rl.drawtextc m_o_rl.event m_o_rl.fileicon m_o_rl.flex m_o_rl.font \
 m_o_rl.heap m_o_rl.help m_o_rl.magnify m_o_rl.menu m_o_rl.msgs m_o_rl.os \
 m_o_rl.pointer m_o_rl.poll m_o_rl.print m_o_rl.res m_o_rl.resspr m_o_rl.saveas \
 m_o_rl.sprite m_o_rl.swi m_o_rl.template m_o_rl.trace m_o_rl.txt m_o_rl.txt1 \
 m_o_rl.txt3 m_o_rl.txtar m_o_rl.txtedit m_o_rl.txtfile m_o_rl.txtfind \
 m_o_rl.txtmisc m_o_rl.txtopt m_o_rl.txtoptmenu m_o_rl.txtregexp \
 m_o_rl.txtscrap m_o_rl.txtundo m_o_rl.txtwin m_o_rl.visdelay m_o_rl.werr \
 m_o_rl.wimp m_o_rl.wimpt m_o_rl.win m_o_rl.xferrecv m_o_rl.xfersend

#
# Build rules:
#
rom: ${TARGET}
        @echo ${COMPONENT}: rom library built

export: export_${PHASE}
        @echo ${COMPONENT}: export complete (${PHASE})

export_hdrs: ${EXP_HDR}.SharedCLib; @

export_libs: ${EXPORTS} dirs; @

install_rom: ${TARGET}
        ${CP} ${TARGET} ${INSTDIR}.${COMPONENT} ${CPFLAGS}
        @echo ${COMPONENT}: rom library installed

clean:
        @echo ${COMPONENT}: *** NOT cleaned *** run locally if required

clean_all:
        ${WIPE} o.* ${WFLAGS}
        ${WIPE} o_rl.* ${WFLAGS}
        ${WIPE} m_o_rl.* ${WFLAGS}
        ${WIPE} rm_o.* ${WFLAGS}
        ${WIPE} rm_o_rl.* ${WFLAGS}
        ${WIPE} linked.* ${WFLAGS}
        ${WIPE} map.* ${WFLAGS}
        ${RM} ${TARGET}
        ${RM} syms.RISC_OSLib
        ${RM} syms.Entries
        ${RM} syms.C_Entries
        ${RM} derived.swis
        ${RM} s.abssym
        ${RM} s.c_abssym
        ${RM} s.a_abssym
        ${WIPE} lib.* ${WFLAGS}
        @echo ${COMPONENT}: cleaned

resources:
        ${MKDIR} ${RESDIR}.${COMPONENT}
        ${MKDIR} ${RESDIR}.CLib
        ${CP} clib.Resources.${LOCALE}.Messages ${RESDIR}.CLib.Messages ${CPFLAGS}
        ${CP} rlib.Resources.${LOCALE}.Messages ${RESDIR}.RISC_OSLib.Messages ${CPFLAGS}
        @echo ${COMPONENT}: resource files copied

dirs:
        ${MKDIR} ${LIBDIR}
        ${MKDIR} ${LIBDIR}.CLib
        ${MKDIR} ${LIBDIR}.CLib.h
        ${MKDIR} ${LIBDIR}.CLib.o
        ${MKDIR} ${LIBDIR}.RISC_OSLib
        ${MKDIR} ${LIBDIR}.RISC_OSLib.h
        ${MKDIR} ${LIBDIR}.RISC_OSLib.h.EditIntern
        ${MKDIR} ${LIBDIR}.RISC_OSLib.s
        ${MKDIR} ${LIBDIR}.RISC_OSLib.o

#
# ROM target {re-linked at ROM Image build time}
#
${TARGET}: ${ROM_OBJS}
        ${LD} -o $@ -aof ${ROM_OBJS}

#
# Final link for the ROM Image {using given base address}
#
rom_link:
        ${LD} -o linked.RISC_OSLib ${ROM_OBJS} \
              -symbols syms.RISC_OSLib \
              -bin -base ${ADDRESS} \
              -map > map.RISC_OSLib
        ${CP} linked.RISC_OSLib ${LINKDIR}.RISC_OSLib ${CPFLAGS}
        |
        xtentries syms.Entries kernel.s.k_entries clib.s.cl_entries rlib.s.rl_entries
        print rlib.swi { >> syms.Entries }
        xtentries syms.C_Entries kernel.s.k_entries clib.s.cl_entries
        print rlib.swi { >> syms.C_Entries }
        |
        symgen syms.Entries syms.RISC_OSLib s.abssym
        symgen syms.C_Entries syms.RISC_OSLib s.c_abssym
        symgen syms.A_Entries syms.RISC_OSLib s.a_abssym
        |
        ${OBJASM} ${AFLAGS} -from s.abssym -to o.abssym
        ${OBJASM} ${AFLAGS} -from s.c_abssym -to o.c_abssym
        ${OBJASM} ${AFLAGS} -from s.a_abssym -to o.a_abssym
        |
        ${CP} o.abssym ${ABSSYM} ${CPFLAGS}
        ${CP} o.c_abssym ${C_ABSSYM} ${CPFLAGS}
        ${CP} o.a_abssym ${A_ABSSYM} ${CPFLAGS}
        @echo ${COMPONENT}: rom_link complete

#
# Build rules for Libraries and Stubs:
#
lib.ansilib: ${ANSI_OBJS}
        ${LIBFILE} ${LIBFLAGS} $@ ${ANSI_OBJS}

lib.risc_oslib: ${RLIB_OBJS}
        ${LIBFILE} ${LIBFLAGS} $@ ${RLIB_OBJS}

lib.riscoslibm: ${RLIB_MOD_OBJS}
        ${LIBFILE} ${LIBFLAGS} $@ ${RLIB_MOD_OBJS}

lib.stubs: clib.s.cl_stub_r
        ${OBJASM} ${AFLAGS} -from clib.s.cl_stub_r -to $@

lib.rstubs: rlib.s.rl_stub_r
        ${OBJASM} ${AFLAGS} -from rlib.s.rl_stub_r -to $@

lib.romcstubs: clib.s.cl_stub_rm
        ${OBJASM} ${AFLAGS} -from clib.s.cl_stub_rm -to $@

lib.romstubs: rlib.s.rl_stub_rm
        ${OBJASM} ${AFLAGS} -from rlib.s.rl_stub_rm -to $@

lib.romastubs: rlib.s.rl_stub_a
        ${OBJASM} ${AFLAGS} -from rlib.s.rl_stub_a -to $@

# Non-exported libraries:
lib.clib: ${CLIB_MOD_OBJS}
        ${LD} -o $@ -module ${CLIB_MOD_OBJS}

lib.arthurlib: o.arth_new_n o.arth_old_n o.ArtAsm_n o.ArtAsm_o
        ${LIBFILE} ${LIBFLAGS} $@ o.Arth_new_n o.Arth_old_n o.ArtAsm_n o.ArtAsm_o

# Derived headers:
derived.swis: s.makehswis
        ${AS} ${AFLAGS} -from s.makehswis -to $@
        settype $@ text

#
# Rules for exporting:
#
${EXP_HDR}.SharedCLib: hdr.SharedCLib
        ${CP} hdr.SharedCLib $@ ${CPFLAGS}

# Headers:
CLIB:h.assert: clib.h.assert;   ${CP} clib.h.assert $@ ${CPFLAGS}
CLIB:h.ctype: clib.h.ctype;     ${CP} clib.h.ctype $@ ${CPFLAGS}
CLIB:h.errno: clib.h.errno;     ${CP} clib.h.errno $@ ${CPFLAGS}
CLIB:h.float: clib.h.float;     ${CP} clib.h.float $@ ${CPFLAGS}
CLIB:h.kernel: clib.h.kernel;   ${CP} clib.h.kernel $@ ${CPFLAGS}
CLIB:h.limits: clib.h.limits;   ${CP} clib.h.limits $@ ${CPFLAGS}
CLIB:h.locale: clib.h.locale;   ${CP} clib.h.locale $@ ${CPFLAGS}
CLIB:h.math: clib.h.math;       ${CP} clib.h.math $@ ${CPFLAGS}
CLIB:h.setjmp: clib.h.setjmp;   ${CP} clib.h.setjmp $@ ${CPFLAGS}
CLIB:h.signal: clib.h.signal;   ${CP} clib.h.signal $@ ${CPFLAGS}
CLIB:h.stdarg: clib.h.stdarg;   ${CP} clib.h.stdarg $@ ${CPFLAGS}
CLIB:h.stddef: clib.h.stddef;   ${CP} clib.h.stddef $@ ${CPFLAGS}
CLIB:h.stdio: clib.h.stdio;     ${CP} clib.h.stdio $@ ${CPFLAGS}
CLIB:h.stdlib: clib.h.stdlib;   ${CP} clib.h.stdlib $@ ${CPFLAGS}
CLIB:h.string: clib.h.string;   ${CP} clib.h.string $@ ${CPFLAGS}
CLIB:h.swis: derived.swis;      ${CP} derived.swis $@ ${CPFLAGS}
CLIB:h.time: clib.h.time;       ${CP} clib.h.time $@ ${CPFLAGS}
CLIB:h.varargs: clib.h.varargs; ${CP} clib.h.varargs $@ ${CPFLAGS}

RISC_OSLib:h.akbd: rlib.h.akbd;              ${CP} rlib.h.akbd $@ ${CPFLAGS}
RISC_OSLib:h.alarm: rlib.h.alarm;            ${CP} rlib.h.alarm $@ ${CPFLAGS}
RISC_OSLib:h.baricon: rlib.h.baricon;        ${CP} rlib.h.baricon $@ ${CPFLAGS}
RISC_OSLib:h.bbc: rlib.h.bbc;                ${CP} rlib.h.bbc $@ ${CPFLAGS}
RISC_OSLib:h.colourmenu: rlib.h.colourmenu;  ${CP} rlib.h.colourmenu $@ ${CPFLAGS}
RISC_OSLib:h.colourpick: rlib.h.colourpick;  ${CP} rlib.h.colourpick $@ ${CPFLAGS}
RISC_OSLib:h.colourtran: rlib.h.colourtran;  ${CP} rlib.h.colourtran $@ ${CPFLAGS}
RISC_OSLib:h.coords: rlib.h.coords;          ${CP} rlib.h.coords $@ ${CPFLAGS}
RISC_OSLib:h.ctl: rlib.h.ctl;                ${CP} rlib.h.ctl $@ ${CPFLAGS}
RISC_OSLib:h.dbox: rlib.h.dbox;              ${CP} rlib.h.dbox $@ ${CPFLAGS}
RISC_OSLib:h.dboxfile: rlib.h.dboxfile;      ${CP} rlib.h.dboxfile $@ ${CPFLAGS}
RISC_OSLib:h.dboxquery: rlib.h.dboxquery;    ${CP} rlib.h.dboxquery $@ ${CPFLAGS}
RISC_OSLib:h.dboxtcol: rlib.h.dboxtcol;      ${CP} rlib.h.dboxtcol $@ ${CPFLAGS}
RISC_OSLib:h.dragasprit: rlib.h.dragasprit;  ${CP} rlib.h.dragasprit $@ ${CPFLAGS}
RISC_OSLib:h.drawfdiag: rlib.h.drawfdiag;    ${CP} rlib.h.drawfdiag $@ ${CPFLAGS}
RISC_OSLib:h.drawferror: rlib.h.drawferror;  ${CP} rlib.h.drawferror $@ ${CPFLAGS}
RISC_OSLib:h.drawfobj: rlib.h.drawfobj;      ${CP} rlib.h.drawfobj $@ ${CPFLAGS}
RISC_OSLib:h.drawftypes: rlib.h.drawftypes;  ${CP} rlib.h.drawftypes $@ ${CPFLAGS}
RISC_OSLib:h.drawmod: rlib.h.drawmod;        ${CP} rlib.h.drawmod $@ ${CPFLAGS}
RISC_OSLib:h.event: rlib.h.event;            ${CP} rlib.h.event $@ ${CPFLAGS}
RISC_OSLib:h.fileicon: rlib.h.fileicon;      ${CP} rlib.h.fileicon $@ ${CPFLAGS}
RISC_OSLib:h.flex: rlib.h.flex;              ${CP} rlib.h.flex $@ ${CPFLAGS}
RISC_OSLib:h.font: rlib.h.font;              ${CP} rlib.h.font $@ ${CPFLAGS}
RISC_OSLib:h.heap: rlib.h.heap;              ${CP} rlib.h.heap $@ ${CPFLAGS}
RISC_OSLib:h.help: rlib.h.help;              ${CP} rlib.h.help $@ ${CPFLAGS}
RISC_OSLib:h.magnify: rlib.h.magnify;        ${CP} rlib.h.magnify $@ ${CPFLAGS}
RISC_OSLib:h.menu: rlib.h.menu;              ${CP} rlib.h.menu $@ ${CPFLAGS}
RISC_OSLib:h.msgs: rlib.h.msgs;              ${CP} rlib.h.msgs $@ ${CPFLAGS}
RISC_OSLib:h.msgtrans: rlib.h.msgtrans;      ${CP} rlib.h.msgtrans $@ ${CPFLAGS}
RISC_OSLib:h.os: rlib.h.os;                  ${CP} rlib.h.os $@ ${CPFLAGS}
RISC_OSLib:h.pointer: rlib.h.pointer;        ${CP} rlib.h.pointer $@ ${CPFLAGS}
RISC_OSLib:h.print: rlib.h.print;            ${CP} rlib.h.print $@ ${CPFLAGS}
RISC_OSLib:h.res: rlib.h.res;                ${CP} rlib.h.res $@ ${CPFLAGS}
RISC_OSLib:h.resspr: rlib.h.resspr;          ${CP} rlib.h.resspr $@ ${CPFLAGS}
RISC_OSLib:h.saveas: rlib.h.saveas;          ${CP} rlib.h.saveas $@ ${CPFLAGS}
RISC_OSLib:h.sprite: rlib.h.sprite;          ${CP} rlib.h.sprite $@ ${CPFLAGS}
RISC_OSLib:h.template: rlib.h.template;      ${CP} rlib.h.template $@ ${CPFLAGS}
RISC_OSLib:h.trace: rlib.h.trace;            ${CP} rlib.h.trace $@ ${CPFLAGS}
RISC_OSLib:h.txt: rlib.h.txt;                ${CP} rlib.h.txt $@ ${CPFLAGS}
RISC_OSLib:h.txtedit: rlib.h.txtedit;        ${CP} rlib.h.txtedit $@ ${CPFLAGS}
RISC_OSLib:h.txtopt: rlib.h.txtopt;          ${CP} rlib.h.txtopt $@ ${CPFLAGS}
RISC_OSLib:h.txtscrap: rlib.h.txtscrap;      ${CP} rlib.h.txtscrap $@ ${CPFLAGS}
RISC_OSLib:h.txtwin: rlib.h.txtwin;          ${CP} rlib.h.txtwin $@ ${CPFLAGS}
RISC_OSLib:h.typdat: rlib.h.typdat;          ${CP} rlib.h.typdat $@ ${CPFLAGS}
RISC_OSLib:h.visdelay: rlib.h.visdelay;      ${CP} rlib.h.visdelay $@ ${CPFLAGS}
RISC_OSLib:h.werr: rlib.h.werr;              ${CP} rlib.h.werr $@ ${CPFLAGS}
RISC_OSLib:h.wimp: rlib.h.wimp;              ${CP} rlib.h.wimp $@ ${CPFLAGS}
RISC_OSLib:h.wimpt: rlib.h.wimpt;            ${CP} rlib.h.wimpt $@ ${CPFLAGS}
RISC_OSLib:h.win: rlib.h.win;                ${CP} rlib.h.win $@ ${CPFLAGS}
RISC_OSLib:h.xferrecv: rlib.h.xferrecv;      ${CP} rlib.h.xferrecv $@ ${CPFLAGS}
RISC_OSLib:h.xfersend: rlib.h.xfersend;      ${CP} rlib.h.xfersend $@ ${CPFLAGS}

RISC_OSLib:h.EditIntern.message: rlib.h.EditIntern.message;       ${CP} rlib.h.EditIntern.message $@ ${CPFLAGS}
RISC_OSLib:h.EditIntern.txtar: rlib.h.EditIntern.txtar;           ${CP} rlib.h.EditIntern.txtar $@ ${CPFLAGS}
RISC_OSLib:h.EditIntern.txtfile: rlib.h.EditIntern.txtfile;       ${CP} rlib.h.EditIntern.txtfile $@ ${CPFLAGS}
RISC_OSLib:h.EditIntern.txtoptmenu: rlib.h.EditIntern.txtoptmenu; ${CP} rlib.h.EditIntern.txtoptmenu $@ ${CPFLAGS}

# Libraries
Clib:o.ansilib:          lib.ansilib;        ${CP} lib.ansilib    $@ ${CPFLAGS}
CLib:o.stubs:            lib.stubs;          ${CP} lib.stubs $@ ${CPFLAGS}
RISC_OSLib:o.risc_oslib: lib.risc_oslib;     ${CP} lib.risc_oslib $@ ${CPFLAGS}
RISC_OSLib:o.riscoslibm: lib.riscoslibm;     ${CP} lib.riscoslibm $@ ${CPFLAGS}
RISC_OSLib:o.rstubs:     lib.rstubs;         ${CP} lib.rstubs $@ ${CPFLAGS}
RISC_OSLib:o.romstubs:   lib.romstubs;       ${CP} lib.romstubs $@ ${CPFLAGS}
RISC_OSLib:o.romastubs:  lib.romastubs;      ${CP} lib.romastubs $@ ${CPFLAGS}
RISC_OSLib:o.romcstubs:  lib.romcstubs;      ${CP} lib.romcstubs $@ ${CPFLAGS}

# ModuleWrap
RISC_OSLib:s.modulewrap: s.modulewrap;       ${CP} s.modulewrap $@ ${CPFLAGS}

#
# Objects whose name isn't the same as their source
#
o.clib: clib.s.cl_obj_r
        ${OBJASM} ${AFLAGS} -from clib.s.cl_obj_r -to $@

o.kernel: kernel.s.k_obj_r
        ${OBJASM} ${AFLAGS} -from kernel.s.k_obj_r -to $@

rm_o.bsearch_a: c.bsearch
        ${CC} ${CFLAGS} -ffah ${DFLAGS} -zm1 ${CSFLAGS} -zkA -o $@ c.bsearch

rm_o.clib:  clib.s.cl_obj_r
        ${OBJASM} ${AFLAGS} -from clib.s.cl_obj_r -to $@

rm_o.cl_modbody: clib.s.cl_mod_r
        ${OBJASM} ${AFLAGS} -from clib.s.cl_mod_r -to $@

rm_o_rl.rl_modbody: rlib.s.rl_mod_r
        ${OBJASM} ${AFLAGS} -from rlib.s.rl_mod_r -to $@

rm_o.k_modbody: kernel.s.k_mod_r
        ${OBJASM} ${AFLAGS} -from kernel.s.k_mod_r -to $@

rm_o.memcpy: s.memcpy s.h_regs
        ${OBJASM} ${AFLAGS} -from s.memcpy -to $@

rm_o.initmodule: clib.s.initmod_r
        ${OBJASM} ${AFLAGS} -from clib.s.initmod_r -to $@

rm_o_rl.initmodule: rlib.s.initmod_r
        ${OBJASM} ${AFLAGS} -from rlib.s.initmod_r -to $@

#
# Objects that require extra flags
#
o.armsys: c.armsys
        ${CC} ${CFLAGS} -fah ${VLFLAGS} -o $@ c.armsys

o.armprof: c.armprof
        ${CC} ${CFLAGS} -fah ${VLFLAGS} -pcc -o $@ c.armprof

o.string: c.string
        ${CC} ${CFLAGS} -fah -DSEPERATE_MEMCPY -o $@ c.string

rm_o.armsys: c.armsys
        ${CC} ${CFLAGS} -ffah ${DFLAGS} -zm1 ${CSFLAGS} ${VSFLAGS} -o $@ c.armsys

rm_o.string: c.string
        ${CC} ${CFLAGS} -ffah ${DFLAGS} -zm1 ${CSFLAGS} -DSEPERATE_MEMCPY -o $@ c.string

#
# Special case: use "rom_defs" for ROM library (o_rm), "defs" for the others
# Note: New Assembler - could use -PreDefine "UROM SETL {FALSE}"
#
o_rl.swi: rlib.s.swi
        ${CP} rlib.s.defs rlib.s.asmdefs ${CPFLAGS}
        ${OBJASM} rlib.s.swi o_rl.swi ${AFLAGS}

o_rl.poll: rlib.s.poll
        ${CP} rlib.s.defs rlib.s.asmdefs ${CPFLAGS}
        ${OBJASM} rlib.s.poll o_rl.poll ${AFLAGS}

m_o_rl.swi: rlib.s.swi
        ${CP} rlib.s.defs rlib.s.asmdefs ${CPFLAGS}
        ${OBJASM} rlib.s.swi m_o_rl.swi ${AFLAGS}

m_o_rl.poll: rlib.s.poll
        ${CP} rlib.s.defs rlib.s.asmdefs ${CPFLAGS}
        ${OBJASM} rlib.s.poll m_o_rl.poll ${AFLAGS}

rm_o_rl.swi: rlib.s.swi
        ${CP} rlib.s.rom_defs rlib.s.asmdefs ${CPFLAGS}
        ${OBJASM} rlib.s.swi rm_o_rl.swi ${AFLAGS}

rm_o_rl.poll: rlib.s.poll
        ${CP} rlib.s.rom_defs rlib.s.asmdefs ${CPFLAGS}
        ${OBJASM} rlib.s.poll rm_o_rl.poll ${AFLAGS}

#
# trace separated out to allow defining of TRACE
#
o_rl.trace: rlib.c.trace
   ${CC} ${CFLAGS} ${DFLAGS} -DTRACE -o o_rl.trace rlib.c.trace

m_o_rl.trace: rlib.c.trace
   ${CC} ${CFLAGS} -ffah ${DFLAGS} -zM -DTRACE -o m_o_rl.trace rlib.c.trace

rm_o_rl.trace: rlib.c.trace
   ${CC} ${CFLAGS} -ffah ${DFLAGS} -zm1 ${CSFLAGS} ${STK_EXTN} -DTRACE -o rm_o_rl.trace rlib.c.trace

#
# Arthur objects
#
o.arth_new_n: c.arthur
        ${CC} ${CFLAGS} -fah -o $@ c.arthur

o.arth_old_n: c.arthur
        ${CC} ${CFLAGS} -fah -DARTHUR_OLD_NAMES -o $@ c.arthur

o.ArtAsm_n: s.Art_n_r
        ${OBJASM} ${AFLAGS} -from s.Art_n_r -to $@

o.ArtAsm_o: s.Art_o_r
        ${OBJASM} ${AFLAGS} -from s.Art_o_r -to $@

# Dynamic dependencies:
rm_o.initmodule: clib.s.initmod_r
rm_o.initmodule: s.InitModule
rm_o.initmodule: s.h_StrongA
rm_o.initmodule: s.h_Regs
rm_o.initmodule: s.h_Brazil
rm_o.initmodule: s.h_stack
rm_o.initmodule: s.h_modmacro
rm_o.initmodule: s.h_workspc
m_o_rl.akbd:	rlib.c.akbd
m_o_rl.akbd:	rlib.h.os
m_o_rl.akbd:	C:h.kernel
m_o_rl.akbd:	rlib.h.trace
m_o_rl.akbd:	rlib.h.akbd
m_o_rl.alarm:	rlib.c.alarm
m_o_rl.alarm:	rlib.h.alarm
m_o_rl.alarm:	rlib.h.werr
m_o_rl.alarm:	rlib.h.os
m_o_rl.alarm:	C:h.kernel
m_o_rl.alarm:	rlib.h.msgs
m_o_rl.alarm:	C:h.swis
m_o_rl.alarm:	rlib.h.verintern.messages
m_o_rl.baricon:	rlib.c.baricon
m_o_rl.baricon:	rlib.h.os
m_o_rl.baricon:	C:h.kernel
m_o_rl.baricon:	rlib.h.wimp
m_o_rl.baricon:	rlib.h.sprite
m_o_rl.baricon:	rlib.h.wimpt
m_o_rl.baricon:	rlib.h.trace
m_o_rl.baricon:	rlib.h.bbc
m_o_rl.baricon:	rlib.h.sprite
m_o_rl.baricon:	rlib.h.win
m_o_rl.baricon:	rlib.h.menu
m_o_rl.baricon:	rlib.h.event
m_o_rl.baricon:	rlib.h.baricon
m_o_rl.baricon:	C:h.swis
m_o_rl.bastxt: rlib.s.bastxt
m_o_rl.bbc:	rlib.c.bbc
m_o_rl.bbc:	rlib.h.os
m_o_rl.bbc:	C:h.kernel
m_o_rl.bbc:	rlib.h.bbc
m_o_rl.bbc:	C:h.swis
m_o_rl.colourmenu:	rlib.c.colourmenu
m_o_rl.colourmenu:	rlib.h.os
m_o_rl.colourmenu:	C:h.kernel
m_o_rl.colourmenu:	rlib.h.wimp
m_o_rl.colourmenu:	rlib.h.sprite
m_o_rl.colourmenu:	rlib.h.menu
m_o_rl.colourmenu:	rlib.h.colourmenu
m_o_rl.colourtran:	rlib.c.colourtran
m_o_rl.colourtran:	rlib.h.colourtran
m_o_rl.colourtran:	rlib.h.os
m_o_rl.colourtran:	C:h.kernel
m_o_rl.colourtran:	rlib.h.wimp
m_o_rl.colourtran:	rlib.h.sprite
m_o_rl.colourtran:	rlib.h.font
m_o_rl.colourtran:	rlib.h.drawmod
m_o_rl.colourtran:	rlib.h.os
m_o_rl.colourtran:	rlib.h.wimp
m_o_rl.coords:	rlib.c.coords
m_o_rl.coords:	rlib.h.wimp
m_o_rl.coords:	rlib.h.os
m_o_rl.coords:	C:h.kernel
m_o_rl.coords:	rlib.h.sprite
m_o_rl.coords:	rlib.h.coords
m_o_rl.ctl:	rlib.c.ctl
m_o_rl.ctl:	C:h.kernel
m_o_rl.ctl:	C:h.swis
m_o_rl.ctl:	rlib.h.msgs
m_o_rl.ctl:	rlib.h.wimp
m_o_rl.ctl:	rlib.h.os
m_o_rl.ctl:	rlib.h.sprite
m_o_rl.ctl:	rlib.h.wimpt
m_o_rl.ctl:	rlib.h.win
m_o_rl.ctl:	rlib.h.werr
m_o_rl.ctl:	rlib.h.event
m_o_rl.ctl:	rlib.h.menu
m_o_rl.ctl:	rlib.h.res
m_o_rl.ctl:	rlib.h.menu
m_o_rl.ctl:	rlib.h.dbox
m_o_rl.ctl:	rlib.h.akbd
m_o_rl.ctl:	rlib.h.template
m_o_rl.ctl:	rlib.h.colourmenu
m_o_rl.ctl:	rlib.h.ctl
m_o_rl.ctl:	rlib.h.wimp
m_o_rl.ctl:	rlib.h.event
m_o_rl.dbox:	rlib.c.dbox
m_o_rl.dbox:	rlib.h.trace
m_o_rl.dbox:	rlib.h.werr
m_o_rl.dbox:	rlib.h.os
m_o_rl.dbox:	C:h.kernel
m_o_rl.dbox:	rlib.h.akbd
m_o_rl.dbox:	rlib.h.wimp
m_o_rl.dbox:	rlib.h.sprite
m_o_rl.dbox:	rlib.h.wimpt
m_o_rl.dbox:	rlib.h.win
m_o_rl.dbox:	rlib.h.menu
m_o_rl.dbox:	rlib.h.event
m_o_rl.dbox:	rlib.h.dbox
m_o_rl.dbox:	rlib.h.res
m_o_rl.dbox:	rlib.h.sprite
m_o_rl.dbox:	rlib.h.resspr
m_o_rl.dbox:	rlib.h.template
m_o_rl.dbox:	rlib.h.alarm
m_o_rl.dbox:	rlib.h.msgs
m_o_rl.dbox:	rlib.h.verintern.messages
m_o_rl.dboxfile:	rlib.c.dboxfile
m_o_rl.dboxfile:	rlib.h.dbox
m_o_rl.dboxfile:	rlib.h.dboxfile
m_o_rl.dboxfile:	rlib.h.trace
m_o_rl.dboxquery:	rlib.c.dboxquery
m_o_rl.dboxquery:	rlib.h.dbox
m_o_rl.dboxquery:	rlib.h.dboxquery
m_o_rl.dboxquery:	rlib.h.help
m_o_rl.dboxquery:	rlib.h.wimp
m_o_rl.dboxquery:	rlib.h.os
m_o_rl.dboxquery:	C:h.kernel
m_o_rl.dboxquery:	rlib.h.sprite
m_o_rl.dboxquery:	rlib.h.event
m_o_rl.dboxquery:	rlib.h.menu
m_o_rl.dboxtcol:	rlib.c.dboxtcol
m_o_rl.dboxtcol:	C:h.swis
m_o_rl.dboxtcol:	C:h.kernel
m_o_rl.dboxtcol:	rlib.h.colourpick
m_o_rl.dboxtcol:	rlib.h.coords
m_o_rl.dboxtcol:	rlib.h.wimp
m_o_rl.dboxtcol:	rlib.h.os
m_o_rl.dboxtcol:	rlib.h.sprite
m_o_rl.dboxtcol:	rlib.h.event
m_o_rl.dboxtcol:	rlib.h.menu
m_o_rl.dboxtcol:	rlib.h.dboxtcol
m_o_rl.dboxtcol:	rlib.h.help
m_o_rl.dboxtcol:	rlib.h.dbox
m_o_rl.dboxtcol:	rlib.h.os
m_o_rl.dboxtcol:	rlib.h.wimp
m_o_rl.dboxtcol:	rlib.h.wimpt
m_o_rl.dboxtcol:	rlib.h.win
m_o_rl.dragasprit:	rlib.c.dragasprit
m_o_rl.dragasprit:	rlib.h.os
m_o_rl.dragasprit:	C:h.kernel
m_o_rl.dragasprit:	rlib.h.dragasprit
m_o_rl.dragasprit:	rlib.h.sprite
m_o_rl.dragasprit:	rlib.h.wimp
m_o_rl.drawcheck:	rlib.c.drawcheck
m_o_rl.drawcheck:	rlib.h.os
m_o_rl.drawcheck:	C:h.kernel
m_o_rl.drawcheck:	rlib.h.sprite
m_o_rl.drawcheck:	rlib.h.bbc
m_o_rl.drawcheck:	rlib.h.font
m_o_rl.drawcheck:	rlib.h.drawmod
m_o_rl.drawcheck:	rlib.h.wimp
m_o_rl.drawcheck:	rlib.h.drawmod
m_o_rl.drawcheck:	rlib.h.wimpt
m_o_rl.drawcheck:	rlib.h.trace
m_o_rl.drawcheck:	rlib.h.DrawIntern.drawfile1
m_o_rl.drawcheck:	rlib.h.drawferror
m_o_rl.drawfdiag:	rlib.c.drawfdiag
m_o_rl.drawfdiag:	rlib.h.os
m_o_rl.drawfdiag:	C:h.kernel
m_o_rl.drawfdiag:	rlib.h.sprite
m_o_rl.drawfdiag:	rlib.h.DrawIntern.drawfile1
m_o_rl.drawfdiag:	rlib.h.drawfdiag
m_o_rl.drawfdiag:	rlib.h.drawfobj
m_o_rl.drawfdiag:	rlib.h.DrawIntern.drawcvttyp
m_o_rl.drawfdiag:	rlib.h.DrawIntern.drawfile2
m_o_rl.drawfdiag:	rlib.h.drawferror
m_o_rl.drawfiles:	rlib.c.drawfiles
m_o_rl.drawfiles:	rlib.h.os
m_o_rl.drawfiles:	C:h.kernel
m_o_rl.drawfiles:	rlib.h.bbc
m_o_rl.drawfiles:	rlib.h.sprite
m_o_rl.drawfiles:	rlib.h.font
m_o_rl.drawfiles:	rlib.h.drawmod
m_o_rl.drawfiles:	rlib.h.wimp
m_o_rl.drawfiles:	C:h.swis
m_o_rl.drawfiles:	rlib.h.DrawIntern.drawfile1
m_o_rl.drawfiles:	rlib.h.drawfdiag
m_o_rl.drawfiles:	rlib.h.DrawIntern.drawfile2
m_o_rl.drawfobj:	rlib.c.drawfobj
m_o_rl.drawfobj:	rlib.h.os
m_o_rl.drawfobj:	C:h.kernel
m_o_rl.drawfobj:	rlib.h.bbc
m_o_rl.drawfobj:	rlib.h.sprite
m_o_rl.drawfobj:	rlib.h.DrawIntern.drawfile1
m_o_rl.drawfobj:	rlib.h.drawfdiag
m_o_rl.drawfobj:	rlib.h.drawfobj
m_o_rl.drawfobj:	rlib.h.DrawIntern.drawcvttyp
m_o_rl.drawfobj:	rlib.h.DrawIntern.drawfile2
m_o_rl.drawfobj:	rlib.h.drawferror
m_o_rl.drawmod:	rlib.c.drawmod
m_o_rl.drawmod:	rlib.h.drawmod
m_o_rl.drawmod:	rlib.h.os
m_o_rl.drawmod:	C:h.kernel
m_o_rl.drawmod:	rlib.h.os
m_o_rl.drawtextc:	rlib.c.drawtextc
m_o_rl.drawtextc:	rlib.h.os
m_o_rl.drawtextc:	C:h.kernel
m_o_rl.drawtextc:	rlib.h.bbc
m_o_rl.drawtextc:	rlib.h.font
m_o_rl.drawtextc:	rlib.h.drawmod
m_o_rl.drawtextc:	rlib.h.wimp
m_o_rl.drawtextc:	rlib.h.sprite
m_o_rl.drawtextc:	rlib.h.sprite
m_o_rl.drawtextc:	rlib.h.DrawIntern.drawfile1
m_o_rl.drawtextc:	rlib.h.drawfdiag
m_o_rl.drawtextc:	rlib.h.DrawIntern.drawfile2
m_o_rl.drawtextc:	rlib.h.drawferror
m_o_rl.event:	rlib.c.event
m_o_rl.event:	rlib.h.trace
m_o_rl.event:	rlib.h.os
m_o_rl.event:	C:h.kernel
m_o_rl.event:	rlib.h.wimp
m_o_rl.event:	rlib.h.sprite
m_o_rl.event:	rlib.h.wimpt
m_o_rl.event:	rlib.h.win
m_o_rl.event:	rlib.h.menu
m_o_rl.event:	rlib.h.alarm
m_o_rl.event:	rlib.h.event
m_o_rl.fileicon:	rlib.c.fileicon
m_o_rl.fileicon:	rlib.h.os
m_o_rl.fileicon:	C:h.kernel
m_o_rl.fileicon:	rlib.h.wimp
m_o_rl.fileicon:	rlib.h.sprite
m_o_rl.fileicon:	rlib.h.wimpt
m_o_rl.fileicon:	rlib.h.sprite
m_o_rl.fileicon:	rlib.h.trace
m_o_rl.fileicon:	rlib.h.fileicon
m_o_rl.fileicon:	rlib.h.werr
m_o_rl.flex:	rlib.c.flex
m_o_rl.flex:	C:h.kernel
m_o_rl.flex:	C:h.swis
m_o_rl.flex:	rlib.h.os
m_o_rl.flex:	rlib.h.werr
m_o_rl.flex:	rlib.h.flex
m_o_rl.flex:	rlib.h.trace
m_o_rl.flex:	rlib.h.wimp
m_o_rl.flex:	rlib.h.sprite
m_o_rl.flex:	rlib.h.wimpt
m_o_rl.flex:	rlib.h.msgs
m_o_rl.flex:	rlib.h.verintern.messages
m_o_rl.font:	rlib.c.font
m_o_rl.font:	rlib.h.os
m_o_rl.font:	C:h.kernel
m_o_rl.font:	rlib.h.trace
m_o_rl.font:	rlib.h.msgs
m_o_rl.font:	rlib.h.wimp
m_o_rl.font:	rlib.h.sprite
m_o_rl.font:	rlib.h.font
m_o_rl.font:	rlib.h.drawmod
m_o_rl.font:	rlib.h.verintern.messages
m_o_rl.heap:	rlib.c.heap
m_o_rl.heap:	rlib.h.werr
m_o_rl.heap:	rlib.h.heap
m_o_rl.heap:	rlib.h.os
m_o_rl.heap:	C:h.kernel
m_o_rl.heap:	rlib.h.os
m_o_rl.heap:	rlib.h.flex
m_o_rl.heap:	rlib.h.msgs
m_o_rl.heap:	rlib.h.verintern.messages
m_o_rl.help:	rlib.c.help
m_o_rl.help:	rlib.h.os
m_o_rl.help:	C:h.kernel
m_o_rl.help:	rlib.h.wimp
m_o_rl.help:	rlib.h.sprite
m_o_rl.help:	rlib.h.wimpt
m_o_rl.help:	rlib.h.werr
m_o_rl.help:	rlib.h.trace
m_o_rl.help:	rlib.h.event
m_o_rl.help:	rlib.h.menu
m_o_rl.help:	rlib.h.dbox
m_o_rl.help:	rlib.h.msgs
m_o_rl.help:	rlib.h.help
m_o_rl.help:	C:h.swis
m_o_rl.magnify:	rlib.c.magnify
m_o_rl.magnify:	rlib.h.os
m_o_rl.magnify:	C:h.kernel
m_o_rl.magnify:	rlib.h.wimp
m_o_rl.magnify:	rlib.h.sprite
m_o_rl.magnify:	rlib.h.wimpt
m_o_rl.magnify:	rlib.h.dbox
m_o_rl.magnify:	rlib.h.magnify
m_o_rl.magnify:	rlib.h.help
m_o_rl.magnify:	rlib.h.event
m_o_rl.magnify:	rlib.h.menu
m_o_rl.menu:	rlib.c.menu
m_o_rl.menu:	rlib.h.os
m_o_rl.menu:	C:h.kernel
m_o_rl.menu:	rlib.h.wimp
m_o_rl.menu:	rlib.h.sprite
m_o_rl.menu:	rlib.h.werr
m_o_rl.menu:	rlib.h.menu
m_o_rl.menu:	rlib.h.sprite
m_o_rl.menu:	rlib.h.resspr
m_o_rl.menu:	rlib.h.msgs
m_o_rl.menu:	rlib.h.verintern.messages
m_o_rl.msgs:	rlib.c.msgs
m_o_rl.msgs:	rlib.h.msgs
m_o_rl.msgs:	C:h.swis
m_o_rl.msgs:	C:h.kernel
m_o_rl.msgs:	rlib.h.msgtrans
m_o_rl.msgs:	rlib.h.res
m_o_rl.msgs:	rlib.h.os
m_o_rl.os:	rlib.c.os
m_o_rl.os:	rlib.h.os
m_o_rl.os:	C:h.kernel
m_o_rl.pointer:	rlib.c.pointer
m_o_rl.pointer:	rlib.h.os
m_o_rl.pointer:	C:h.kernel
m_o_rl.pointer:	rlib.h.sprite
m_o_rl.pointer:	rlib.h.pointer
m_o_rl.pointer:	rlib.h.wimp
m_o_rl.poll: rlib.s.poll
m_o_rl.poll: rlib.s.asmdefs
m_o_rl.print:	rlib.c.print
m_o_rl.print:	rlib.h.os
m_o_rl.print:	C:h.kernel
m_o_rl.print:	rlib.h.print
m_o_rl.res:	rlib.c.res
m_o_rl.res:	rlib.h.os
m_o_rl.res:	C:h.kernel
m_o_rl.res:	rlib.h.trace
m_o_rl.res:	rlib.h.werr
m_o_rl.res:	rlib.h.res
m_o_rl.resspr:	rlib.c.resspr
m_o_rl.resspr:	C:h.swis
m_o_rl.resspr:	C:h.kernel
m_o_rl.resspr:	rlib.h.sprite
m_o_rl.resspr:	rlib.h.os
m_o_rl.resspr:	rlib.h.res
m_o_rl.resspr:	rlib.h.werr
m_o_rl.resspr:	rlib.h.msgs
m_o_rl.resspr:	rlib.h.verintern.messages
m_o_rl.resspr:	rlib.h.resspr
m_o_rl.saveas:	rlib.c.saveas
m_o_rl.saveas:	rlib.h.trace
m_o_rl.saveas:	rlib.h.os
m_o_rl.saveas:	C:h.kernel
m_o_rl.saveas:	rlib.h.bbc
m_o_rl.saveas:	rlib.h.wimp
m_o_rl.saveas:	rlib.h.sprite
m_o_rl.saveas:	rlib.h.wimpt
m_o_rl.saveas:	rlib.h.win
m_o_rl.saveas:	rlib.h.dbox
m_o_rl.saveas:	rlib.h.saveas
m_o_rl.saveas:	rlib.h.xfersend
m_o_rl.saveas:	rlib.h.fileicon
m_o_rl.saveas:	rlib.h.werr
m_o_rl.saveas:	rlib.h.menu
m_o_rl.saveas:	rlib.h.event
m_o_rl.saveas:	rlib.h.msgs
m_o_rl.saveas:	rlib.h.help
m_o_rl.saveas:	rlib.h.template
m_o_rl.saveas:	rlib.h.verintern.messages
m_o_rl.sprite:	rlib.c.sprite
m_o_rl.sprite:	rlib.h.os
m_o_rl.sprite:	C:h.kernel
m_o_rl.sprite:	rlib.h.sprite
m_o_rl.swi: rlib.s.swi
m_o_rl.swi: rlib.s.asmdefs
m_o_rl.swi: s.h_StrongA
m_o_rl.template:	rlib.c.template
m_o_rl.template:	C:h.swis
m_o_rl.template:	C:h.kernel
m_o_rl.template:	rlib.h.os
m_o_rl.template:	rlib.h.wimp
m_o_rl.template:	rlib.h.sprite
m_o_rl.template:	rlib.h.wimpt
m_o_rl.template:	rlib.h.res
m_o_rl.template:	rlib.h.sprite
m_o_rl.template:	rlib.h.resspr
m_o_rl.template:	rlib.h.werr
m_o_rl.template:	rlib.h.template
m_o_rl.template:	rlib.h.trace
m_o_rl.template:	rlib.h.msgs
m_o_rl.template:	rlib.h.font
m_o_rl.template:	rlib.h.drawmod
m_o_rl.template:	rlib.h.verintern.messages
m_o_rl.trace:	rlib.c.trace
m_o_rl.trace:	rlib.h.os
m_o_rl.trace:	C:h.kernel
m_o_rl.trace:	rlib.h.bbc
m_o_rl.trace:	rlib.h.wimp
m_o_rl.trace:	rlib.h.sprite
m_o_rl.trace:	rlib.h.wimpt
m_o_rl.txt:	rlib.c.txt
m_o_rl.txt:	rlib.h.txt
m_o_rl.txt:	rlib.h.EditIntern.txtundo
m_o_rl.txt:	rlib.h.EditIntern.txt1
m_o_rl.txt:	rlib.h.EditIntern.txt3
m_o_rl.txt:	rlib.h.EditIntern.txtar
m_o_rl.txt:	rlib.h.werr
m_o_rl.txt:	rlib.h.trace
m_o_rl.txt1:	rlib.c.txt1
m_o_rl.txt1:	rlib.h.trace
m_o_rl.txt1:	rlib.h.werr
m_o_rl.txt1:	rlib.h.flex
m_o_rl.txt1:	rlib.h.msgs
m_o_rl.txt1:	rlib.h.txt
m_o_rl.txt1:	rlib.h.EditIntern.txtundo
m_o_rl.txt1:	rlib.h.EditIntern.txt1
m_o_rl.txt1:	rlib.h.EditIntern.txt3
m_o_rl.txt1:	rlib.h.verintern.messages
m_o_rl.txt3:	rlib.c.txt3
m_o_rl.txt3:	rlib.h.trace
m_o_rl.txt3:	rlib.h.werr
m_o_rl.txt3:	rlib.h.txt
m_o_rl.txt3:	rlib.h.EditIntern.txtundo
m_o_rl.txt3:	rlib.h.EditIntern.txt1
m_o_rl.txt3:	rlib.h.EditIntern.txt3
m_o_rl.txtar:	rlib.c.txtar
m_o_rl.txtar:	rlib.h.os
m_o_rl.txtar:	C:h.kernel
m_o_rl.txtar:	C:h.swis
m_o_rl.txtar:	rlib.h.bbc
m_o_rl.txtar:	rlib.h.dbox
m_o_rl.txtar:	rlib.h.werr
m_o_rl.txtar:	rlib.h.akbd
m_o_rl.txtar:	rlib.h.wimp
m_o_rl.txtar:	rlib.h.sprite
m_o_rl.txtar:	rlib.h.wimpt
m_o_rl.txtar:	rlib.h.font
m_o_rl.txtar:	rlib.h.drawmod
m_o_rl.txtar:	rlib.h.trace
m_o_rl.txtar:	rlib.h.win
m_o_rl.txtar:	rlib.h.menu
m_o_rl.txtar:	rlib.h.event
m_o_rl.txtar:	rlib.h.xferrecv
m_o_rl.txtar:	rlib.h.visdelay
m_o_rl.txtar:	rlib.h.msgs
m_o_rl.txtar:	rlib.h.txt
m_o_rl.txtar:	rlib.h.EditIntern.txtundo
m_o_rl.txtar:	rlib.h.EditIntern.txt1
m_o_rl.txtar:	rlib.h.EditIntern.txt3
m_o_rl.txtar:	rlib.h.EditIntern.txtar
m_o_rl.txtar:	rlib.h.txtscrap
m_o_rl.txtar:	rlib.h.txtopt
m_o_rl.txtar:	rlib.h.verintern.messages
m_o_rl.txtedit:	rlib.c.txtedit
m_o_rl.txtedit:	rlib.h.akbd
m_o_rl.txtedit:	rlib.h.werr
m_o_rl.txtedit:	rlib.h.menu
m_o_rl.txtedit:	rlib.h.os
m_o_rl.txtedit:	C:h.kernel
m_o_rl.txtedit:	rlib.h.wimp
m_o_rl.txtedit:	rlib.h.sprite
m_o_rl.txtedit:	rlib.h.wimpt
m_o_rl.txtedit:	rlib.h.txt
m_o_rl.txtedit:	rlib.h.win
m_o_rl.txtedit:	rlib.h.txtwin
m_o_rl.txtedit:	rlib.h.flex
m_o_rl.txtedit:	rlib.h.txtscrap
m_o_rl.txtedit:	rlib.h.event
m_o_rl.txtedit:	rlib.h.txtedit
m_o_rl.txtedit:	rlib.h.typdat
m_o_rl.txtedit:	rlib.h.EditIntern.txtfind
m_o_rl.txtedit:	rlib.h.editintern.txtregexp
m_o_rl.txtedit:	rlib.h.EditIntern.txtmisc
m_o_rl.txtedit:	rlib.h.EditIntern.txtundo
m_o_rl.txtedit:	rlib.h.EditIntern.txtar
m_o_rl.txtedit:	rlib.h.dboxquery
m_o_rl.txtedit:	rlib.h.dboxfile
m_o_rl.txtedit:	rlib.h.trace
m_o_rl.txtedit:	rlib.h.dbox
m_o_rl.txtedit:	rlib.h.EditIntern.txtoptmenu
m_o_rl.txtedit:	rlib.h.xfersend
m_o_rl.txtedit:	rlib.h.xferrecv
m_o_rl.txtedit:	rlib.h.saveas
m_o_rl.txtedit:	rlib.h.typdat
m_o_rl.txtedit:	rlib.h.fileicon
m_o_rl.txtedit:	rlib.h.visdelay
m_o_rl.txtedit:	rlib.h.EditIntern.txtfile
m_o_rl.txtedit:	rlib.h.EditIntern.message
m_o_rl.txtedit:	rlib.h.Editintern.txtregexp
m_o_rl.txtedit:	C:h.swis
m_o_rl.txtedit:	rlib.h.txtopt
m_o_rl.txtedit:	rlib.h.msgs
m_o_rl.txtedit:	rlib.h.help
m_o_rl.txtedit:	rlib.h.template
m_o_rl.txtedit:	rlib.h.verintern.messages
m_o_rl.txtfile:	rlib.c.txtfile
m_o_rl.txtfile:	rlib.h.os
m_o_rl.txtfile:	C:h.kernel
m_o_rl.txtfile:	rlib.h.txt
m_o_rl.txtfile:	rlib.h.typdat
m_o_rl.txtfile:	rlib.h.flex
m_o_rl.txtfile:	C:h.swis
m_o_rl.txtfile:	rlib.h.wimpt
m_o_rl.txtfile:	rlib.h.wimp
m_o_rl.txtfile:	rlib.h.sprite
m_o_rl.txtfile:	rlib.h.EditIntern.txtundo
m_o_rl.txtfile:	rlib.h.txtedit
m_o_rl.txtfile:	rlib.h.menu
m_o_rl.txtfile:	rlib.h.xfersend
m_o_rl.txtfile:	rlib.h.xferrecv
m_o_rl.txtfile:	rlib.h.EditIntern.txtfile
m_o_rl.txtfile:	rlib.h.trace
m_o_rl.txtfile:	rlib.h.werr
m_o_rl.txtfile:	rlib.h.msgs
m_o_rl.txtfile:	rlib.h.visdelay
m_o_rl.txtfile:	rlib.h.verintern.messages
m_o_rl.txtfind:	rlib.c.txtfind
m_o_rl.txtfind:	rlib.h.werr
m_o_rl.txtfind:	rlib.h.txt
m_o_rl.txtfind:	rlib.h.EditIntern.txtregexp
m_o_rl.txtfind:	rlib.h.EditIntern.txtfind
m_o_rl.txtfind:	rlib.h.editintern.txtregexp
m_o_rl.txtfind:	rlib.h.trace
m_o_rl.txtfind:	rlib.h.msgs
m_o_rl.txtfind:	rlib.h.visdelay
m_o_rl.txtfind:	rlib.h.flex
m_o_rl.txtfind:	rlib.h.verintern.messages
m_o_rl.txtmisc:	rlib.c.txtmisc
m_o_rl.txtmisc:	rlib.h.werr
m_o_rl.txtmisc:	rlib.h.txt
m_o_rl.txtmisc:	rlib.h.flex
m_o_rl.txtmisc:	rlib.h.txtscrap
m_o_rl.txtmisc:	rlib.h.EditIntern.txtmisc
m_o_rl.txtmisc:	rlib.h.EditIntern.txtundo
m_o_rl.txtmisc:	rlib.h.trace
m_o_rl.txtmisc:	rlib.h.msgs
m_o_rl.txtmisc:	rlib.h.verintern.messages
m_o_rl.txtopt:	rlib.c.txtopt
m_o_rl.txtopt:	rlib.h.msgs
m_o_rl.txtopt:	rlib.h.werr
m_o_rl.txtopt:	rlib.h.txtopt
m_o_rl.txtopt:	rlib.h.verintern.messages
m_o_rl.txtoptmenu:	rlib.c.txtoptmenu
m_o_rl.txtoptmenu:	rlib.h.txt
m_o_rl.txtoptmenu:	rlib.h.os
m_o_rl.txtoptmenu:	C:h.kernel
m_o_rl.txtoptmenu:	rlib.h.wimp
m_o_rl.txtoptmenu:	rlib.h.sprite
m_o_rl.txtoptmenu:	rlib.h.wimpt
m_o_rl.txtoptmenu:	rlib.h.menu
m_o_rl.txtoptmenu:	rlib.h.EditIntern.txtar
m_o_rl.txtoptmenu:	rlib.h.dbox
m_o_rl.txtoptmenu:	rlib.h.event
m_o_rl.txtoptmenu:	rlib.h.EditIntern.txtoptmenu
m_o_rl.txtoptmenu:	rlib.h.visdelay
m_o_rl.txtoptmenu:	rlib.h.font
m_o_rl.txtoptmenu:	rlib.h.drawmod
m_o_rl.txtoptmenu:	rlib.h.trace
m_o_rl.txtoptmenu:	rlib.h.werr
m_o_rl.txtoptmenu:	rlib.h.colourmenu
m_o_rl.txtoptmenu:	rlib.h.msgs
m_o_rl.txtoptmenu:	rlib.h.txtwin
m_o_rl.txtoptmenu:	rlib.h.verintern.messages
m_o_rl.txtregexp:	rlib.c.txtregexp
m_o_rl.txtregexp:	rlib.h.EditIntern.txtregexp
m_o_rl.txtregexp:	rlib.h.txt
m_o_rl.txtregexp:	rlib.h.verintern.messages
m_o_rl.txtregexp:	rlib.h.msgs
m_o_rl.txtregexp:	rlib.h.txt
m_o_rl.txtregexp:	rlib.h.werr
m_o_rl.txtscrap:	rlib.c.txtscrap
m_o_rl.txtscrap:	rlib.h.txt
m_o_rl.txtscrap:	rlib.h.txtscrap
m_o_rl.txtundo:	rlib.c.txtundo
m_o_rl.txtundo:	rlib.h.flex
m_o_rl.txtundo:	rlib.h.trace
m_o_rl.txtundo:	rlib.h.txt
m_o_rl.txtundo:	rlib.h.EditIntern.txtundo
m_o_rl.txtundo:	rlib.h.EditIntern.txt1
m_o_rl.txtundo:	rlib.h.txtscrap
m_o_rl.txtundo:	rlib.h.werr
m_o_rl.txtwin:	rlib.c.txtwin
m_o_rl.txtwin:	rlib.h.trace
m_o_rl.txtwin:	rlib.h.os
m_o_rl.txtwin:	C:h.kernel
m_o_rl.txtwin:	rlib.h.wimp
m_o_rl.txtwin:	rlib.h.sprite
m_o_rl.txtwin:	rlib.h.wimpt
m_o_rl.txtwin:	rlib.h.win
m_o_rl.txtwin:	rlib.h.txt
m_o_rl.txtwin:	rlib.h.EditIntern.txtundo
m_o_rl.txtwin:	rlib.h.EditIntern.txt1
m_o_rl.txtwin:	rlib.h.EditIntern.txt3
m_o_rl.txtwin:	rlib.h.EditIntern.txtar
m_o_rl.txtwin:	rlib.h.txtwin
m_o_rl.visdelay:	rlib.c.visdelay
m_o_rl.visdelay:	rlib.h.os
m_o_rl.visdelay:	C:h.kernel
m_o_rl.visdelay:	rlib.h.visdelay
m_o_rl.werr:	rlib.c.werr
m_o_rl.werr:	C:h.swis
m_o_rl.werr:	C:h.kernel
m_o_rl.werr:	rlib.h.os
m_o_rl.werr:	rlib.h.wimp
m_o_rl.werr:	rlib.h.sprite
m_o_rl.werr:	rlib.h.werr
m_o_rl.werr:	rlib.h.wimpt
m_o_rl.wimp:	rlib.c.wimp
m_o_rl.wimp:	rlib.h.os
m_o_rl.wimp:	C:h.kernel
m_o_rl.wimp:	rlib.h.trace
m_o_rl.wimp:	rlib.h.wimp
m_o_rl.wimp:	rlib.h.sprite
m_o_rl.wimpt:	rlib.c.wimpt
m_o_rl.wimpt:	C:h.swis
m_o_rl.wimpt:	C:h.kernel
m_o_rl.wimpt:	rlib.h.akbd
m_o_rl.wimpt:	rlib.h.os
m_o_rl.wimpt:	rlib.h.bbc
m_o_rl.wimpt:	rlib.h.wimp
m_o_rl.wimpt:	rlib.h.sprite
m_o_rl.wimpt:	rlib.h.wimpt
m_o_rl.wimpt:	rlib.h.trace
m_o_rl.wimpt:	rlib.h.werr
m_o_rl.wimpt:	rlib.h.alarm
m_o_rl.wimpt:	rlib.h.event
m_o_rl.wimpt:	rlib.h.menu
m_o_rl.wimpt:	rlib.h.msgs
m_o_rl.wimpt:	rlib.h.win
m_o_rl.wimpt:	rlib.h.verintern.messages
m_o_rl.win:	rlib.c.win
m_o_rl.win:	rlib.h.trace
m_o_rl.win:	rlib.h.os
m_o_rl.win:	C:h.kernel
m_o_rl.win:	rlib.h.wimp
m_o_rl.win:	rlib.h.sprite
m_o_rl.win:	rlib.h.werr
m_o_rl.win:	rlib.h.wimpt
m_o_rl.win:	rlib.h.event
m_o_rl.win:	rlib.h.menu
m_o_rl.win:	rlib.h.msgs
m_o_rl.win:	rlib.h.verintern.messages
m_o_rl.win:	rlib.h.win
m_o_rl.xferrecv:	rlib.c.xferrecv
m_o_rl.xferrecv:	rlib.h.trace
m_o_rl.xferrecv:	rlib.h.os
m_o_rl.xferrecv:	C:h.kernel
m_o_rl.xferrecv:	rlib.h.bbc
m_o_rl.xferrecv:	rlib.h.wimp
m_o_rl.xferrecv:	rlib.h.sprite
m_o_rl.xferrecv:	rlib.h.wimpt
m_o_rl.xferrecv:	rlib.h.win
m_o_rl.xferrecv:	rlib.h.dbox
m_o_rl.xferrecv:	rlib.h.typdat
m_o_rl.xferrecv:	rlib.h.xfersend
m_o_rl.xferrecv:	rlib.h.fileicon
m_o_rl.xferrecv:	rlib.h.werr
m_o_rl.xferrecv:	rlib.h.menu
m_o_rl.xferrecv:	rlib.h.event
m_o_rl.xferrecv:	rlib.h.xferrecv
m_o_rl.xferrecv:	rlib.h.msgs
m_o_rl.xferrecv:	rlib.h.verintern.messages
m_o_rl.xfersend:	rlib.c.xfersend
m_o_rl.xfersend:	rlib.h.trace
m_o_rl.xfersend:	C:h.swis
m_o_rl.xfersend:	C:h.kernel
m_o_rl.xfersend:	rlib.h.os
m_o_rl.xfersend:	rlib.h.bbc
m_o_rl.xfersend:	rlib.h.wimp
m_o_rl.xfersend:	rlib.h.sprite
m_o_rl.xfersend:	rlib.h.wimpt
m_o_rl.xfersend:	rlib.h.win
m_o_rl.xfersend:	rlib.h.dbox
m_o_rl.xfersend:	rlib.h.xfersend
m_o_rl.xfersend:	rlib.h.fileicon
m_o_rl.xfersend:	rlib.h.werr
m_o_rl.xfersend:	rlib.h.menu
m_o_rl.xfersend:	rlib.h.event
m_o_rl.xfersend:	rlib.h.msgs
m_o_rl.xfersend:	rlib.h.dragasprit
m_o_rl.xfersend:	rlib.h.verintern.messages
o.alloc:	c.alloc
o.alloc:	h.hostsys
o.alloc:	h.alloc
o.alloc:	C:h.kernel
o.alloc:	C:h.swis
o.armprof:	c.armprof
o.armsys:	c.armsys
o.armsys:	h.hostsys
o.armsys:	h.territory
o.armsys:	C:h.kernel
o.armsys:	C:h.swis
o.clib: clib.s.cl_obj_r
o.clib: s.h_Regs
o.clib: s.h_Brazil
o.clib: s.h_objmacro
o.clib: clib.s.cl_data
o.clib: clib.s.cl_init
o.clib: clib.s.cl_body
o.clib: s.h_Stack
o.clib: rlib.s.asmdefs
o.clib: clib.s.h_signal
o.ctype:	c.ctype
o.ctype:	C:h.kernel
o.ctype:	h.territory
o.ctype:	C:h.swis
o.error:	c.error
o.error:	h.hostsys
o.fpprintf:	c.fpprintf
o.fpprintf:	h.hostsys
o.fpprintf:	C:h.kernel
o.kernel: kernel.s.k_obj_r
o.kernel: s.h_Regs
o.kernel: s.h_Brazil
o.kernel: s.h_objmacro
o.kernel: kernel.s.k_data
o.kernel: kernel.s.k_init
o.kernel: kernel.s.k_body
o.kernel: s.h_stack
o.kernel: s.h_workspc
o.kernel: s.h_StrongA
o.locale:	c.locale
o.locale:	h.hostsys
o.locale:	C:h.kernel
o.locale:	h.territory
o.locale:	C:h.swis
o.math:	c.math
o.math:	h.hostsys
o.memcpy: s.memcpy
o.memcpy: s.h_Regs
o.overmgr: s.overmgr
o.overmgr: s.h_StrongA
o.printf:	c.printf
o.printf:	h.hostsys
o.printf:	C:h.kernel
o.scanf:	c.scanf
o.scanf:	h.hostsys
o.scanf:	C:h.kernel
o.signal:	c.signal
o.signal:	h.hostsys
o.signal:	C:h.kernel
o.sort:	c.sort
o.sort:	h.hostsys
o.sort:	C:h.kernel
o.stdio:	c.stdio
o.stdio:	h.hostsys
o.stdio:	C:h.kernel
o.stdlib:	c.stdlib
o.stdlib:	h.hostsys
o.stdlib:	C:h.kernel
o.string:	c.string
o.string:	h.hostsys
o.string:	C:h.kernel
o.string:	h.territory
o.string:	C:h.swis
o.swiv: kernel.s.swiv
o.swiv: s.h_StrongA
o.time:	c.time
o.time:	C:h.kernel
o.time:	h.territory
o.time:	C:h.swis
lib.stubs: clib.s.cl_stub_r
lib.stubs: clib.s.cl_stub
lib.stubs: s.h_Regs
lib.stubs: s.h_Brazil
lib.stubs: s.h_stubs
lib.stubs: s.h_stack
lib.stubs: clib.s.h_signal
lib.stubs: clib.s.cl_init
lib.stubs: kernel.s.k_entries
lib.stubs: clib.s.cl_entries
lib.stubs: kernel.s.k_data
lib.stubs: clib.s.cl_data
lib.stubs: clib.s.clibdata
o_rl.akbd:	rlib.c.akbd
o_rl.akbd:	rlib.h.os
o_rl.akbd:	C:h.kernel
o_rl.akbd:	rlib.h.trace
o_rl.akbd:	rlib.h.akbd
o_rl.alarm:	rlib.c.alarm
o_rl.alarm:	rlib.h.alarm
o_rl.alarm:	rlib.h.werr
o_rl.alarm:	rlib.h.os
o_rl.alarm:	C:h.kernel
o_rl.alarm:	rlib.h.msgs
o_rl.alarm:	C:h.swis
o_rl.alarm:	rlib.h.verintern.messages
o_rl.baricon:	rlib.c.baricon
o_rl.baricon:	rlib.h.os
o_rl.baricon:	C:h.kernel
o_rl.baricon:	rlib.h.wimp
o_rl.baricon:	rlib.h.sprite
o_rl.baricon:	rlib.h.wimpt
o_rl.baricon:	rlib.h.trace
o_rl.baricon:	rlib.h.bbc
o_rl.baricon:	rlib.h.sprite
o_rl.baricon:	rlib.h.win
o_rl.baricon:	rlib.h.menu
o_rl.baricon:	rlib.h.event
o_rl.baricon:	rlib.h.baricon
o_rl.baricon:	C:h.swis
o_rl.bastxt: rlib.s.bastxt
o_rl.bbc:	rlib.c.bbc
o_rl.bbc:	rlib.h.os
o_rl.bbc:	C:h.kernel
o_rl.bbc:	rlib.h.bbc
o_rl.bbc:	C:h.swis
o_rl.colourmenu:	rlib.c.colourmenu
o_rl.colourmenu:	rlib.h.os
o_rl.colourmenu:	C:h.kernel
o_rl.colourmenu:	rlib.h.wimp
o_rl.colourmenu:	rlib.h.sprite
o_rl.colourmenu:	rlib.h.menu
o_rl.colourmenu:	rlib.h.colourmenu
o_rl.colourtran:	rlib.c.colourtran
o_rl.colourtran:	rlib.h.colourtran
o_rl.colourtran:	rlib.h.os
o_rl.colourtran:	C:h.kernel
o_rl.colourtran:	rlib.h.wimp
o_rl.colourtran:	rlib.h.sprite
o_rl.colourtran:	rlib.h.font
o_rl.colourtran:	rlib.h.drawmod
o_rl.colourtran:	rlib.h.os
o_rl.colourtran:	rlib.h.wimp
o_rl.coords:	rlib.c.coords
o_rl.coords:	rlib.h.wimp
o_rl.coords:	rlib.h.os
o_rl.coords:	C:h.kernel
o_rl.coords:	rlib.h.sprite
o_rl.coords:	rlib.h.coords
o_rl.ctl:	rlib.c.ctl
o_rl.ctl:	C:h.kernel
o_rl.ctl:	C:h.swis
o_rl.ctl:	rlib.h.msgs
o_rl.ctl:	rlib.h.wimp
o_rl.ctl:	rlib.h.os
o_rl.ctl:	rlib.h.sprite
o_rl.ctl:	rlib.h.wimpt
o_rl.ctl:	rlib.h.win
o_rl.ctl:	rlib.h.werr
o_rl.ctl:	rlib.h.event
o_rl.ctl:	rlib.h.menu
o_rl.ctl:	rlib.h.res
o_rl.ctl:	rlib.h.menu
o_rl.ctl:	rlib.h.dbox
o_rl.ctl:	rlib.h.akbd
o_rl.ctl:	rlib.h.template
o_rl.ctl:	rlib.h.colourmenu
o_rl.ctl:	rlib.h.ctl
o_rl.ctl:	rlib.h.wimp
o_rl.ctl:	rlib.h.event
o_rl.dbox:	rlib.c.dbox
o_rl.dbox:	rlib.h.trace
o_rl.dbox:	rlib.h.werr
o_rl.dbox:	rlib.h.os
o_rl.dbox:	C:h.kernel
o_rl.dbox:	rlib.h.akbd
o_rl.dbox:	rlib.h.wimp
o_rl.dbox:	rlib.h.sprite
o_rl.dbox:	rlib.h.wimpt
o_rl.dbox:	rlib.h.win
o_rl.dbox:	rlib.h.menu
o_rl.dbox:	rlib.h.event
o_rl.dbox:	rlib.h.dbox
o_rl.dbox:	rlib.h.res
o_rl.dbox:	rlib.h.sprite
o_rl.dbox:	rlib.h.resspr
o_rl.dbox:	rlib.h.template
o_rl.dbox:	rlib.h.alarm
o_rl.dbox:	rlib.h.msgs
o_rl.dbox:	rlib.h.verintern.messages
o_rl.dboxfile:	rlib.c.dboxfile
o_rl.dboxfile:	rlib.h.dbox
o_rl.dboxfile:	rlib.h.dboxfile
o_rl.dboxfile:	rlib.h.trace
o_rl.dboxquery:	rlib.c.dboxquery
o_rl.dboxquery:	rlib.h.dbox
o_rl.dboxquery:	rlib.h.dboxquery
o_rl.dboxquery:	rlib.h.help
o_rl.dboxquery:	rlib.h.wimp
o_rl.dboxquery:	rlib.h.os
o_rl.dboxquery:	C:h.kernel
o_rl.dboxquery:	rlib.h.sprite
o_rl.dboxquery:	rlib.h.event
o_rl.dboxquery:	rlib.h.menu
o_rl.dboxtcol:	rlib.c.dboxtcol
o_rl.dboxtcol:	C:h.swis
o_rl.dboxtcol:	C:h.kernel
o_rl.dboxtcol:	rlib.h.colourpick
o_rl.dboxtcol:	rlib.h.coords
o_rl.dboxtcol:	rlib.h.wimp
o_rl.dboxtcol:	rlib.h.os
o_rl.dboxtcol:	rlib.h.sprite
o_rl.dboxtcol:	rlib.h.event
o_rl.dboxtcol:	rlib.h.menu
o_rl.dboxtcol:	rlib.h.dboxtcol
o_rl.dboxtcol:	rlib.h.help
o_rl.dboxtcol:	rlib.h.dbox
o_rl.dboxtcol:	rlib.h.os
o_rl.dboxtcol:	rlib.h.wimp
o_rl.dboxtcol:	rlib.h.wimpt
o_rl.dboxtcol:	rlib.h.win
o_rl.dragasprit:	rlib.c.dragasprit
o_rl.dragasprit:	rlib.h.os
o_rl.dragasprit:	C:h.kernel
o_rl.dragasprit:	rlib.h.dragasprit
o_rl.dragasprit:	rlib.h.sprite
o_rl.dragasprit:	rlib.h.wimp
o_rl.drawcheck:	rlib.c.drawcheck
o_rl.drawcheck:	rlib.h.os
o_rl.drawcheck:	C:h.kernel
o_rl.drawcheck:	rlib.h.sprite
o_rl.drawcheck:	rlib.h.bbc
o_rl.drawcheck:	rlib.h.font
o_rl.drawcheck:	rlib.h.drawmod
o_rl.drawcheck:	rlib.h.wimp
o_rl.drawcheck:	rlib.h.drawmod
o_rl.drawcheck:	rlib.h.wimpt
o_rl.drawcheck:	rlib.h.trace
o_rl.drawcheck:	rlib.h.DrawIntern.drawfile1
o_rl.drawcheck:	rlib.h.drawferror
o_rl.drawfdiag:	rlib.c.drawfdiag
o_rl.drawfdiag:	rlib.h.os
o_rl.drawfdiag:	C:h.kernel
o_rl.drawfdiag:	rlib.h.sprite
o_rl.drawfdiag:	rlib.h.DrawIntern.drawfile1
o_rl.drawfdiag:	rlib.h.drawfdiag
o_rl.drawfdiag:	rlib.h.drawfobj
o_rl.drawfdiag:	rlib.h.DrawIntern.drawcvttyp
o_rl.drawfdiag:	rlib.h.DrawIntern.drawfile2
o_rl.drawfdiag:	rlib.h.drawferror
o_rl.drawfiles:	rlib.c.drawfiles
o_rl.drawfiles:	rlib.h.os
o_rl.drawfiles:	C:h.kernel
o_rl.drawfiles:	rlib.h.bbc
o_rl.drawfiles:	rlib.h.sprite
o_rl.drawfiles:	rlib.h.font
o_rl.drawfiles:	rlib.h.drawmod
o_rl.drawfiles:	rlib.h.wimp
o_rl.drawfiles:	C:h.swis
o_rl.drawfiles:	rlib.h.DrawIntern.drawfile1
o_rl.drawfiles:	rlib.h.drawfdiag
o_rl.drawfiles:	rlib.h.DrawIntern.drawfile2
o_rl.drawfobj:	rlib.c.drawfobj
o_rl.drawfobj:	rlib.h.os
o_rl.drawfobj:	C:h.kernel
o_rl.drawfobj:	rlib.h.bbc
o_rl.drawfobj:	rlib.h.sprite
o_rl.drawfobj:	rlib.h.DrawIntern.drawfile1
o_rl.drawfobj:	rlib.h.drawfdiag
o_rl.drawfobj:	rlib.h.drawfobj
o_rl.drawfobj:	rlib.h.DrawIntern.drawcvttyp
o_rl.drawfobj:	rlib.h.DrawIntern.drawfile2
o_rl.drawfobj:	rlib.h.drawferror
o_rl.drawmod:	rlib.c.drawmod
o_rl.drawmod:	rlib.h.drawmod
o_rl.drawmod:	rlib.h.os
o_rl.drawmod:	C:h.kernel
o_rl.drawmod:	rlib.h.os
o_rl.drawtextc:	rlib.c.drawtextc
o_rl.drawtextc:	rlib.h.os
o_rl.drawtextc:	C:h.kernel
o_rl.drawtextc:	rlib.h.bbc
o_rl.drawtextc:	rlib.h.font
o_rl.drawtextc:	rlib.h.drawmod
o_rl.drawtextc:	rlib.h.wimp
o_rl.drawtextc:	rlib.h.sprite
o_rl.drawtextc:	rlib.h.sprite
o_rl.drawtextc:	rlib.h.DrawIntern.drawfile1
o_rl.drawtextc:	rlib.h.drawfdiag
o_rl.drawtextc:	rlib.h.DrawIntern.drawfile2
o_rl.drawtextc:	rlib.h.drawferror
o_rl.event:	rlib.c.event
o_rl.event:	rlib.h.trace
o_rl.event:	rlib.h.os
o_rl.event:	C:h.kernel
o_rl.event:	rlib.h.wimp
o_rl.event:	rlib.h.sprite
o_rl.event:	rlib.h.wimpt
o_rl.event:	rlib.h.win
o_rl.event:	rlib.h.menu
o_rl.event:	rlib.h.alarm
o_rl.event:	rlib.h.event
o_rl.fileicon:	rlib.c.fileicon
o_rl.fileicon:	rlib.h.os
o_rl.fileicon:	C:h.kernel
o_rl.fileicon:	rlib.h.wimp
o_rl.fileicon:	rlib.h.sprite
o_rl.fileicon:	rlib.h.wimpt
o_rl.fileicon:	rlib.h.sprite
o_rl.fileicon:	rlib.h.trace
o_rl.fileicon:	rlib.h.fileicon
o_rl.fileicon:	rlib.h.werr
o_rl.flex:	rlib.c.flex
o_rl.flex:	C:h.kernel
o_rl.flex:	C:h.swis
o_rl.flex:	rlib.h.os
o_rl.flex:	rlib.h.werr
o_rl.flex:	rlib.h.flex
o_rl.flex:	rlib.h.trace
o_rl.flex:	rlib.h.wimp
o_rl.flex:	rlib.h.sprite
o_rl.flex:	rlib.h.wimpt
o_rl.flex:	rlib.h.msgs
o_rl.flex:	rlib.h.verintern.messages
o_rl.font:	rlib.c.font
o_rl.font:	rlib.h.os
o_rl.font:	C:h.kernel
o_rl.font:	rlib.h.trace
o_rl.font:	rlib.h.msgs
o_rl.font:	rlib.h.wimp
o_rl.font:	rlib.h.sprite
o_rl.font:	rlib.h.font
o_rl.font:	rlib.h.drawmod
o_rl.font:	rlib.h.verintern.messages
o_rl.heap:	rlib.c.heap
o_rl.heap:	rlib.h.werr
o_rl.heap:	rlib.h.heap
o_rl.heap:	rlib.h.os
o_rl.heap:	C:h.kernel
o_rl.heap:	rlib.h.os
o_rl.heap:	rlib.h.flex
o_rl.heap:	rlib.h.msgs
o_rl.heap:	rlib.h.verintern.messages
o_rl.help:	rlib.c.help
o_rl.help:	rlib.h.os
o_rl.help:	C:h.kernel
o_rl.help:	rlib.h.wimp
o_rl.help:	rlib.h.sprite
o_rl.help:	rlib.h.wimpt
o_rl.help:	rlib.h.werr
o_rl.help:	rlib.h.trace
o_rl.help:	rlib.h.event
o_rl.help:	rlib.h.menu
o_rl.help:	rlib.h.dbox
o_rl.help:	rlib.h.msgs
o_rl.help:	rlib.h.help
o_rl.help:	C:h.swis
o_rl.magnify:	rlib.c.magnify
o_rl.magnify:	rlib.h.os
o_rl.magnify:	C:h.kernel
o_rl.magnify:	rlib.h.wimp
o_rl.magnify:	rlib.h.sprite
o_rl.magnify:	rlib.h.wimpt
o_rl.magnify:	rlib.h.dbox
o_rl.magnify:	rlib.h.magnify
o_rl.magnify:	rlib.h.help
o_rl.magnify:	rlib.h.event
o_rl.magnify:	rlib.h.menu
o_rl.menu:	rlib.c.menu
o_rl.menu:	rlib.h.os
o_rl.menu:	C:h.kernel
o_rl.menu:	rlib.h.wimp
o_rl.menu:	rlib.h.sprite
o_rl.menu:	rlib.h.werr
o_rl.menu:	rlib.h.menu
o_rl.menu:	rlib.h.sprite
o_rl.menu:	rlib.h.resspr
o_rl.menu:	rlib.h.msgs
o_rl.menu:	rlib.h.verintern.messages
o_rl.msgs:	rlib.c.msgs
o_rl.msgs:	rlib.h.msgs
o_rl.msgs:	C:h.swis
o_rl.msgs:	C:h.kernel
o_rl.msgs:	rlib.h.msgtrans
o_rl.msgs:	rlib.h.res
o_rl.msgs:	rlib.h.os
o_rl.os:	rlib.c.os
o_rl.os:	rlib.h.os
o_rl.os:	C:h.kernel
o_rl.pointer:	rlib.c.pointer
o_rl.pointer:	rlib.h.os
o_rl.pointer:	C:h.kernel
o_rl.pointer:	rlib.h.sprite
o_rl.pointer:	rlib.h.pointer
o_rl.pointer:	rlib.h.wimp
o_rl.poll: rlib.s.poll
o_rl.poll: rlib.s.asmdefs
o_rl.print:	rlib.c.print
o_rl.print:	rlib.h.os
o_rl.print:	C:h.kernel
o_rl.print:	rlib.h.print
o_rl.res:	rlib.c.res
o_rl.res:	rlib.h.os
o_rl.res:	C:h.kernel
o_rl.res:	rlib.h.trace
o_rl.res:	rlib.h.werr
o_rl.res:	rlib.h.res
o_rl.resspr:	rlib.c.resspr
o_rl.resspr:	C:h.swis
o_rl.resspr:	C:h.kernel
o_rl.resspr:	rlib.h.sprite
o_rl.resspr:	rlib.h.os
o_rl.resspr:	rlib.h.res
o_rl.resspr:	rlib.h.werr
o_rl.resspr:	rlib.h.msgs
o_rl.resspr:	rlib.h.verintern.messages
o_rl.resspr:	rlib.h.resspr
o_rl.saveas:	rlib.c.saveas
o_rl.saveas:	rlib.h.trace
o_rl.saveas:	rlib.h.os
o_rl.saveas:	C:h.kernel
o_rl.saveas:	rlib.h.bbc
o_rl.saveas:	rlib.h.wimp
o_rl.saveas:	rlib.h.sprite
o_rl.saveas:	rlib.h.wimpt
o_rl.saveas:	rlib.h.win
o_rl.saveas:	rlib.h.dbox
o_rl.saveas:	rlib.h.saveas
o_rl.saveas:	rlib.h.xfersend
o_rl.saveas:	rlib.h.fileicon
o_rl.saveas:	rlib.h.werr
o_rl.saveas:	rlib.h.menu
o_rl.saveas:	rlib.h.event
o_rl.saveas:	rlib.h.msgs
o_rl.saveas:	rlib.h.help
o_rl.saveas:	rlib.h.template
o_rl.saveas:	rlib.h.verintern.messages
o_rl.sprite:	rlib.c.sprite
o_rl.sprite:	rlib.h.os
o_rl.sprite:	C:h.kernel
o_rl.sprite:	rlib.h.sprite
o_rl.swi: rlib.s.swi
o_rl.swi: rlib.s.asmdefs
o_rl.swi: s.h_StrongA
o_rl.template:	rlib.c.template
o_rl.template:	C:h.swis
o_rl.template:	C:h.kernel
o_rl.template:	rlib.h.os
o_rl.template:	rlib.h.wimp
o_rl.template:	rlib.h.sprite
o_rl.template:	rlib.h.wimpt
o_rl.template:	rlib.h.res
o_rl.template:	rlib.h.sprite
o_rl.template:	rlib.h.resspr
o_rl.template:	rlib.h.werr
o_rl.template:	rlib.h.template
o_rl.template:	rlib.h.trace
o_rl.template:	rlib.h.msgs
o_rl.template:	rlib.h.font
o_rl.template:	rlib.h.drawmod
o_rl.template:	rlib.h.verintern.messages
o_rl.trace:	rlib.c.trace
o_rl.trace:	rlib.h.os
o_rl.trace:	C:h.kernel
o_rl.trace:	rlib.h.bbc
o_rl.trace:	rlib.h.wimp
o_rl.trace:	rlib.h.sprite
o_rl.trace:	rlib.h.wimpt
o_rl.txt:	rlib.c.txt
o_rl.txt:	rlib.h.txt
o_rl.txt:	rlib.h.EditIntern.txtundo
o_rl.txt:	rlib.h.EditIntern.txt1
o_rl.txt:	rlib.h.EditIntern.txt3
o_rl.txt:	rlib.h.EditIntern.txtar
o_rl.txt:	rlib.h.werr
o_rl.txt:	rlib.h.trace
o_rl.txt1:	rlib.c.txt1
o_rl.txt1:	rlib.h.trace
o_rl.txt1:	rlib.h.werr
o_rl.txt1:	rlib.h.flex
o_rl.txt1:	rlib.h.msgs
o_rl.txt1:	rlib.h.txt
o_rl.txt1:	rlib.h.EditIntern.txtundo
o_rl.txt1:	rlib.h.EditIntern.txt1
o_rl.txt1:	rlib.h.EditIntern.txt3
o_rl.txt1:	rlib.h.verintern.messages
o_rl.txt3:	rlib.c.txt3
o_rl.txt3:	rlib.h.trace
o_rl.txt3:	rlib.h.werr
o_rl.txt3:	rlib.h.txt
o_rl.txt3:	rlib.h.EditIntern.txtundo
o_rl.txt3:	rlib.h.EditIntern.txt1
o_rl.txt3:	rlib.h.EditIntern.txt3
o_rl.txtar:	rlib.c.txtar
o_rl.txtar:	rlib.h.os
o_rl.txtar:	C:h.kernel
o_rl.txtar:	C:h.swis
o_rl.txtar:	rlib.h.bbc
o_rl.txtar:	rlib.h.dbox
o_rl.txtar:	rlib.h.werr
o_rl.txtar:	rlib.h.akbd
o_rl.txtar:	rlib.h.wimp
o_rl.txtar:	rlib.h.sprite
o_rl.txtar:	rlib.h.wimpt
o_rl.txtar:	rlib.h.font
o_rl.txtar:	rlib.h.drawmod
o_rl.txtar:	rlib.h.trace
o_rl.txtar:	rlib.h.win
o_rl.txtar:	rlib.h.menu
o_rl.txtar:	rlib.h.event
o_rl.txtar:	rlib.h.xferrecv
o_rl.txtar:	rlib.h.visdelay
o_rl.txtar:	rlib.h.msgs
o_rl.txtar:	rlib.h.txt
o_rl.txtar:	rlib.h.EditIntern.txtundo
o_rl.txtar:	rlib.h.EditIntern.txt1
o_rl.txtar:	rlib.h.EditIntern.txt3
o_rl.txtar:	rlib.h.EditIntern.txtar
o_rl.txtar:	rlib.h.txtscrap
o_rl.txtar:	rlib.h.txtopt
o_rl.txtar:	rlib.h.verintern.messages
o_rl.txtedit:	rlib.c.txtedit
o_rl.txtedit:	rlib.h.akbd
o_rl.txtedit:	rlib.h.werr
o_rl.txtedit:	rlib.h.menu
o_rl.txtedit:	rlib.h.os
o_rl.txtedit:	C:h.kernel
o_rl.txtedit:	rlib.h.wimp
o_rl.txtedit:	rlib.h.sprite
o_rl.txtedit:	rlib.h.wimpt
o_rl.txtedit:	rlib.h.txt
o_rl.txtedit:	rlib.h.win
o_rl.txtedit:	rlib.h.txtwin
o_rl.txtedit:	rlib.h.flex
o_rl.txtedit:	rlib.h.txtscrap
o_rl.txtedit:	rlib.h.event
o_rl.txtedit:	rlib.h.txtedit
o_rl.txtedit:	rlib.h.typdat
o_rl.txtedit:	rlib.h.EditIntern.txtfind
o_rl.txtedit:	rlib.h.editintern.txtregexp
o_rl.txtedit:	rlib.h.EditIntern.txtmisc
o_rl.txtedit:	rlib.h.EditIntern.txtundo
o_rl.txtedit:	rlib.h.EditIntern.txtar
o_rl.txtedit:	rlib.h.dboxquery
o_rl.txtedit:	rlib.h.dboxfile
o_rl.txtedit:	rlib.h.trace
o_rl.txtedit:	rlib.h.dbox
o_rl.txtedit:	rlib.h.EditIntern.txtoptmenu
o_rl.txtedit:	rlib.h.xfersend
o_rl.txtedit:	rlib.h.xferrecv
o_rl.txtedit:	rlib.h.saveas
o_rl.txtedit:	rlib.h.typdat
o_rl.txtedit:	rlib.h.fileicon
o_rl.txtedit:	rlib.h.visdelay
o_rl.txtedit:	rlib.h.EditIntern.txtfile
o_rl.txtedit:	rlib.h.EditIntern.message
o_rl.txtedit:	rlib.h.Editintern.txtregexp
o_rl.txtedit:	C:h.swis
o_rl.txtedit:	rlib.h.txtopt
o_rl.txtedit:	rlib.h.msgs
o_rl.txtedit:	rlib.h.help
o_rl.txtedit:	rlib.h.template
o_rl.txtedit:	rlib.h.verintern.messages
o_rl.txtfile:	rlib.c.txtfile
o_rl.txtfile:	rlib.h.os
o_rl.txtfile:	C:h.kernel
o_rl.txtfile:	rlib.h.txt
o_rl.txtfile:	rlib.h.typdat
o_rl.txtfile:	rlib.h.flex
o_rl.txtfile:	C:h.swis
o_rl.txtfile:	rlib.h.wimpt
o_rl.txtfile:	rlib.h.wimp
o_rl.txtfile:	rlib.h.sprite
o_rl.txtfile:	rlib.h.EditIntern.txtundo
o_rl.txtfile:	rlib.h.txtedit
o_rl.txtfile:	rlib.h.menu
o_rl.txtfile:	rlib.h.xfersend
o_rl.txtfile:	rlib.h.xferrecv
o_rl.txtfile:	rlib.h.EditIntern.txtfile
o_rl.txtfile:	rlib.h.trace
o_rl.txtfile:	rlib.h.werr
o_rl.txtfile:	rlib.h.msgs
o_rl.txtfile:	rlib.h.visdelay
o_rl.txtfile:	rlib.h.verintern.messages
o_rl.txtfind:	rlib.c.txtfind
o_rl.txtfind:	rlib.h.werr
o_rl.txtfind:	rlib.h.txt
o_rl.txtfind:	rlib.h.EditIntern.txtregexp
o_rl.txtfind:	rlib.h.EditIntern.txtfind
o_rl.txtfind:	rlib.h.editintern.txtregexp
o_rl.txtfind:	rlib.h.trace
o_rl.txtfind:	rlib.h.msgs
o_rl.txtfind:	rlib.h.visdelay
o_rl.txtfind:	rlib.h.flex
o_rl.txtfind:	rlib.h.verintern.messages
o_rl.txtmisc:	rlib.c.txtmisc
o_rl.txtmisc:	rlib.h.werr
o_rl.txtmisc:	rlib.h.txt
o_rl.txtmisc:	rlib.h.flex
o_rl.txtmisc:	rlib.h.txtscrap
o_rl.txtmisc:	rlib.h.EditIntern.txtmisc
o_rl.txtmisc:	rlib.h.EditIntern.txtundo
o_rl.txtmisc:	rlib.h.trace
o_rl.txtmisc:	rlib.h.msgs
o_rl.txtmisc:	rlib.h.verintern.messages
o_rl.txtopt:	rlib.c.txtopt
o_rl.txtopt:	rlib.h.msgs
o_rl.txtopt:	rlib.h.werr
o_rl.txtopt:	rlib.h.txtopt
o_rl.txtopt:	rlib.h.verintern.messages
o_rl.txtoptmenu:	rlib.c.txtoptmenu
o_rl.txtoptmenu:	rlib.h.txt
o_rl.txtoptmenu:	rlib.h.os
o_rl.txtoptmenu:	C:h.kernel
o_rl.txtoptmenu:	rlib.h.wimp
o_rl.txtoptmenu:	rlib.h.sprite
o_rl.txtoptmenu:	rlib.h.wimpt
o_rl.txtoptmenu:	rlib.h.menu
o_rl.txtoptmenu:	rlib.h.EditIntern.txtar
o_rl.txtoptmenu:	rlib.h.dbox
o_rl.txtoptmenu:	rlib.h.event
o_rl.txtoptmenu:	rlib.h.EditIntern.txtoptmenu
o_rl.txtoptmenu:	rlib.h.visdelay
o_rl.txtoptmenu:	rlib.h.font
o_rl.txtoptmenu:	rlib.h.drawmod
o_rl.txtoptmenu:	rlib.h.trace
o_rl.txtoptmenu:	rlib.h.werr
o_rl.txtoptmenu:	rlib.h.colourmenu
o_rl.txtoptmenu:	rlib.h.msgs
o_rl.txtoptmenu:	rlib.h.txtwin
o_rl.txtoptmenu:	rlib.h.verintern.messages
o_rl.txtregexp:	rlib.c.txtregexp
o_rl.txtregexp:	rlib.h.EditIntern.txtregexp
o_rl.txtregexp:	rlib.h.txt
o_rl.txtregexp:	rlib.h.verintern.messages
o_rl.txtregexp:	rlib.h.msgs
o_rl.txtregexp:	rlib.h.txt
o_rl.txtregexp:	rlib.h.werr
o_rl.txtscrap:	rlib.c.txtscrap
o_rl.txtscrap:	rlib.h.txt
o_rl.txtscrap:	rlib.h.txtscrap
o_rl.txtundo:	rlib.c.txtundo
o_rl.txtundo:	rlib.h.flex
o_rl.txtundo:	rlib.h.trace
o_rl.txtundo:	rlib.h.txt
o_rl.txtundo:	rlib.h.EditIntern.txtundo
o_rl.txtundo:	rlib.h.EditIntern.txt1
o_rl.txtundo:	rlib.h.txtscrap
o_rl.txtundo:	rlib.h.werr
o_rl.txtwin:	rlib.c.txtwin
o_rl.txtwin:	rlib.h.trace
o_rl.txtwin:	rlib.h.os
o_rl.txtwin:	C:h.kernel
o_rl.txtwin:	rlib.h.wimp
o_rl.txtwin:	rlib.h.sprite
o_rl.txtwin:	rlib.h.wimpt
o_rl.txtwin:	rlib.h.win
o_rl.txtwin:	rlib.h.txt
o_rl.txtwin:	rlib.h.EditIntern.txtundo
o_rl.txtwin:	rlib.h.EditIntern.txt1
o_rl.txtwin:	rlib.h.EditIntern.txt3
o_rl.txtwin:	rlib.h.EditIntern.txtar
o_rl.txtwin:	rlib.h.txtwin
o_rl.visdelay:	rlib.c.visdelay
o_rl.visdelay:	rlib.h.os
o_rl.visdelay:	C:h.kernel
o_rl.visdelay:	rlib.h.visdelay
o_rl.werr:	rlib.c.werr
o_rl.werr:	C:h.swis
o_rl.werr:	C:h.kernel
o_rl.werr:	rlib.h.os
o_rl.werr:	rlib.h.wimp
o_rl.werr:	rlib.h.sprite
o_rl.werr:	rlib.h.werr
o_rl.werr:	rlib.h.wimpt
o_rl.wimp:	rlib.c.wimp
o_rl.wimp:	rlib.h.os
o_rl.wimp:	C:h.kernel
o_rl.wimp:	rlib.h.trace
o_rl.wimp:	rlib.h.wimp
o_rl.wimp:	rlib.h.sprite
o_rl.wimpt:	rlib.c.wimpt
o_rl.wimpt:	C:h.swis
o_rl.wimpt:	C:h.kernel
o_rl.wimpt:	rlib.h.akbd
o_rl.wimpt:	rlib.h.os
o_rl.wimpt:	rlib.h.bbc
o_rl.wimpt:	rlib.h.wimp
o_rl.wimpt:	rlib.h.sprite
o_rl.wimpt:	rlib.h.wimpt
o_rl.wimpt:	rlib.h.trace
o_rl.wimpt:	rlib.h.werr
o_rl.wimpt:	rlib.h.alarm
o_rl.wimpt:	rlib.h.event
o_rl.wimpt:	rlib.h.menu
o_rl.wimpt:	rlib.h.msgs
o_rl.wimpt:	rlib.h.win
o_rl.wimpt:	rlib.h.verintern.messages
o_rl.win:	rlib.c.win
o_rl.win:	rlib.h.trace
o_rl.win:	rlib.h.os
o_rl.win:	C:h.kernel
o_rl.win:	rlib.h.wimp
o_rl.win:	rlib.h.sprite
o_rl.win:	rlib.h.werr
o_rl.win:	rlib.h.wimpt
o_rl.win:	rlib.h.event
o_rl.win:	rlib.h.menu
o_rl.win:	rlib.h.msgs
o_rl.win:	rlib.h.verintern.messages
o_rl.win:	rlib.h.win
o_rl.xferrecv:	rlib.c.xferrecv
o_rl.xferrecv:	rlib.h.trace
o_rl.xferrecv:	rlib.h.os
o_rl.xferrecv:	C:h.kernel
o_rl.xferrecv:	rlib.h.bbc
o_rl.xferrecv:	rlib.h.wimp
o_rl.xferrecv:	rlib.h.sprite
o_rl.xferrecv:	rlib.h.wimpt
o_rl.xferrecv:	rlib.h.win
o_rl.xferrecv:	rlib.h.dbox
o_rl.xferrecv:	rlib.h.typdat
o_rl.xferrecv:	rlib.h.xfersend
o_rl.xferrecv:	rlib.h.fileicon
o_rl.xferrecv:	rlib.h.werr
o_rl.xferrecv:	rlib.h.menu
o_rl.xferrecv:	rlib.h.event
o_rl.xferrecv:	rlib.h.xferrecv
o_rl.xferrecv:	rlib.h.msgs
o_rl.xferrecv:	rlib.h.verintern.messages
o_rl.xfersend:	rlib.c.xfersend
o_rl.xfersend:	rlib.h.trace
o_rl.xfersend:	C:h.swis
o_rl.xfersend:	C:h.kernel
o_rl.xfersend:	rlib.h.os
o_rl.xfersend:	rlib.h.bbc
o_rl.xfersend:	rlib.h.wimp
o_rl.xfersend:	rlib.h.sprite
o_rl.xfersend:	rlib.h.wimpt
o_rl.xfersend:	rlib.h.win
o_rl.xfersend:	rlib.h.dbox
o_rl.xfersend:	rlib.h.xfersend
o_rl.xfersend:	rlib.h.fileicon
o_rl.xfersend:	rlib.h.werr
o_rl.xfersend:	rlib.h.menu
o_rl.xfersend:	rlib.h.event
o_rl.xfersend:	rlib.h.msgs
o_rl.xfersend:	rlib.h.dragasprit
o_rl.xfersend:	rlib.h.verintern.messages
lib.rstubs: rlib.s.rl_stub_r
lib.rstubs: clib.s.cl_stub
lib.rstubs: s.h_Regs
lib.rstubs: s.h_Brazil
lib.rstubs: s.h_stubs
lib.rstubs: s.h_stack
lib.rstubs: clib.s.h_signal
lib.rstubs: clib.s.cl_init
lib.rstubs: kernel.s.k_entries
lib.rstubs: clib.s.cl_entries
lib.rstubs: rlib.s.rl_entries
lib.rstubs: kernel.s.k_data
lib.rstubs: clib.s.cl_data
lib.rstubs: clib.s.clibdata
lib.rstubs: rlib.s.rl_data
lib.rstubs: rlib.s.rlibdata
lib.romstubs: rlib.s.rl_stub_rm
lib.romstubs: clib.s.cl_stub
lib.romstubs: s.h_Regs
lib.romstubs: s.h_Brazil
lib.romstubs: s.h_stubs
lib.romstubs: s.h_stack
lib.romstubs: clib.s.h_signal
lib.romstubs: clib.s.cl_init
lib.romstubs: kernel.s.k_data
lib.romstubs: clib.s.cl_data
lib.romstubs: clib.s.clibdata
lib.romstubs: rlib.s.rl_data
lib.romstubs: rlib.s.rlibdata
lib.romcstubs: clib.s.cl_stub_rm
lib.romcstubs: clib.s.cl_stub
lib.romcstubs: s.h_Regs
lib.romcstubs: s.h_Brazil
lib.romcstubs: s.h_stubs
lib.romcstubs: s.h_stack
lib.romcstubs: clib.s.h_signal
lib.romcstubs: clib.s.cl_init
lib.romcstubs: kernel.s.k_data
lib.romcstubs: clib.s.cl_data
lib.romcstubs: clib.s.clibdata
derived.swis: Hdr:ListOpts
derived.swis: Hdr:PublicWS
derived.swis: Hdr:FSNumbers
derived.swis: Hdr:NewErrors
derived.swis: Hdr:SWIs
derived.swis: Hdr:CPU.Generic26
derived.swis: Hdr:IO.GenericIO
derived.swis: Hdr:ModHand
derived.swis: Hdr:ADFS
derived.swis: Hdr:ATAPI
derived.swis: Hdr:BasicTrans
derived.swis: Hdr:Buffer
derived.swis: Hdr:ARM3Cache
derived.swis: Hdr:CDROM
derived.swis: Hdr:CDFS
derived.swis: Hdr:ColourPick
derived.swis: Hdr:ColourTran
derived.swis: Hdr:DDT
derived.swis: Hdr:Debugger
derived.swis: Hdr:DeviceFS
derived.swis: Hdr:DMA
derived.swis: Hdr:DOSFS
derived.swis: Hdr:DragASprit
derived.swis: Hdr:DragAnObj
derived.swis: Hdr:Draw
derived.swis: Hdr:Econet
derived.swis: Hdr:FileCore
derived.swis: Hdr:FilerAct
derived.swis: Hdr:Filter
derived.swis: Hdr:Font
derived.swis: Hdr:FPEmulator
derived.swis: Hdr:Free
derived.swis: Hdr:FSLock
derived.swis: Hdr:Hourglass
derived.swis: Hdr:HostFS
derived.swis: Hdr:IIC
derived.swis: Hdr:Joystick
derived.swis: Hdr:MakePSFont
derived.swis: Hdr:MsgTrans
derived.swis: Hdr:RISCOS
derived.swis: Hdr:Parallel
derived.swis: Hdr:PDriver
derived.swis: Hdr:PDumper
derived.swis: Hdr:Podule
derived.swis: Hdr:Portable
derived.swis: Hdr:RAMFS
derived.swis: Hdr:ResourceFS
derived.swis: Hdr:ScrBlank
derived.swis: Hdr:ScrModes
derived.swis: Hdr:SCSI
derived.swis: Hdr:SCSIFS
derived.swis: Hdr:SharedCLib
derived.swis: Hdr:Shell
derived.swis: Hdr:Sound
derived.swis: Hdr:Squash
derived.swis: Hdr:Super
derived.swis: Hdr:Switcher
derived.swis: Hdr:TaskWindow
derived.swis: Hdr:Territory
derived.swis: Hdr:Wimp
rm_o.cl_rmhdr: clib.s.cl_rmhdr
rm_o.cl_rmhdr: s.Version
rm_o_rl.initmodule: rlib.s.initmod_r
rm_o_rl.initmodule: s.initmodule
rm_o_rl.initmodule: s.h_StrongA
rm_o_rl.initmodule: s.h_Regs
rm_o_rl.initmodule: s.h_Brazil
rm_o_rl.initmodule: s.h_stack
rm_o_rl.initmodule: s.h_modmacro
rm_o_rl.initmodule: s.h_workspc
rm_o.k_modbody: kernel.s.k_mod_r
rm_o.k_modbody: s.h_Regs
rm_o.k_modbody: s.h_Brazil
rm_o.k_modbody: s.h_modmacro
rm_o.k_modbody: kernel.s.k_data
rm_o.k_modbody: kernel.s.k_entries
rm_o.k_modbody: kernel.s.k_entries
rm_o.k_modbody: kernel.s.k_body
rm_o.k_modbody: s.h_stack
rm_o.k_modbody: s.h_workspc
rm_o.k_modbody: s.h_StrongA
rm_o.cl_modbody: clib.s.cl_mod_r
rm_o.cl_modbody: s.h_Regs
rm_o.cl_modbody: s.h_Brazil
rm_o.cl_modbody: s.h_modmacro
rm_o.cl_modbody: clib.s.cl_data
rm_o.cl_modbody: clib.s.cl_entries
rm_o.cl_modbody: clib.s.cl_entries
rm_o.cl_modbody: clib.s.cl_body
rm_o.cl_modbody: s.h_Stack
rm_o.cl_modbody: rlib.s.asmdefs
rm_o.cl_modbody: clib.s.h_signal
rm_o.alloc:	c.alloc
rm_o.alloc:	h.hostsys
rm_o.alloc:	h.alloc
rm_o.alloc:	C:h.kernel
rm_o.alloc:	C:h.swis
rm_o.armsys:	c.armsys
rm_o.armsys:	h.hostsys
rm_o.armsys:	h.territory
rm_o.armsys:	C:h.kernel
rm_o.armsys:	C:h.swis
rm_o.bsearch_a:	c.bsearch
rm_o.ctype:	c.ctype
rm_o.ctype:	C:h.kernel
rm_o.ctype:	h.territory
rm_o.ctype:	C:h.swis
rm_o.error:	c.error
rm_o.error:	h.hostsys
rm_o.fpprintf:	c.fpprintf
rm_o.fpprintf:	h.hostsys
rm_o.fpprintf:	C:h.kernel
rm_o.locale:	c.locale
rm_o.locale:	h.hostsys
rm_o.locale:	C:h.kernel
rm_o.locale:	h.territory
rm_o.locale:	C:h.swis
rm_o.math:	c.math
rm_o.math:	h.hostsys
rm_o.memcpy: s.memcpy
rm_o.memcpy: s.h_Regs
rm_o.printf:	c.printf
rm_o.printf:	h.hostsys
rm_o.printf:	C:h.kernel
rm_o.scanf:	c.scanf
rm_o.scanf:	h.hostsys
rm_o.scanf:	C:h.kernel
rm_o.signal:	c.signal
rm_o.signal:	h.hostsys
rm_o.signal:	C:h.kernel
rm_o.sort:	c.sort
rm_o.sort:	h.hostsys
rm_o.sort:	C:h.kernel
rm_o.stdio:	c.stdio
rm_o.stdio:	h.hostsys
rm_o.stdio:	C:h.kernel
rm_o.stdlib:	c.stdlib
rm_o.stdlib:	h.hostsys
rm_o.stdlib:	C:h.kernel
rm_o.string:	c.string
rm_o.string:	h.hostsys
rm_o.string:	C:h.kernel
rm_o.string:	h.territory
rm_o.string:	C:h.swis
rm_o.time:	c.time
rm_o.time:	C:h.kernel
rm_o.time:	h.territory
rm_o.time:	C:h.swis
rm_o.swiv: kernel.s.swiv
rm_o.swiv: s.h_StrongA
rm_o.cl_spare: clib.s.cl_spare
rm_o_rl.rl_modbody: rlib.s.rl_mod_r
rm_o_rl.rl_modbody: s.h_regs
rm_o_rl.rl_modbody: s.h_brazil
rm_o_rl.rl_modbody: s.h_modmacro
rm_o_rl.rl_modbody: rlib.s.rl_data
rm_o_rl.rl_modbody: rlib.s.rl_entries
rm_o_rl.akbd:	rlib.c.akbd
rm_o_rl.akbd:	rlib.h.os
rm_o_rl.akbd:	C:h.kernel
rm_o_rl.akbd:	rlib.h.trace
rm_o_rl.akbd:	rlib.h.akbd
rm_o_rl.alarm:	rlib.c.alarm
rm_o_rl.alarm:	rlib.h.alarm
rm_o_rl.alarm:	rlib.h.werr
rm_o_rl.alarm:	rlib.h.os
rm_o_rl.alarm:	C:h.kernel
rm_o_rl.alarm:	rlib.h.msgs
rm_o_rl.alarm:	C:h.swis
rm_o_rl.alarm:	rlib.h.verintern.messages
rm_o_rl.baricon:	rlib.c.baricon
rm_o_rl.baricon:	rlib.h.os
rm_o_rl.baricon:	C:h.kernel
rm_o_rl.baricon:	rlib.h.wimp
rm_o_rl.baricon:	rlib.h.sprite
rm_o_rl.baricon:	rlib.h.wimpt
rm_o_rl.baricon:	rlib.h.trace
rm_o_rl.baricon:	rlib.h.bbc
rm_o_rl.baricon:	rlib.h.sprite
rm_o_rl.baricon:	rlib.h.win
rm_o_rl.baricon:	rlib.h.menu
rm_o_rl.baricon:	rlib.h.event
rm_o_rl.baricon:	rlib.h.baricon
rm_o_rl.baricon:	C:h.swis
rm_o_rl.bastxt: rlib.s.bastxt
rm_o_rl.bbc:	rlib.c.bbc
rm_o_rl.bbc:	rlib.h.os
rm_o_rl.bbc:	C:h.kernel
rm_o_rl.bbc:	rlib.h.bbc
rm_o_rl.bbc:	C:h.swis
rm_o_rl.colourmenu:	rlib.c.colourmenu
rm_o_rl.colourmenu:	rlib.h.os
rm_o_rl.colourmenu:	C:h.kernel
rm_o_rl.colourmenu:	rlib.h.wimp
rm_o_rl.colourmenu:	rlib.h.sprite
rm_o_rl.colourmenu:	rlib.h.menu
rm_o_rl.colourmenu:	rlib.h.colourmenu
rm_o_rl.colourtran:	rlib.c.colourtran
rm_o_rl.colourtran:	rlib.h.colourtran
rm_o_rl.colourtran:	rlib.h.os
rm_o_rl.colourtran:	C:h.kernel
rm_o_rl.colourtran:	rlib.h.wimp
rm_o_rl.colourtran:	rlib.h.sprite
rm_o_rl.colourtran:	rlib.h.font
rm_o_rl.colourtran:	rlib.h.drawmod
rm_o_rl.colourtran:	rlib.h.os
rm_o_rl.colourtran:	rlib.h.wimp
rm_o_rl.dbox:	rlib.c.dbox
rm_o_rl.dbox:	rlib.h.trace
rm_o_rl.dbox:	rlib.h.werr
rm_o_rl.dbox:	rlib.h.os
rm_o_rl.dbox:	C:h.kernel
rm_o_rl.dbox:	rlib.h.akbd
rm_o_rl.dbox:	rlib.h.wimp
rm_o_rl.dbox:	rlib.h.sprite
rm_o_rl.dbox:	rlib.h.wimpt
rm_o_rl.dbox:	rlib.h.win
rm_o_rl.dbox:	rlib.h.menu
rm_o_rl.dbox:	rlib.h.event
rm_o_rl.dbox:	rlib.h.dbox
rm_o_rl.dbox:	rlib.h.res
rm_o_rl.dbox:	rlib.h.sprite
rm_o_rl.dbox:	rlib.h.resspr
rm_o_rl.dbox:	rlib.h.template
rm_o_rl.dbox:	rlib.h.alarm
rm_o_rl.dbox:	rlib.h.msgs
rm_o_rl.dbox:	rlib.h.verintern.messages
rm_o_rl.dboxfile:	rlib.c.dboxfile
rm_o_rl.dboxfile:	rlib.h.dbox
rm_o_rl.dboxfile:	rlib.h.dboxfile
rm_o_rl.dboxfile:	rlib.h.trace
rm_o_rl.dboxquery:	rlib.c.dboxquery
rm_o_rl.dboxquery:	rlib.h.dbox
rm_o_rl.dboxquery:	rlib.h.dboxquery
rm_o_rl.dboxquery:	rlib.h.help
rm_o_rl.dboxquery:	rlib.h.wimp
rm_o_rl.dboxquery:	rlib.h.os
rm_o_rl.dboxquery:	C:h.kernel
rm_o_rl.dboxquery:	rlib.h.sprite
rm_o_rl.dboxquery:	rlib.h.event
rm_o_rl.dboxquery:	rlib.h.menu
rm_o_rl.dboxtcol:	rlib.c.dboxtcol
rm_o_rl.dboxtcol:	C:h.swis
rm_o_rl.dboxtcol:	C:h.kernel
rm_o_rl.dboxtcol:	rlib.h.colourpick
rm_o_rl.dboxtcol:	rlib.h.coords
rm_o_rl.dboxtcol:	rlib.h.wimp
rm_o_rl.dboxtcol:	rlib.h.os
rm_o_rl.dboxtcol:	rlib.h.sprite
rm_o_rl.dboxtcol:	rlib.h.event
rm_o_rl.dboxtcol:	rlib.h.menu
rm_o_rl.dboxtcol:	rlib.h.dboxtcol
rm_o_rl.dboxtcol:	rlib.h.help
rm_o_rl.dboxtcol:	rlib.h.dbox
rm_o_rl.dboxtcol:	rlib.h.os
rm_o_rl.dboxtcol:	rlib.h.wimp
rm_o_rl.dboxtcol:	rlib.h.wimpt
rm_o_rl.dboxtcol:	rlib.h.win
rm_o_rl.dragasprit:	rlib.c.dragasprit
rm_o_rl.dragasprit:	rlib.h.os
rm_o_rl.dragasprit:	C:h.kernel
rm_o_rl.dragasprit:	rlib.h.dragasprit
rm_o_rl.dragasprit:	rlib.h.sprite
rm_o_rl.dragasprit:	rlib.h.wimp
rm_o_rl.drawmod:	rlib.c.drawmod
rm_o_rl.drawmod:	rlib.h.drawmod
rm_o_rl.drawmod:	rlib.h.os
rm_o_rl.drawmod:	C:h.kernel
rm_o_rl.drawmod:	rlib.h.os
rm_o_rl.event:	rlib.c.event
rm_o_rl.event:	rlib.h.trace
rm_o_rl.event:	rlib.h.os
rm_o_rl.event:	C:h.kernel
rm_o_rl.event:	rlib.h.wimp
rm_o_rl.event:	rlib.h.sprite
rm_o_rl.event:	rlib.h.wimpt
rm_o_rl.event:	rlib.h.win
rm_o_rl.event:	rlib.h.menu
rm_o_rl.event:	rlib.h.alarm
rm_o_rl.event:	rlib.h.event
rm_o_rl.fileicon:	rlib.c.fileicon
rm_o_rl.fileicon:	rlib.h.os
rm_o_rl.fileicon:	C:h.kernel
rm_o_rl.fileicon:	rlib.h.wimp
rm_o_rl.fileicon:	rlib.h.sprite
rm_o_rl.fileicon:	rlib.h.wimpt
rm_o_rl.fileicon:	rlib.h.sprite
rm_o_rl.fileicon:	rlib.h.trace
rm_o_rl.fileicon:	rlib.h.fileicon
rm_o_rl.fileicon:	rlib.h.werr
rm_o_rl.flex:	rlib.c.flex
rm_o_rl.flex:	C:h.kernel
rm_o_rl.flex:	C:h.swis
rm_o_rl.flex:	rlib.h.os
rm_o_rl.flex:	rlib.h.werr
rm_o_rl.flex:	rlib.h.flex
rm_o_rl.flex:	rlib.h.trace
rm_o_rl.flex:	rlib.h.wimp
rm_o_rl.flex:	rlib.h.sprite
rm_o_rl.flex:	rlib.h.wimpt
rm_o_rl.flex:	rlib.h.msgs
rm_o_rl.flex:	rlib.h.verintern.messages
rm_o_rl.font:	rlib.c.font
rm_o_rl.font:	rlib.h.os
rm_o_rl.font:	C:h.kernel
rm_o_rl.font:	rlib.h.trace
rm_o_rl.font:	rlib.h.msgs
rm_o_rl.font:	rlib.h.wimp
rm_o_rl.font:	rlib.h.sprite
rm_o_rl.font:	rlib.h.font
rm_o_rl.font:	rlib.h.drawmod
rm_o_rl.font:	rlib.h.verintern.messages
rm_o_rl.heap:	rlib.c.heap
rm_o_rl.heap:	rlib.h.werr
rm_o_rl.heap:	rlib.h.heap
rm_o_rl.heap:	rlib.h.os
rm_o_rl.heap:	C:h.kernel
rm_o_rl.heap:	rlib.h.os
rm_o_rl.heap:	rlib.h.flex
rm_o_rl.heap:	rlib.h.msgs
rm_o_rl.heap:	rlib.h.verintern.messages
rm_o_rl.magnify:	rlib.c.magnify
rm_o_rl.magnify:	rlib.h.os
rm_o_rl.magnify:	C:h.kernel
rm_o_rl.magnify:	rlib.h.wimp
rm_o_rl.magnify:	rlib.h.sprite
rm_o_rl.magnify:	rlib.h.wimpt
rm_o_rl.magnify:	rlib.h.dbox
rm_o_rl.magnify:	rlib.h.magnify
rm_o_rl.magnify:	rlib.h.help
rm_o_rl.magnify:	rlib.h.event
rm_o_rl.magnify:	rlib.h.menu
rm_o_rl.menu:	rlib.c.menu
rm_o_rl.menu:	rlib.h.os
rm_o_rl.menu:	C:h.kernel
rm_o_rl.menu:	rlib.h.wimp
rm_o_rl.menu:	rlib.h.sprite
rm_o_rl.menu:	rlib.h.werr
rm_o_rl.menu:	rlib.h.menu
rm_o_rl.menu:	rlib.h.sprite
rm_o_rl.menu:	rlib.h.resspr
rm_o_rl.menu:	rlib.h.msgs
rm_o_rl.menu:	rlib.h.verintern.messages
rm_o_rl.msgs:	rlib.c.msgs
rm_o_rl.msgs:	rlib.h.msgs
rm_o_rl.msgs:	C:h.swis
rm_o_rl.msgs:	C:h.kernel
rm_o_rl.msgs:	rlib.h.msgtrans
rm_o_rl.msgs:	rlib.h.res
rm_o_rl.msgs:	rlib.h.os
rm_o_rl.os:	rlib.c.os
rm_o_rl.os:	rlib.h.os
rm_o_rl.os:	C:h.kernel
rm_o_rl.pointer:	rlib.c.pointer
rm_o_rl.pointer:	rlib.h.os
rm_o_rl.pointer:	C:h.kernel
rm_o_rl.pointer:	rlib.h.sprite
rm_o_rl.pointer:	rlib.h.pointer
rm_o_rl.pointer:	rlib.h.wimp
rm_o_rl.poll: rlib.s.poll
rm_o_rl.poll: rlib.s.asmdefs
rm_o_rl.res:	rlib.c.res
rm_o_rl.res:	rlib.h.os
rm_o_rl.res:	C:h.kernel
rm_o_rl.res:	rlib.h.trace
rm_o_rl.res:	rlib.h.werr
rm_o_rl.res:	rlib.h.res
rm_o_rl.resspr:	rlib.c.resspr
rm_o_rl.resspr:	C:h.swis
rm_o_rl.resspr:	C:h.kernel
rm_o_rl.resspr:	rlib.h.sprite
rm_o_rl.resspr:	rlib.h.os
rm_o_rl.resspr:	rlib.h.res
rm_o_rl.resspr:	rlib.h.werr
rm_o_rl.resspr:	rlib.h.msgs
rm_o_rl.resspr:	rlib.h.verintern.messages
rm_o_rl.resspr:	rlib.h.resspr
rm_o_rl.saveas:	rlib.c.saveas
rm_o_rl.saveas:	rlib.h.trace
rm_o_rl.saveas:	rlib.h.os
rm_o_rl.saveas:	C:h.kernel
rm_o_rl.saveas:	rlib.h.bbc
rm_o_rl.saveas:	rlib.h.wimp
rm_o_rl.saveas:	rlib.h.sprite
rm_o_rl.saveas:	rlib.h.wimpt
rm_o_rl.saveas:	rlib.h.win
rm_o_rl.saveas:	rlib.h.dbox
rm_o_rl.saveas:	rlib.h.saveas
rm_o_rl.saveas:	rlib.h.xfersend
rm_o_rl.saveas:	rlib.h.fileicon
rm_o_rl.saveas:	rlib.h.werr
rm_o_rl.saveas:	rlib.h.menu
rm_o_rl.saveas:	rlib.h.event
rm_o_rl.saveas:	rlib.h.msgs
rm_o_rl.saveas:	rlib.h.help
rm_o_rl.saveas:	rlib.h.template
rm_o_rl.saveas:	rlib.h.verintern.messages
rm_o_rl.sprite:	rlib.c.sprite
rm_o_rl.sprite:	rlib.h.os
rm_o_rl.sprite:	C:h.kernel
rm_o_rl.sprite:	rlib.h.sprite
rm_o_rl.swi: rlib.s.swi
rm_o_rl.swi: rlib.s.asmdefs
rm_o_rl.swi: s.h_StrongA
rm_o_rl.template:	rlib.c.template
rm_o_rl.template:	C:h.swis
rm_o_rl.template:	C:h.kernel
rm_o_rl.template:	rlib.h.os
rm_o_rl.template:	rlib.h.wimp
rm_o_rl.template:	rlib.h.sprite
rm_o_rl.template:	rlib.h.wimpt
rm_o_rl.template:	rlib.h.res
rm_o_rl.template:	rlib.h.sprite
rm_o_rl.template:	rlib.h.resspr
rm_o_rl.template:	rlib.h.werr
rm_o_rl.template:	rlib.h.template
rm_o_rl.template:	rlib.h.trace
rm_o_rl.template:	rlib.h.msgs
rm_o_rl.template:	rlib.h.font
rm_o_rl.template:	rlib.h.drawmod
rm_o_rl.template:	rlib.h.verintern.messages
rm_o_rl.txt:	rlib.c.txt
rm_o_rl.txt:	rlib.h.txt
rm_o_rl.txt:	rlib.h.EditIntern.txtundo
rm_o_rl.txt:	rlib.h.EditIntern.txt1
rm_o_rl.txt:	rlib.h.EditIntern.txt3
rm_o_rl.txt:	rlib.h.EditIntern.txtar
rm_o_rl.txt:	rlib.h.werr
rm_o_rl.txt:	rlib.h.trace
rm_o_rl.txt1:	rlib.c.txt1
rm_o_rl.txt1:	rlib.h.trace
rm_o_rl.txt1:	rlib.h.werr
rm_o_rl.txt1:	rlib.h.flex
rm_o_rl.txt1:	rlib.h.msgs
rm_o_rl.txt1:	rlib.h.txt
rm_o_rl.txt1:	rlib.h.EditIntern.txtundo
rm_o_rl.txt1:	rlib.h.EditIntern.txt1
rm_o_rl.txt1:	rlib.h.EditIntern.txt3
rm_o_rl.txt1:	rlib.h.verintern.messages
rm_o_rl.txt3:	rlib.c.txt3
rm_o_rl.txt3:	rlib.h.trace
rm_o_rl.txt3:	rlib.h.werr
rm_o_rl.txt3:	rlib.h.txt
rm_o_rl.txt3:	rlib.h.EditIntern.txtundo
rm_o_rl.txt3:	rlib.h.EditIntern.txt1
rm_o_rl.txt3:	rlib.h.EditIntern.txt3
rm_o_rl.txtar:	rlib.c.txtar
rm_o_rl.txtar:	rlib.h.os
rm_o_rl.txtar:	C:h.kernel
rm_o_rl.txtar:	C:h.swis
rm_o_rl.txtar:	rlib.h.bbc
rm_o_rl.txtar:	rlib.h.dbox
rm_o_rl.txtar:	rlib.h.werr
rm_o_rl.txtar:	rlib.h.akbd
rm_o_rl.txtar:	rlib.h.wimp
rm_o_rl.txtar:	rlib.h.sprite
rm_o_rl.txtar:	rlib.h.wimpt
rm_o_rl.txtar:	rlib.h.font
rm_o_rl.txtar:	rlib.h.drawmod
rm_o_rl.txtar:	rlib.h.trace
rm_o_rl.txtar:	rlib.h.win
rm_o_rl.txtar:	rlib.h.menu
rm_o_rl.txtar:	rlib.h.event
rm_o_rl.txtar:	rlib.h.xferrecv
rm_o_rl.txtar:	rlib.h.visdelay
rm_o_rl.txtar:	rlib.h.msgs
rm_o_rl.txtar:	rlib.h.txt
rm_o_rl.txtar:	rlib.h.EditIntern.txtundo
rm_o_rl.txtar:	rlib.h.EditIntern.txt1
rm_o_rl.txtar:	rlib.h.EditIntern.txt3
rm_o_rl.txtar:	rlib.h.EditIntern.txtar
rm_o_rl.txtar:	rlib.h.txtscrap
rm_o_rl.txtar:	rlib.h.txtopt
rm_o_rl.txtar:	rlib.h.verintern.messages
rm_o_rl.txtedit:	rlib.c.txtedit
rm_o_rl.txtedit:	rlib.h.akbd
rm_o_rl.txtedit:	rlib.h.werr
rm_o_rl.txtedit:	rlib.h.menu
rm_o_rl.txtedit:	rlib.h.os
rm_o_rl.txtedit:	C:h.kernel
rm_o_rl.txtedit:	rlib.h.wimp
rm_o_rl.txtedit:	rlib.h.sprite
rm_o_rl.txtedit:	rlib.h.wimpt
rm_o_rl.txtedit:	rlib.h.txt
rm_o_rl.txtedit:	rlib.h.win
rm_o_rl.txtedit:	rlib.h.txtwin
rm_o_rl.txtedit:	rlib.h.flex
rm_o_rl.txtedit:	rlib.h.txtscrap
rm_o_rl.txtedit:	rlib.h.event
rm_o_rl.txtedit:	rlib.h.txtedit
rm_o_rl.txtedit:	rlib.h.typdat
rm_o_rl.txtedit:	rlib.h.EditIntern.txtfind
rm_o_rl.txtedit:	rlib.h.editintern.txtregexp
rm_o_rl.txtedit:	rlib.h.EditIntern.txtmisc
rm_o_rl.txtedit:	rlib.h.EditIntern.txtundo
rm_o_rl.txtedit:	rlib.h.EditIntern.txtar
rm_o_rl.txtedit:	rlib.h.dboxquery
rm_o_rl.txtedit:	rlib.h.dboxfile
rm_o_rl.txtedit:	rlib.h.trace
rm_o_rl.txtedit:	rlib.h.dbox
rm_o_rl.txtedit:	rlib.h.EditIntern.txtoptmenu
rm_o_rl.txtedit:	rlib.h.xfersend
rm_o_rl.txtedit:	rlib.h.xferrecv
rm_o_rl.txtedit:	rlib.h.saveas
rm_o_rl.txtedit:	rlib.h.typdat
rm_o_rl.txtedit:	rlib.h.fileicon
rm_o_rl.txtedit:	rlib.h.visdelay
rm_o_rl.txtedit:	rlib.h.EditIntern.txtfile
rm_o_rl.txtedit:	rlib.h.EditIntern.message
rm_o_rl.txtedit:	rlib.h.Editintern.txtregexp
rm_o_rl.txtedit:	C:h.swis
rm_o_rl.txtedit:	rlib.h.txtopt
rm_o_rl.txtedit:	rlib.h.msgs
rm_o_rl.txtedit:	rlib.h.help
rm_o_rl.txtedit:	rlib.h.template
rm_o_rl.txtedit:	rlib.h.verintern.messages
rm_o_rl.txtfile:	rlib.c.txtfile
rm_o_rl.txtfile:	rlib.h.os
rm_o_rl.txtfile:	C:h.kernel
rm_o_rl.txtfile:	rlib.h.txt
rm_o_rl.txtfile:	rlib.h.typdat
rm_o_rl.txtfile:	rlib.h.flex
rm_o_rl.txtfile:	C:h.swis
rm_o_rl.txtfile:	rlib.h.wimpt
rm_o_rl.txtfile:	rlib.h.wimp
rm_o_rl.txtfile:	rlib.h.sprite
rm_o_rl.txtfile:	rlib.h.EditIntern.txtundo
rm_o_rl.txtfile:	rlib.h.txtedit
rm_o_rl.txtfile:	rlib.h.menu
rm_o_rl.txtfile:	rlib.h.xfersend
rm_o_rl.txtfile:	rlib.h.xferrecv
rm_o_rl.txtfile:	rlib.h.EditIntern.txtfile
rm_o_rl.txtfile:	rlib.h.trace
rm_o_rl.txtfile:	rlib.h.werr
rm_o_rl.txtfile:	rlib.h.msgs
rm_o_rl.txtfile:	rlib.h.visdelay
rm_o_rl.txtfile:	rlib.h.verintern.messages
rm_o_rl.txtfind:	rlib.c.txtfind
rm_o_rl.txtfind:	rlib.h.werr
rm_o_rl.txtfind:	rlib.h.txt
rm_o_rl.txtfind:	rlib.h.EditIntern.txtregexp
rm_o_rl.txtfind:	rlib.h.EditIntern.txtfind
rm_o_rl.txtfind:	rlib.h.editintern.txtregexp
rm_o_rl.txtfind:	rlib.h.trace
rm_o_rl.txtfind:	rlib.h.msgs
rm_o_rl.txtfind:	rlib.h.visdelay
rm_o_rl.txtfind:	rlib.h.flex
rm_o_rl.txtfind:	rlib.h.verintern.messages
rm_o_rl.txtmisc:	rlib.c.txtmisc
rm_o_rl.txtmisc:	rlib.h.werr
rm_o_rl.txtmisc:	rlib.h.txt
rm_o_rl.txtmisc:	rlib.h.flex
rm_o_rl.txtmisc:	rlib.h.txtscrap
rm_o_rl.txtmisc:	rlib.h.EditIntern.txtmisc
rm_o_rl.txtmisc:	rlib.h.EditIntern.txtundo
rm_o_rl.txtmisc:	rlib.h.trace
rm_o_rl.txtmisc:	rlib.h.msgs
rm_o_rl.txtmisc:	rlib.h.verintern.messages
rm_o_rl.txtoptmenu:	rlib.c.txtoptmenu
rm_o_rl.txtoptmenu:	rlib.h.txt
rm_o_rl.txtoptmenu:	rlib.h.os
rm_o_rl.txtoptmenu:	C:h.kernel
rm_o_rl.txtoptmenu:	rlib.h.wimp
rm_o_rl.txtoptmenu:	rlib.h.sprite
rm_o_rl.txtoptmenu:	rlib.h.wimpt
rm_o_rl.txtoptmenu:	rlib.h.menu
rm_o_rl.txtoptmenu:	rlib.h.EditIntern.txtar
rm_o_rl.txtoptmenu:	rlib.h.dbox
rm_o_rl.txtoptmenu:	rlib.h.event
rm_o_rl.txtoptmenu:	rlib.h.EditIntern.txtoptmenu
rm_o_rl.txtoptmenu:	rlib.h.visdelay
rm_o_rl.txtoptmenu:	rlib.h.font
rm_o_rl.txtoptmenu:	rlib.h.drawmod
rm_o_rl.txtoptmenu:	rlib.h.trace
rm_o_rl.txtoptmenu:	rlib.h.werr
rm_o_rl.txtoptmenu:	rlib.h.colourmenu
rm_o_rl.txtoptmenu:	rlib.h.msgs
rm_o_rl.txtoptmenu:	rlib.h.txtwin
rm_o_rl.txtoptmenu:	rlib.h.verintern.messages
rm_o_rl.txtscrap:	rlib.c.txtscrap
rm_o_rl.txtscrap:	rlib.h.txt
rm_o_rl.txtscrap:	rlib.h.txtscrap
rm_o_rl.txtundo:	rlib.c.txtundo
rm_o_rl.txtundo:	rlib.h.flex
rm_o_rl.txtundo:	rlib.h.trace
rm_o_rl.txtundo:	rlib.h.txt
rm_o_rl.txtundo:	rlib.h.EditIntern.txtundo
rm_o_rl.txtundo:	rlib.h.EditIntern.txt1
rm_o_rl.txtundo:	rlib.h.txtscrap
rm_o_rl.txtundo:	rlib.h.werr
rm_o_rl.txtwin:	rlib.c.txtwin
rm_o_rl.txtwin:	rlib.h.trace
rm_o_rl.txtwin:	rlib.h.os
rm_o_rl.txtwin:	C:h.kernel
rm_o_rl.txtwin:	rlib.h.wimp
rm_o_rl.txtwin:	rlib.h.sprite
rm_o_rl.txtwin:	rlib.h.wimpt
rm_o_rl.txtwin:	rlib.h.win
rm_o_rl.txtwin:	rlib.h.txt
rm_o_rl.txtwin:	rlib.h.EditIntern.txtundo
rm_o_rl.txtwin:	rlib.h.EditIntern.txt1
rm_o_rl.txtwin:	rlib.h.EditIntern.txt3
rm_o_rl.txtwin:	rlib.h.EditIntern.txtar
rm_o_rl.txtwin:	rlib.h.txtwin
rm_o_rl.visdelay:	rlib.c.visdelay
rm_o_rl.visdelay:	rlib.h.os
rm_o_rl.visdelay:	C:h.kernel
rm_o_rl.visdelay:	rlib.h.visdelay
rm_o_rl.werr:	rlib.c.werr
rm_o_rl.werr:	C:h.swis
rm_o_rl.werr:	C:h.kernel
rm_o_rl.werr:	rlib.h.os
rm_o_rl.werr:	rlib.h.wimp
rm_o_rl.werr:	rlib.h.sprite
rm_o_rl.werr:	rlib.h.werr
rm_o_rl.werr:	rlib.h.wimpt
rm_o_rl.wimp:	rlib.c.wimp
rm_o_rl.wimp:	rlib.h.os
rm_o_rl.wimp:	C:h.kernel
rm_o_rl.wimp:	rlib.h.trace
rm_o_rl.wimp:	rlib.h.wimp
rm_o_rl.wimp:	rlib.h.sprite
rm_o_rl.wimpt:	rlib.c.wimpt
rm_o_rl.wimpt:	C:h.swis
rm_o_rl.wimpt:	C:h.kernel
rm_o_rl.wimpt:	rlib.h.akbd
rm_o_rl.wimpt:	rlib.h.os
rm_o_rl.wimpt:	rlib.h.bbc
rm_o_rl.wimpt:	rlib.h.wimp
rm_o_rl.wimpt:	rlib.h.sprite
rm_o_rl.wimpt:	rlib.h.wimpt
rm_o_rl.wimpt:	rlib.h.trace
rm_o_rl.wimpt:	rlib.h.werr
rm_o_rl.wimpt:	rlib.h.alarm
rm_o_rl.wimpt:	rlib.h.event
rm_o_rl.wimpt:	rlib.h.menu
rm_o_rl.wimpt:	rlib.h.msgs
rm_o_rl.wimpt:	rlib.h.win
rm_o_rl.wimpt:	rlib.h.verintern.messages
rm_o_rl.win:	rlib.c.win
rm_o_rl.win:	rlib.h.trace
rm_o_rl.win:	rlib.h.os
rm_o_rl.win:	C:h.kernel
rm_o_rl.win:	rlib.h.wimp
rm_o_rl.win:	rlib.h.sprite
rm_o_rl.win:	rlib.h.werr
rm_o_rl.win:	rlib.h.wimpt
rm_o_rl.win:	rlib.h.event
rm_o_rl.win:	rlib.h.menu
rm_o_rl.win:	rlib.h.msgs
rm_o_rl.win:	rlib.h.verintern.messages
rm_o_rl.win:	rlib.h.win
rm_o_rl.xferrecv:	rlib.c.xferrecv
rm_o_rl.xferrecv:	rlib.h.trace
rm_o_rl.xferrecv:	rlib.h.os
rm_o_rl.xferrecv:	C:h.kernel
rm_o_rl.xferrecv:	rlib.h.bbc
rm_o_rl.xferrecv:	rlib.h.wimp
rm_o_rl.xferrecv:	rlib.h.sprite
rm_o_rl.xferrecv:	rlib.h.wimpt
rm_o_rl.xferrecv:	rlib.h.win
rm_o_rl.xferrecv:	rlib.h.dbox
rm_o_rl.xferrecv:	rlib.h.typdat
rm_o_rl.xferrecv:	rlib.h.xfersend
rm_o_rl.xferrecv:	rlib.h.fileicon
rm_o_rl.xferrecv:	rlib.h.werr
rm_o_rl.xferrecv:	rlib.h.menu
rm_o_rl.xferrecv:	rlib.h.event
rm_o_rl.xferrecv:	rlib.h.xferrecv
rm_o_rl.xferrecv:	rlib.h.msgs
rm_o_rl.xferrecv:	rlib.h.verintern.messages
rm_o_rl.xfersend:	rlib.c.xfersend
rm_o_rl.xfersend:	rlib.h.trace
rm_o_rl.xfersend:	C:h.swis
rm_o_rl.xfersend:	C:h.kernel
rm_o_rl.xfersend:	rlib.h.os
rm_o_rl.xfersend:	rlib.h.bbc
rm_o_rl.xfersend:	rlib.h.wimp
rm_o_rl.xfersend:	rlib.h.sprite
rm_o_rl.xfersend:	rlib.h.wimpt
rm_o_rl.xfersend:	rlib.h.win
rm_o_rl.xfersend:	rlib.h.dbox
rm_o_rl.xfersend:	rlib.h.xfersend
rm_o_rl.xfersend:	rlib.h.fileicon
rm_o_rl.xfersend:	rlib.h.werr
rm_o_rl.xfersend:	rlib.h.menu
rm_o_rl.xfersend:	rlib.h.event
rm_o_rl.xfersend:	rlib.h.msgs
rm_o_rl.xfersend:	rlib.h.dragasprit
rm_o_rl.xfersend:	rlib.h.verintern.messages
rm_o_rl.help:	rlib.c.help
rm_o_rl.help:	rlib.h.os
rm_o_rl.help:	C:h.kernel
rm_o_rl.help:	rlib.h.wimp
rm_o_rl.help:	rlib.h.sprite
rm_o_rl.help:	rlib.h.wimpt
rm_o_rl.help:	rlib.h.werr
rm_o_rl.help:	rlib.h.trace
rm_o_rl.help:	rlib.h.event
rm_o_rl.help:	rlib.h.menu
rm_o_rl.help:	rlib.h.dbox
rm_o_rl.help:	rlib.h.msgs
rm_o_rl.help:	rlib.h.help
rm_o_rl.help:	C:h.swis
rm_o_rl.print:	rlib.c.print
rm_o_rl.print:	rlib.h.os
rm_o_rl.print:	C:h.kernel
rm_o_rl.print:	rlib.h.print
rm_o_rl.txtopt:	rlib.c.txtopt
rm_o_rl.txtopt:	rlib.h.msgs
rm_o_rl.txtopt:	rlib.h.werr
rm_o_rl.txtopt:	rlib.h.txtopt
rm_o_rl.txtopt:	rlib.h.verintern.messages
rm_o_rl.txtregexp:	rlib.c.txtregexp
rm_o_rl.txtregexp:	rlib.h.EditIntern.txtregexp
rm_o_rl.txtregexp:	rlib.h.txt
rm_o_rl.txtregexp:	rlib.h.verintern.messages
rm_o_rl.txtregexp:	rlib.h.msgs
rm_o_rl.txtregexp:	rlib.h.txt
rm_o_rl.txtregexp:	rlib.h.werr
rm_o_rl.rl_spare: rlib.s.rl_spare
o.a_abssym: s.a_abssym
o.c_abssym: s.c_abssym
o.abssym: s.abssym
