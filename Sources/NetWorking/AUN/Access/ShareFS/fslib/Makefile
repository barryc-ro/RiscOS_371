# -*-Text-*-
#
# $Header: /ax/networking:Starling/ShareFS/fslib/Makefile:networking  1.3  $
# $Source: /ax/networking:Starling/ShareFS/fslib/Makefile: $
#
# Copyright (c) 1995 Acorn Computers Ltd., Cambridge, England
#
# Makefile for Freeway module
#
# $Log: Makefile,v $
# Revision 1.3  95/01/09  14:13:24  kwelton
# Added ifswrap.c into the list of C source files, remade dependencies
# (again).
# 
# Revision 1.2  95/01/09  13:40:01  kwelton
# Now use system versions of "kernel.h" and "swis.h", "_swis.h" no longer
# exists - remade dependencies.
# 
# Revision 1.1  95/01/04  19:18:55  kwelton
# Initial revision
# 
#
# Manually adapted for use under RISC iX
#

CC=             cc
AS=             objasm ${ASFLAGS}
LIB=            libfile
RM=             remove
WIPE=           -wipe
CPFLAGS=        ~cfr~v
WFLAGS=         ~c~v

CFLAGS=         -zM -zps1 -ffah -IC: ${DFLAGS}
DFLAGS=         -DLOOKUPERR
ASFLAGS=        -IHdr:Global.,Hdr:Interface. -Stamp -quit

CFILES=         _Args.c _Close.c _File.c _Func.c _Free.c _GBPB.c \
                _GetBytes.c _Open.c _PutBytes.c command.c debug.c \
                esc.c fixsf.c fswrap.c ifswrap.c leaf.c lookup.c \
                noimage.c privw.c readwidth.c stricmp.c strins.c \
                stampinfo.c ticker.c visdelay.c ukerrs.c

FSOBJS=         _Args.o _Close.o _File.o _Func.o _GBPB.o command.o \
                _GetBytes.o _Open.o _PutBytes.o Interface.o _Free.o \
                cstart.o ticker.o dropper.o privw.o

FSOBJS1=        stricmp.o strins.o readwidth.o stampinfo.o esc.o \
                debug.o noimage.o fixsf.o callcnpv.o callinsv.o callmore.o \
                callremv.o visdelay.o fswrap.o lookup.o robase.o asw.o \
                fwupcall.o leaf.o

IMOBJS=         Imterface.o ifswrap.o

#
# Rule patterns
#
.c.o:;      ${CC} -depend !Depend -c ${CFLAGS} -o $@ $<
.s.o:;      ${AS} -depend !Depend ${AFLAGS} $< $@

all:            fslib.o imlib.o ukerrs.o

fslib.o:        ${FSOBJS} ${FSOBJS1}
                ${LIB} -co $@ ${FSOBJS}
                ${LIB} -io $@ ${FSOBJS1}

clean:
        ${WIPE} o.* ${WFLAGS}
