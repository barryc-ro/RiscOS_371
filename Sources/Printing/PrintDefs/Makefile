# Makefile for Printer Definition files (PrintDefs)
#


# Generic options:
#
MKDIR   = cdir
CP      = copy
RM      = remove
WIPE    = -wipe

CPFLAGS = ~cfr~v
WFLAGS  = ~c~v


#
# Main rules:
#

install: Version
        echo copy papers and feeds...
        ${MKDIR}                             ${INSTDIR}.^.!Boot
        ${MKDIR}                             ${INSTDIR}.^.!Boot.Choices
        ${MKDIR}                             ${INSTDIR}.^.!Boot.Choices.Printers
        ${MKDIR}                             ${INSTDIR}.^.!Boot.Choices.Printers.ps
        ${CP} Feeds                          ${INSTDIR}.^.!Boot.Choices.Printers.ps.Feeds ${CPFLAGS}
        ${CP} Paper                          ${INSTDIR}.^.!Boot.Choices.Printers.ps.Paper ${CPFLAGS}
        -attr -directories +wr ${INSTDIR}.^.!Boot.Choices.Printers
        -attr -files +or +ow +wr -ww ${INSTDIR}.^.!Boot.Choices.Printers
        ${MKDIR}                             ${INSTDIR}.^.Utilities
        ${MKDIR}                             ${INSTDIR}.^.Utilities.!ResetBoot
        ${MKDIR}                             ${INSTDIR}.^.Utilities.!ResetBoot.Choices
        ${MKDIR}                             ${INSTDIR}.^.Utilities.!ResetBoot.Choices.Printers
        ${MKDIR}                             ${INSTDIR}.^.Utilities.!ResetBoot.Choices.Printers.ps
        ${CP} Feeds                          ${INSTDIR}.^.Utilities.!ResetBoot.Choices.Printers.ps.Feeds ${CPFLAGS}
        ${CP} Paper                          ${INSTDIR}.^.Utilities.!ResetBoot.Choices.Printers.ps.Paper ${CPFLAGS}
        -attr -directories +wr ${INSTDIR}.^.Utilities.!ResetBoot.Choices.Printers
        -attr -files +or +ow +wr -ww ${INSTDIR}.^.Utilities.!ResetBoot.Choices.Printers
        echo copy Printers ...
        ${CP} Printers                       ${INSTDIR}.Printers          ${CPFLAGS}
        ${CP} Version                        ${INSTDIR}.Printers.Version  ${CPFLAGS}
        -attr -directories +wr ${INSTDIR}.Printers
        -attr -files +ol +or -ow +wr -ww ${INSTDIR}.Printers
        @echo ${COMPONENT}: All installed {Disc}


clean:
        @echo ${COMPONENT}: cleaned

#---------------------------------------------------------------------------
# Dynamic dependencies:
