
#makefile for !Installer

CCflags = -c -depend !Depend -I@.loclibs.tboxlibs -ff
Linkflags = -aif -o $@
Squeezeflags = -o $@
RM = remove

@.!Installer.!RunImage:   @.!RunImageU 
        squeeze $(squeezeflags) @.!RunImageU 

@.!RunImageU:   @.o.gui @.o.main @.o.unarc @.o.utils \
        C:o.Stubs @.loclibs.tboxlibs.o.eventlib @.loclibs.tboxlibs.o.toolboxlib @.loclibs.tboxlibs.o.wimplib 
        link $(linkflags) @.o.gui @.o.main @.o.unarc @.o.utils \
        C:o.Stubs @.loclibs.tboxlibs.o.eventlib @.loclibs.tboxlibs.o.toolboxlib @.loclibs.tboxlibs.o.wimplib 

clean:
        ${RM} @.!Installer.!RunImage
        ${RM} @.!RunImageU
        ${RM} @.o.gui
        ${RM} @.o.main
        ${RM} @.o.unarc
        ${RM} @.o.utils
        @echo Installer cleaned

@.o.gui:   @.c.gui
        cc $(ccflags) -o @.o.gui @.c.gui 
@.o.main:   @.c.main
        cc $(ccflags) -o @.o.main @.c.main 
@.o.unarc:   @.c.unarc
        cc $(ccflags) -o @.o.unarc @.c.unarc 
@.o.utils:   @.c.utils
        cc $(ccflags) -o @.o.utils @.c.utils 


# Dynamic dependencies:
o.gui:	c.gui
o.gui:	C:h.kernel
o.gui:	C:h.swis
o.gui:	loclibs.tboxlibs.h.wimp
o.gui:	loclibs.tboxlibs.h.wimplib
o.gui:	loclibs.tboxlibs.h.toolbox
o.gui:	loclibs.tboxlibs.h.gadgets
o.gui:	loclibs.tboxlibs.h.event
o.gui:	loclibs.tboxlibs.h.window
o.gui:	h.main
o.gui:	h.params
o.gui:	h.utils
o.gui:	h.gui
o.gui:	h.unarc
o.main:	c.main
o.main:	C:h.kernel
o.main:	h.main
o.main:	h.params
o.main:	h.utils
o.main:	h.gui
o.unarc:	c.unarc
o.unarc:	C:h.swis
o.unarc:	C:h.kernel
o.unarc:	h.unarc
o.utils:	c.utils
o.utils:	C:h.kernel
o.utils:	C:h.swis
o.utils:	h.main
o.utils:	h.params
o.utils:	h.utils
o.utils:	h.gui
o.utils:	h.discspec