#---------------------------------------------------------------------------
# Dynamic dependencies:
o._Args:	c._Args
o._Args:	h.FS
o._Args:	h.ker
o._Args:	C:h.kernel
o._Args:	C:h.swis
o._Args:	h.interface
o._Args:	h.ModuleWrap
o._Args:	C:h.kernel
o._Args:	h.util
o._Args:	h.lookup
o._Args:	h.fscore
o._Args:	h.lookup
o._Args:	h.RO3ONLY
o._Close:	c._Close
o._Close:	h.FS
o._Close:	h.ker
o._Close:	C:h.kernel
o._Close:	C:h.swis
o._Close:	h.interface
o._Close:	h.ModuleWrap
o._Close:	C:h.kernel
o._Close:	h.util
o._Close:	h.lookup
o._Close:	h.fscore
o._Close:	h.lookup
o._File:	c._File
o._File:	h.FS
o._File:	h.ker
o._File:	C:h.kernel
o._File:	C:h.swis
o._File:	h.interface
o._File:	h.ModuleWrap
o._File:	C:h.kernel
o._File:	h.util
o._File:	h.lookup
o._File:	h.fscore
o._File:	h.lookup
o._Func:	c._Func
o._Func:	h.FS
o._Func:	h.ker
o._Func:	C:h.kernel
o._Func:	C:h.swis
o._Func:	h.interface
o._Func:	h.ModuleWrap
o._Func:	C:h.kernel
o._Func:	h.util
o._Func:	h.lookup
o._Func:	h.fscore
o._Func:	h.lookup
o._Func:	h.RO3ONLY
o._GBPB:	c._GBPB
o._GBPB:	h.FS
o._GBPB:	h.ker
o._GBPB:	C:h.kernel
o._GBPB:	C:h.swis
o._GBPB:	h.interface
o._GBPB:	h.ModuleWrap
o._GBPB:	C:h.kernel
o._GBPB:	h.util
o._GBPB:	h.lookup
o._GBPB:	h.fscore
o._GBPB:	h.lookup
o._GBPB:	h.RO3ONLY
o.command:	c.command
o.command:	C:h.kernel
o.command:	h.ModuleWrap
o.command:	C:h.kernel
o._GetBytes:	c._GetBytes
o._GetBytes:	h.FS
o._GetBytes:	h.ker
o._GetBytes:	C:h.kernel
o._GetBytes:	C:h.swis
o._GetBytes:	h.interface
o._GetBytes:	h.ModuleWrap
o._GetBytes:	C:h.kernel
o._GetBytes:	h.util
o._GetBytes:	h.lookup
o._GetBytes:	h.fscore
o._GetBytes:	h.lookup
o._GetBytes:	h.RO3ONLY
o._Open:	c._Open
o._Open:	h.FS
o._Open:	h.ker
o._Open:	C:h.kernel
o._Open:	C:h.swis
o._Open:	h.interface
o._Open:	h.ModuleWrap
o._Open:	C:h.kernel
o._Open:	h.util
o._Open:	h.lookup
o._Open:	h.fscore
o._Open:	h.lookup
o._Open:	h.RO3ONLY
o._PutBytes:	c._PutBytes
o._PutBytes:	h.FS
o._PutBytes:	h.ker
o._PutBytes:	C:h.kernel
o._PutBytes:	C:h.swis
o._PutBytes:	h.interface
o._PutBytes:	h.ModuleWrap
o._PutBytes:	C:h.kernel
o._PutBytes:	h.util
o._PutBytes:	h.lookup
o._PutBytes:	h.fscore
o._PutBytes:	h.lookup
o._PutBytes:	h.RO3ONLY
o.Interface: s.Interface
o._Free:	c._Free
o._Free:	h.FS
o._Free:	h.ker
o._Free:	C:h.kernel
o._Free:	C:h.swis
o._Free:	h.interface
o._Free:	h.ModuleWrap
o._Free:	C:h.kernel
o._Free:	h.util
o._Free:	h.lookup
o._Free:	h.fscore
o._Free:	h.lookup
o.cstart: s.cstart
o.ticker:	c.ticker
o.ticker:	C:h.kernel
o.ticker:	C:h.swis
o.ticker:	h.ModuleWrap
o.ticker:	C:h.kernel
o.ticker:	h.ticker
o.dropper: s.dropper
o.privw:	c.privw
o.privw:	h.ModuleWrap
o.privw:	C:h.kernel
o.stricmp:	c.stricmp
o.stricmp:	h.util
o.stricmp:	h.interface
o.stricmp:	C:h.kernel
o.stricmp:	h.lookup
o.strins:	c.strins
o.strins:	h.util
o.strins:	h.interface
o.strins:	C:h.kernel
o.strins:	h.lookup
o.readwidth:	c.readwidth
o.readwidth:	h.util
o.readwidth:	h.interface
o.readwidth:	C:h.kernel
o.readwidth:	h.lookup
o.readwidth:	C:h.swis
o.stampinfo:	c.stampinfo
o.stampinfo:	C:h.swis
o.stampinfo:	C:h.kernel
o.stampinfo:	h.interface
o.stampinfo:	h.util
o.stampinfo:	h.lookup
o.esc:	c.esc
o.esc:	C:h.kernel
o.esc:	h.esc
o.esc:	h.evil
o.esc:	C:h.swis
o.esc:	h.util
o.esc:	h.interface
o.esc:	h.lookup
o.debug:	c.debug
o.debug:	h.debug
o.noimage:	c.noimage
o.noimage:	h.ifscore
o.noimage:	C:h.kernel
o.fixsf:	c.fixsf
o.fixsf:	h.util
o.fixsf:	h.interface
o.fixsf:	C:h.kernel
o.fixsf:	h.lookup
o.callcnpv: s.callcnpv
o.callinsv: s.callinsv
o.callmore: s.callmore
o.callremv: s.callremv
o.visdelay:	c.visdelay
o.visdelay:	C:h.swis
o.visdelay:	C:h.kernel
o.visdelay:	h.visdelay
o.fswrap:	c.fswrap
o.fswrap:	h.FS
o.fswrap:	h.ker
o.fswrap:	C:h.kernel
o.fswrap:	C:h.swis
o.fswrap:	h.interface
o.fswrap:	h.ModuleWrap
o.fswrap:	C:h.kernel
o.fswrap:	h.util
o.fswrap:	h.lookup
o.fswrap:	h.fscore
o.fswrap:	h.lookup
o.lookup:	c.lookup
o.lookup:	C:h.kernel
o.lookup:	C:h.swis
o.lookup:	h.lookup
o.robase: s.robase
o.asw: s.asw
o.asw: Hdr:ListOpts
o.asw: Hdr:CPU.Generic26
o.asw: Hdr:Macros
o.asw: Hdr:SWIs
o.asw: Hdr:RISCOS
o.fwupcall: s.fwupcall
o.leaf:	c.leaf
o.leaf:	h.util
o.leaf:	h.interface
o.leaf:	C:h.kernel
o.leaf:	h.lookup
