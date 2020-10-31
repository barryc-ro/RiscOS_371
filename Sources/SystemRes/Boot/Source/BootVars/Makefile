VPATH = @ <Support$Dir>

CC     = cc410 -D__swi -IOS:,Support: -fafh -wp
LINK   = Link

LIBS  = OSLib:o.OSLib CLib:o.ANSILib

OBJS = o.main o.x

BootVars: ${OBJS}
   ${LINK} -output BootVars ${OBJS} ${LIBS}

#General rules
.SUFFIXES:      .cmhg .h .c .debug .o .oSA .Resources .s .asm .i .def
.c.o:;          ${CC} ${THROWBACK} -depend !Depend -c ${ZM} -ff -o $@ $<
.c.oSA:;        ${CC} ${THROWBACK} -depend !Depend -c ${ZM} -ff -DSTANDALONE -o $@ $<
.c.debug:;      ${CC} ${THROWBACK} -depend !Depend -c ${ZM} -DTRACE=1 -o $@ $<
.c.i:;          ${CC} -E -C $< > $@
.c.s:;          ${CC} ${ZM} -S -ff $<
.cmhg.o:;       ${CMHG} $< $@
.Resources.o .Resources.debug:
                ResGen $* $@ $< Resources.DrawFile.$*
.asm.o:;        ${OBJASM} $< $@
.asm.debug:;    ${OBJASM} $< $@
.def.h:;        DefMod -h < $< > $@
.def.s:;        DefMod -s < $< > $@
.def.o:;        DefMod -l -o l.$* < $<
                LibFile -c -o $@ -via ViaFile
                Wipe l.$* ~C~FR~V

#------------------------------------------------------------------------
# Dynamic dependencies:
o.x:	<Support$Dir>.c.x
o.x:	C:h.kernel
o.x:	C:h.swis
o.x:	OS:h.macros
o.x:	OS:h.os
o.x:	OS:h.types
o.x:	<Support$Dir>.h.x
o.main:	c.main
o.main:	C:h.swis
o.main:	C:h.kernel
o.main:	Support:h.trace
o.main:	OS:h.os
o.main:	OS:h.types
o.main:	Support:h.x
o.main:	OS:h.econet
o.main:	OS:h.netfs
o.main:	OS:h.fileswitch
o.main:	OS:h.macros
o.main:	OS:h.os
o.main:	OS:h.osbyte
o.main:	OS:h.osfscontrol
o.main:	OS:h.osmodule
o.main:	OS:h.socket
o.main:	OS:h.wimpreadsysinfo
o.main:	OS:h.wimp
o.main:	OS:h.osspriteop
o.main:	OS:h.font
