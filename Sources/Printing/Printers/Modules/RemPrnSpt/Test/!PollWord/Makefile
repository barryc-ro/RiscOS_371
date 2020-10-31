# Project:   PollTest


# Toolflags:
CCflags = -c -depend !Depend -throwback -IC: -DDEBUG
Linkflags = -o $@
ObjAsmflags = -depend !Depend -ThrowBack -Stamp -quit -CloseExec
CMHGflags = 
LibFileflags = -c -o $@
Squeezeflags = -o $@
AAsmflags = -depend !Depend -quit -CloseExec -To $@ -From


# Final targets:
@.!RunImage:   @.o.Debug @.o.WimpTask SCSI::Raptor.$.!DDE.Clib.o.Stubs 
        link $(linkflags) @.o.Debug @.o.WimpTask \
        SCSI::Raptor.$.!DDE.Clib.o.Stubs 


# User-editable dependencies:

# Static dependencies:
@.o.Debug:   @.c.Debug
        cc $(ccflags) -o @.o.Debug @.c.Debug 
@.o.WimpTask:   @.c.WimpTask
        cc $(ccflags) -o @.o.WimpTask @.c.WimpTask 


# Dynamic dependencies:
o.Debug:	c.Debug
o.Debug:	C:h.swis
o.Debug:	C:h.kernel
o.WimpTask:	c.WimpTask
o.WimpTask:	C:h.kernel
o.WimpTask:	C:h.swis
o.WimpTask:	h.WimpTask
o.WimpTask:	h.debug
