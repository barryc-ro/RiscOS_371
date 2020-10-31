
#makefile for Archiver

CCflags = -c -depend !Depend -IC: -ff
Linkflags = -aif -o $@
Squeezeflags = -o $@
RM = remove

all: arc arcs.arcspec arcs.arc01
        @echo archives all built

arcs.arc01: arc arcs.arcspec
        arc arcs.arcspec > arcs.arcstats
        type arcs.arcstats

arc: o.arc
        link $(linkflags) o.arc C:o.Stubs

clean:
        ${RM} arc
        ${RM} o.arc
        ${RM} arcs.arc01
        ${RM} arcs.arc02
        ${RM} arcs.arc03
        ${RM} arcs.arcstats
        @echo archives cleaned

o.arc:   c.arc
        cc $(ccflags) -o o.arc c.arc


# Dynamic dependencies:
o.arc:	c.arc
o.arc:	C:h.swis
o.arc:	C:h.kernel
