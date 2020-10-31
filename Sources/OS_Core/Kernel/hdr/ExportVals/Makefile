# Makefile for ExportVals
#

#
# Generic options:
#
MKDIR   = cdir
AS      = aasm
CP      = copy
RM      = remove
CCFLAGS = -c -depend !Depend -IC:
ASFLAGS = -Stamp -quit
CPFLAGS = ~cfr~v


#
# Generic rules:
#
all:
        ${AS} ${ASFLAGS} -To null: -From s.GetVals { > values }
        settype values text
        @echo ok

# Dynamic dependencies:
