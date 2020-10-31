
#makefile for floppy install


RM      = remove
MKDIR   = cdir
CP      = copy
WIPE    = -wipe
ATTR    = -attr

CPFLAGS = ~cfr~v
WFLAGS  = ~cfr~v

instfiles = \
   Installer.!Installer.!Boot\
   Installer.!Installer.!Help\
   Installer.!Installer.!Run\
   Installer.!Installer.!RunImage\
   Installer.!Installer.!Sprites\
   Installer.!Installer.!Sprites22\
   Installer.!Installer.Messages\
   Installer.!Installer.Modules.TinyStubs\
   Installer.!Installer.Modules.Toolbox\
   Installer.!Installer.Modules.Window\
   Installer.!Installer.Res

flop1files = \
   $(instfiles)\
   Archiver.arcs.arc01\
   Installer.Resources.!!ReadMe\
   Installer.Resources.AppNote

flop2files = \
   Archiver.arcs.arc02

flop3files = \
   Archiver.arcs.arc03


install: $(flop1files) $(flop2files) $(flop3files)
        ${CP} Installer.!Installer Floppy01.!Installer ${CPFLAGS}
        ${CP} Archiver.arcs.arc01 Floppy01.!Installer.arc01 ${CPFLAGS}
        ${CP} Installer.Resources.!!ReadMe Floppy01.!!ReadMe ${CPFLAGS}
        ${CP} Installer.Resources.AppNote Floppy01.AppNote ${CPFLAGS}
        ${ATTR} -directories +ol +or -ow -ww Floppy01
        ${ATTR} -files +ol +or -ow -ww Floppy01
        ${CP} Archiver.arcs.arc02 Floppy02.arc02 ${CPFLAGS}
        ${ATTR} -files +ol +or -ow -ww Floppy02
        ${CP} Archiver.arcs.arc03 Floppy03.arc03 ${CPFLAGS}
        ${ATTR} -files +ol +or -ow -ww Floppy03
        @echo floppy install built

clean:
        ${WIPE} Floppy01.* ${WFLAGS}
        ${WIPE} Floppy02.* ${WFLAGS}
        ${WIPE} Floppy03.* ${WFLAGS}
        @echo floppy install cleaned
