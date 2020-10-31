# System Makefile

CD      = dir
MKDIR   = cdir
SYSDIR  = <build$dir>.System
SRCDIR  = <src$dir>
INSTDIR = <discinstall$dir>
RESDIR  = <resource$dir>.Resources
MAKE    = @amu ${MFLAGS} RESDIR=${RESDIR}

BUILD = \
 AREncode \
 AudioDemos \
 Tutorials \
 Sounds \
 Videos \
 Images \
 SlideShow \
 PrintDefs \
 PrintEdit \
 FontPrint \
 Verify \
 T1ToFont \
 SaveCMOS \
 TCP/IP \
 SparkFS \
 SSound \
 SCSIDM \
 CallASWI \
 ansilib \
 Patch \
 Access+ \
 HForm \
 PhotoView \
 CDPlayer \
 SpriteExtend \
 ChangeFSI \
 ShowScrap \
 Calibrate \
 ArtWorks \
 Puzzle \
 Player \
 Patience \
 MineHunt \
 Meteors \
 MemNow \
 Flasher \
 Clock \
 Blocks \
 Diversions \
 Squash \
 SciCalc \
 Maestro \
 CloseUp \
 Bookworm \
 ARPlayer \
 ResetBoot \
 Repeat \
 Public \
 PhotoCD \
 NetI \
 Drivers \
 JCompMod \
 BASIC64 \
 System \
 Scrap \
 Internet \
 InetSetup \
 Fonts \
 FontMerge \
 Configure \
 ARMovie \
 PartNumber \
 Boot

EXPORT =

RESOURCE =

#
# Build rules:
#
clean: ${BUILD}
        @echo clean: Complete

export: ${EXPORT} ${BUILD}
        @echo export: Complete

# disc build
all: ${BUILD}
        @echo all: Complete

install: ${BUILD}
        @echo install: Complete

#
# Component rules:
#

Boot:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.HardDisc4
        @Access ${INSTDIR}.HardDisc4 /r
        @${CD} ${SRCDIR}.SystemRes.Boot
        ${MAKE} INSTDIR=${INSTDIR}.HardDisc4 COMPONENT=Boot

PartNumber:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.HardDisc4
        @Access ${INSTDIR}.HardDisc4 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.!Boot
        @Access ${INSTDIR}.HardDisc4.!Boot /r
        @${CD} ${SRCDIR}.SystemRes.PartNumber
        ${MAKE} INSTDIR=${INSTDIR}.HardDisc4.!Boot PART=HardDisc

ARMovie:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.HardDisc4
        @Access ${INSTDIR}.HardDisc4 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.!Boot
        @Access ${INSTDIR}.HardDisc4.!Boot /r
        @${MKDIR} ${INSTDIR}.HardDisc4.!Boot.Resources
        @Access ${INSTDIR}.HardDisc4.!Boot.Resources /r
        @${CD} ${SRCDIR}.SystemRes.ARMovie
        ${MAKE} INSTDIR=${INSTDIR}.HardDisc4.!Boot.Resources 

Configure:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.HardDisc4
        @Access ${INSTDIR}.HardDisc4 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.!Boot
        @Access ${INSTDIR}.HardDisc4.!Boot /r
        @${MKDIR} ${INSTDIR}.HardDisc4.!Boot.Resources
        @Access ${INSTDIR}.HardDisc4.!Boot.Resources /r
        @${CD} ${SRCDIR}.SystemRes.Configure
        ${MAKE} INSTDIR=${INSTDIR}.HardDisc4.!Boot.Resources COMPONENT=Configure

FontMerge:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.HardDisc4
        @Access ${INSTDIR}.HardDisc4 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.!Boot
        @Access ${INSTDIR}.HardDisc4.!Boot /r
        @${MKDIR} ${INSTDIR}.HardDisc4.!Boot.Library
        @Access ${INSTDIR}.HardDisc4.!Boot.Library /r
        @${CD} ${SRCDIR}.SystemRes.Configure
        ${MAKE} INSTDIR=${INSTDIR}.HardDisc4.!Boot.Library COMPONENT=FontMerge

Fonts:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.HardDisc4
        @Access ${INSTDIR}.HardDisc4 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.!Boot
        @Access ${INSTDIR}.HardDisc4.!Boot /r
        @${MKDIR} ${INSTDIR}.HardDisc4.!Boot.Resources
        @Access ${INSTDIR}.HardDisc4.!Boot.Resources /r
        @${CD} ${SRCDIR}.SystemRes.Fonts
        ${MAKE} INSTDIR=${INSTDIR}.HardDisc4.!Boot.Resources INSTFLAG=all

InetSetup:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.HardDisc4
        @Access ${INSTDIR}.HardDisc4 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.!Boot
        @Access ${INSTDIR}.HardDisc4.!Boot /r
        @${MKDIR} ${INSTDIR}.HardDisc4.!Boot.Resources
        @Access ${INSTDIR}.HardDisc4.!Boot.Resources /r
        @${CD} ${SRCDIR}.SystemRes.InetSetup
        ${MAKE} INSTDIR=${INSTDIR}.HardDisc4.!Boot.Resources 

Internet:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.HardDisc4
        @Access ${INSTDIR}.HardDisc4 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.!Boot
        @Access ${INSTDIR}.HardDisc4.!Boot /r
        @${MKDIR} ${INSTDIR}.HardDisc4.!Boot.Resources
        @Access ${INSTDIR}.HardDisc4.!Boot.Resources /r
        @${CD} ${SRCDIR}.SystemRes.Internet
        ${MAKE} INSTDIR=${INSTDIR}.HardDisc4.!Boot.Resources 

Scrap:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.HardDisc4
        @Access ${INSTDIR}.HardDisc4 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.!Boot
        @Access ${INSTDIR}.HardDisc4.!Boot /r
        @${MKDIR} ${INSTDIR}.HardDisc4.!Boot.Resources
        @Access ${INSTDIR}.HardDisc4.!Boot.Resources /r
        @${CD} ${SRCDIR}.SystemRes.Scrap
        ${MAKE} INSTDIR=${INSTDIR}.HardDisc4.!Boot.Resources 

System:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.HardDisc4
        @Access ${INSTDIR}.HardDisc4 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.!Boot
        @Access ${INSTDIR}.HardDisc4.!Boot /r
        @${MKDIR} ${INSTDIR}.HardDisc4.!Boot.Resources
        @Access ${INSTDIR}.HardDisc4.!Boot.Resources /r
        @${CD} ${SRCDIR}.SystemRes.System
        ${MAKE} INSTDIR=${INSTDIR}.HardDisc4.!Boot.Resources 

BASIC64:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.HardDisc4
        @Access ${INSTDIR}.HardDisc4 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.!Boot
        @Access ${INSTDIR}.HardDisc4.!Boot /r
        @${MKDIR} ${INSTDIR}.HardDisc4.!Boot.Resources
        @Access ${INSTDIR}.HardDisc4.!Boot.Resources /r
        @${MKDIR} ${INSTDIR}.HardDisc4.!Boot.Resources.!System
        @Access ${INSTDIR}.HardDisc4.!Boot.Resources.!System /r
        @${MKDIR} ${INSTDIR}.HardDisc4.!Boot.Resources.!System.350
        @Access ${INSTDIR}.HardDisc4.!Boot.Resources.!System.350 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.!Boot.Resources.!System.350.Modules
        @Access ${INSTDIR}.HardDisc4.!Boot.Resources.!System.350.Modules /r
        @${CD} ${SRCDIR}.Programmer.BASIC
        ${MAKE} INSTDIR=${INSTDIR}.HardDisc4.!Boot.Resources.!System.350.Modules 

JCompMod:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.HardDisc4
        @Access ${INSTDIR}.HardDisc4 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.!Boot
        @Access ${INSTDIR}.HardDisc4.!Boot /r
        @${MKDIR} ${INSTDIR}.HardDisc4.!Boot.Resources
        @Access ${INSTDIR}.HardDisc4.!Boot.Resources /r
        @${MKDIR} ${INSTDIR}.HardDisc4.!Boot.Resources.!System
        @Access ${INSTDIR}.HardDisc4.!Boot.Resources.!System /r
        @${MKDIR} ${INSTDIR}.HardDisc4.!Boot.Resources.!System.350
        @Access ${INSTDIR}.HardDisc4.!Boot.Resources.!System.350 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.!Boot.Resources.!System.350.Modules
        @Access ${INSTDIR}.HardDisc4.!Boot.Resources.!System.350.Modules /r
        @${CD} ${SRCDIR}.OS_Core.Video.Render.jcompmod
        ${MAKE} INSTDIR=${INSTDIR}.HardDisc4.!Boot.Resources.!System.350.Modules 

Drivers:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.HardDisc4
        @Access ${INSTDIR}.HardDisc4 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.!Boot
        @Access ${INSTDIR}.HardDisc4.!Boot /r
        @${MKDIR} ${INSTDIR}.HardDisc4.!Boot.Resources
        @Access ${INSTDIR}.HardDisc4.!Boot.Resources /r
        @${MKDIR} ${INSTDIR}.HardDisc4.!Boot.Resources.!System
        @Access ${INSTDIR}.HardDisc4.!Boot.Resources.!System /r
        @${MKDIR} ${INSTDIR}.HardDisc4.!Boot.Resources.!System.310
        @Access ${INSTDIR}.HardDisc4.!Boot.Resources.!System.310 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.!Boot.Resources.!System.310.Modules
        @Access ${INSTDIR}.HardDisc4.!Boot.Resources.!System.310.Modules /r
        @${CD} ${SRCDIR}.NetWorking.AUN.Drivers
        ${MAKE} INSTDIR=${INSTDIR}.HardDisc4.!Boot.Resources.!System.310.Modules 

NetI:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.HardDisc4
        @Access ${INSTDIR}.HardDisc4 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.!Boot
        @Access ${INSTDIR}.HardDisc4.!Boot /r
        @${MKDIR} ${INSTDIR}.HardDisc4.!Boot.Resources
        @Access ${INSTDIR}.HardDisc4.!Boot.Resources /r
        @${MKDIR} ${INSTDIR}.HardDisc4.!Boot.Resources.!System
        @Access ${INSTDIR}.HardDisc4.!Boot.Resources.!System /r
        @${MKDIR} ${INSTDIR}.HardDisc4.!Boot.Resources.!System.370
        @Access ${INSTDIR}.HardDisc4.!Boot.Resources.!System.370 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.!Boot.Resources.!System.370.Modules
        @Access ${INSTDIR}.HardDisc4.!Boot.Resources.!System.370.Modules /r
        @${MKDIR} ${INSTDIR}.HardDisc4.!Boot.Resources.!System.370.Modules.Network
        @Access ${INSTDIR}.HardDisc4.!Boot.Resources.!System.370.Modules.Network /r
        @${CD} ${SRCDIR}.NetWorking.AUN.Net
        ${MAKE} INSTDIR=${INSTDIR}.HardDisc4.!Boot.Resources.!System.370.Modules.Network 

PhotoCD:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.HardDisc4
        @Access ${INSTDIR}.HardDisc4 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.!Boot
        @Access ${INSTDIR}.HardDisc4.!Boot /r
        @${MKDIR} ${INSTDIR}.HardDisc4.!Boot.Resources
        @Access ${INSTDIR}.HardDisc4.!Boot.Resources /r
        @${MKDIR} ${INSTDIR}.HardDisc4.!Boot.Resources.!System
        @Access ${INSTDIR}.HardDisc4.!Boot.Resources.!System /r
        @${MKDIR} ${INSTDIR}.HardDisc4.!Boot.Resources.!System.300
        @Access ${INSTDIR}.HardDisc4.!Boot.Resources.!System.300 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.!Boot.Resources.!System.300.Modules
        @Access ${INSTDIR}.HardDisc4.!Boot.Resources.!System.300.Modules /r
        @${CD} ${SRCDIR}.Apps.PhotoView
        ${MAKE} INSTDIR=${INSTDIR}.HardDisc4.!Boot.Resources.!System.300.Modules COMPONENT=PhotoCD

Public:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.HardDisc4
        @Access ${INSTDIR}.HardDisc4 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.Public
        @Access ${INSTDIR}.HardDisc4.Public /r
        @${CD} ${SRCDIR}.SystemRes.Public
        ${MAKE} INSTDIR=${INSTDIR}.HardDisc4.Public 

Repeat:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.HardDisc4
        @Access ${INSTDIR}.HardDisc4 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.!Boot
        @Access ${INSTDIR}.HardDisc4.!Boot /r
        @${MKDIR} ${INSTDIR}.HardDisc4.!Boot.Library
        @Access ${INSTDIR}.HardDisc4.!Boot.Library /r
        @${CD} ${SRCDIR}.OS_Core.BootCmds
        ${MAKE} INSTDIR=${INSTDIR}.HardDisc4.!Boot.Library COMPONENT=Repeat

ResetBoot:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.HardDisc4
        @Access ${INSTDIR}.HardDisc4 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.Utilities
        @Access ${INSTDIR}.HardDisc4.Utilities /r
        @${CD} ${SRCDIR}.SystemRes.Boot
        ${MAKE} INSTDIR=${INSTDIR}.HardDisc4.Utilities COMPONENT=ResetBoot

ARPlayer:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.HardDisc4
        @Access ${INSTDIR}.HardDisc4 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.Apps
        @Access ${INSTDIR}.HardDisc4.Apps /r
        @${CD} ${SRCDIR}.Apps.ARPlayer
        ${MAKE} INSTDIR=${INSTDIR}.HardDisc4.Apps 

Bookworm:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.HardDisc4
        @Access ${INSTDIR}.HardDisc4 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.Manuals
        @Access ${INSTDIR}.HardDisc4.Manuals /r
        @${CD} ${SRCDIR}.Apps.Bookworm
        ${MAKE} INSTDIR=${INSTDIR}.HardDisc4.Manuals 

CloseUp:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.HardDisc4
        @Access ${INSTDIR}.HardDisc4 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.Apps
        @Access ${INSTDIR}.HardDisc4.Apps /r
        @${CD} ${SRCDIR}.Apps.CloseUp
        ${MAKE} INSTDIR=${INSTDIR}.HardDisc4.Apps 

Maestro:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.HardDisc4
        @Access ${INSTDIR}.HardDisc4 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.Apps
        @Access ${INSTDIR}.HardDisc4.Apps /r
        @${CD} ${SRCDIR}.Apps.Maestro
        ${MAKE} INSTDIR=${INSTDIR}.HardDisc4.Apps 

SciCalc:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.HardDisc4
        @Access ${INSTDIR}.HardDisc4 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.Apps
        @Access ${INSTDIR}.HardDisc4.Apps /r
        @${CD} ${SRCDIR}.Apps.SciCalc
        ${MAKE} INSTDIR=${INSTDIR}.HardDisc4.Apps 

Squash:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.HardDisc4
        @Access ${INSTDIR}.HardDisc4 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.Apps
        @Access ${INSTDIR}.HardDisc4.Apps /r
        @${CD} ${SRCDIR}.Apps.Squash
        ${MAKE} INSTDIR=${INSTDIR}.HardDisc4.Apps 

Diversions:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.HardDisc4
        @Access ${INSTDIR}.HardDisc4 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.Diversions
        @Access ${INSTDIR}.HardDisc4.Diversions /r
        @${CD} ${SRCDIR}.Diversions.Diversions
        ${MAKE} INSTDIR=${INSTDIR}.HardDisc4.Diversions 

Blocks:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.HardDisc4
        @Access ${INSTDIR}.HardDisc4 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.Diversions
        @Access ${INSTDIR}.HardDisc4.Diversions /r
        @${CD} ${SRCDIR}.Diversions.Blocks
        ${MAKE} INSTDIR=${INSTDIR}.HardDisc4.Diversions 

Clock:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.HardDisc4
        @Access ${INSTDIR}.HardDisc4 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.Diversions
        @Access ${INSTDIR}.HardDisc4.Diversions /r
        @${CD} ${SRCDIR}.Diversions.Clock
        ${MAKE} INSTDIR=${INSTDIR}.HardDisc4.Diversions 

Flasher:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.HardDisc4
        @Access ${INSTDIR}.HardDisc4 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.Diversions
        @Access ${INSTDIR}.HardDisc4.Diversions /r
        @${CD} ${SRCDIR}.Diversions.Flasher
        ${MAKE} INSTDIR=${INSTDIR}.HardDisc4.Diversions 

MemNow:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.HardDisc4
        @Access ${INSTDIR}.HardDisc4 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.Diversions
        @Access ${INSTDIR}.HardDisc4.Diversions /r
        @${CD} ${SRCDIR}.Diversions.MemNow
        ${MAKE} INSTDIR=${INSTDIR}.HardDisc4.Diversions 

Meteors:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.HardDisc4
        @Access ${INSTDIR}.HardDisc4 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.Diversions
        @Access ${INSTDIR}.HardDisc4.Diversions /r
        @${CD} ${SRCDIR}.Diversions.Meteors
        ${MAKE} INSTDIR=${INSTDIR}.HardDisc4.Diversions 

MineHunt:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.HardDisc4
        @Access ${INSTDIR}.HardDisc4 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.Diversions
        @Access ${INSTDIR}.HardDisc4.Diversions /r
        @${CD} ${SRCDIR}.Diversions.MineHunt
        ${MAKE} INSTDIR=${INSTDIR}.HardDisc4.Diversions 

Patience:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.HardDisc4
        @Access ${INSTDIR}.HardDisc4 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.Diversions
        @Access ${INSTDIR}.HardDisc4.Diversions /r
        @${CD} ${SRCDIR}.Diversions.Patience
        ${MAKE} INSTDIR=${INSTDIR}.HardDisc4.Diversions 

Player:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.HardDisc4
        @Access ${INSTDIR}.HardDisc4 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.Diversions
        @Access ${INSTDIR}.HardDisc4.Diversions /r
        @${CD} ${SRCDIR}.Apps.Player
        ${MAKE} INSTDIR=${INSTDIR}.HardDisc4.Diversions 

Puzzle:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.HardDisc4
        @Access ${INSTDIR}.HardDisc4 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.Diversions
        @Access ${INSTDIR}.HardDisc4.Diversions /r
        @${CD} ${SRCDIR}.Diversions.Puzzle
        ${MAKE} INSTDIR=${INSTDIR}.HardDisc4.Diversions 

ArtWorks:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.HardDisc4
        @Access ${INSTDIR}.HardDisc4 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.Diversions
        @Access ${INSTDIR}.HardDisc4.Diversions /r
        @${MKDIR} ${INSTDIR}.HardDisc4.Diversions.ArtWorks
        @Access ${INSTDIR}.HardDisc4.Diversions.ArtWorks /r
        @${CD} ${SRCDIR}.Demos.ArtWorks
        ${MAKE} INSTDIR=${INSTDIR}.HardDisc4.Diversions.ArtWorks 

Calibrate:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.HardDisc4
        @Access ${INSTDIR}.HardDisc4 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.Diversions
        @Access ${INSTDIR}.HardDisc4.Diversions /r
        @${MKDIR} ${INSTDIR}.HardDisc4.Diversions.Tools
        @Access ${INSTDIR}.HardDisc4.Diversions.Tools /r
        @${CD} ${SRCDIR}.Utilities.Calibrate
        ${MAKE} INSTDIR=${INSTDIR}.HardDisc4.Diversions.Tools 

ShowScrap:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.HardDisc4
        @Access ${INSTDIR}.HardDisc4 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.Diversions
        @Access ${INSTDIR}.HardDisc4.Diversions /r
        @${MKDIR} ${INSTDIR}.HardDisc4.Diversions.Tools
        @Access ${INSTDIR}.HardDisc4.Diversions.Tools /r
        @${CD} ${SRCDIR}.Utilities.ShowScrap
        ${MAKE} INSTDIR=${INSTDIR}.HardDisc4.Diversions.Tools 

ChangeFSI:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.HardDisc4
        @Access ${INSTDIR}.HardDisc4 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.Utilities
        @Access ${INSTDIR}.HardDisc4.Utilities /r
        @${CD} ${SRCDIR}.Apps.ChangeFSI
        ${MAKE} INSTDIR=${INSTDIR}.HardDisc4.Utilities 

SpriteExtend:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.HardDisc4
        @Access ${INSTDIR}.HardDisc4 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.Utilities
        @Access ${INSTDIR}.HardDisc4.Utilities /r
        @${MKDIR} ${INSTDIR}.HardDisc4.Utilities.!ChangeFSI
        @Access ${INSTDIR}.HardDisc4.Utilities.!ChangeFSI /r
        @${CD} ${SRCDIR}.OS_Core.Video.Render.SprExtend
        ${MAKE} INSTDIR=${INSTDIR}.HardDisc4.Utilities.!ChangeFSI 

CDPlayer:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.HardDisc4
        @Access ${INSTDIR}.HardDisc4 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.Utilities
        @Access ${INSTDIR}.HardDisc4.Utilities /r
        @${CD} ${SRCDIR}.Apps.CDPlayer
        ${MAKE} INSTDIR=${INSTDIR}.HardDisc4.Utilities 

PhotoView:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.HardDisc4
        @Access ${INSTDIR}.HardDisc4 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.Utilities
        @Access ${INSTDIR}.HardDisc4.Utilities /r
        @${CD} ${SRCDIR}.Apps.PhotoView
        ${MAKE} INSTDIR=${INSTDIR}.HardDisc4.Utilities COMPONENT=PhotoView

HForm:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.HardDisc4
        @Access ${INSTDIR}.HardDisc4 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.Utilities
        @Access ${INSTDIR}.HardDisc4.Utilities /r
        @${CD} ${SRCDIR}.Utilities.HForm
        ${MAKE} INSTDIR=${INSTDIR}.HardDisc4.Utilities 

Access+:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.HardDisc4
        @Access ${INSTDIR}.HardDisc4 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.Utilities
        @Access ${INSTDIR}.HardDisc4.Utilities /r
        @${CD} ${SRCDIR}.NetWorking.AUN.Access+
        ${MAKE} INSTDIR=${INSTDIR}.HardDisc4.Utilities COMPONENT=Access+

Patch:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.HardDisc4
        @Access ${INSTDIR}.HardDisc4 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.Utilities
        @Access ${INSTDIR}.HardDisc4.Utilities /r
        @${MKDIR} ${INSTDIR}.HardDisc4.Utilities.Patches
        @Access ${INSTDIR}.HardDisc4.Utilities.Patches /r
        @${CD} ${SRCDIR}.Utilities.Patches.Patch
        ${MAKE} INSTDIR=${INSTDIR}.HardDisc4.Utilities.Patches 

ansilib:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.HardDisc4
        @Access ${INSTDIR}.HardDisc4 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.Utilities
        @Access ${INSTDIR}.HardDisc4.Utilities /r
        @${MKDIR} ${INSTDIR}.HardDisc4.Utilities.Patches
        @Access ${INSTDIR}.HardDisc4.Utilities.Patches /r
        @${CD} ${SRCDIR}.Utilities.Patches.ansilib
        ${MAKE} INSTDIR=${INSTDIR}.HardDisc4.Utilities.Patches 

CallASWI:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.HardDisc4
        @Access ${INSTDIR}.HardDisc4 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.Utilities
        @Access ${INSTDIR}.HardDisc4.Utilities /r
        @${MKDIR} ${INSTDIR}.HardDisc4.Utilities.Patches
        @Access ${INSTDIR}.HardDisc4.Utilities.Patches /r
        @${CD} ${SRCDIR}.Utilities.Patches.CallASWI
        ${MAKE} INSTDIR=${INSTDIR}.HardDisc4.Utilities.Patches 

SCSIDM:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.HardDisc4
        @Access ${INSTDIR}.HardDisc4 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.Utilities
        @Access ${INSTDIR}.HardDisc4.Utilities /r
        @${MKDIR} ${INSTDIR}.HardDisc4.Utilities.Patches
        @Access ${INSTDIR}.HardDisc4.Utilities.Patches /r
        @${CD} ${SRCDIR}.Utilities.Patches.SCSIDM
        ${MAKE} INSTDIR=${INSTDIR}.HardDisc4.Utilities.Patches 

SSound:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.HardDisc4
        @Access ${INSTDIR}.HardDisc4 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.Utilities
        @Access ${INSTDIR}.HardDisc4.Utilities /r
        @${MKDIR} ${INSTDIR}.HardDisc4.Utilities.Patches
        @Access ${INSTDIR}.HardDisc4.Utilities.Patches /r
        @${CD} ${SRCDIR}.Utilities.Patches.SSound
        ${MAKE} INSTDIR=${INSTDIR}.HardDisc4.Utilities.Patches 

SparkFS:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.HardDisc4
        @Access ${INSTDIR}.HardDisc4 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.Utilities
        @Access ${INSTDIR}.HardDisc4.Utilities /r
        @${MKDIR} ${INSTDIR}.HardDisc4.Utilities.Patches
        @Access ${INSTDIR}.HardDisc4.Utilities.Patches /r
        @${CD} ${SRCDIR}.Utilities.Patches.SparkFS
        ${MAKE} INSTDIR=${INSTDIR}.HardDisc4.Utilities.Patches 

TCP/IP:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.HardDisc4
        @Access ${INSTDIR}.HardDisc4 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.Utilities
        @Access ${INSTDIR}.HardDisc4.Utilities /r
        @${MKDIR} ${INSTDIR}.HardDisc4.Utilities.Patches
        @Access ${INSTDIR}.HardDisc4.Utilities.Patches /r
        @${CD} ${SRCDIR}.Utilities.Patches.TCP/IP
        ${MAKE} INSTDIR=${INSTDIR}.HardDisc4.Utilities.Patches 

SaveCMOS:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.HardDisc4
        @Access ${INSTDIR}.HardDisc4 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.Utilities
        @Access ${INSTDIR}.HardDisc4.Utilities /r
        @${CD} ${SRCDIR}.Utilities.SaveCMOS
        ${MAKE} INSTDIR=${INSTDIR}.HardDisc4.Utilities 

T1ToFont:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.HardDisc4
        @Access ${INSTDIR}.HardDisc4 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.Utilities
        @Access ${INSTDIR}.HardDisc4.Utilities /r
        @${CD} ${SRCDIR}.Printing.T1ToFont
        ${MAKE} INSTDIR=${INSTDIR}.HardDisc4.Utilities 

Verify:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.HardDisc4
        @Access ${INSTDIR}.HardDisc4 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.Utilities
        @Access ${INSTDIR}.HardDisc4.Utilities /r
        @${CD} ${SRCDIR}.Utilities.Verify
        ${MAKE} INSTDIR=${INSTDIR}.HardDisc4.Utilities 

FontPrint:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.HardDisc4
        @Access ${INSTDIR}.HardDisc4 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.Printing
        @Access ${INSTDIR}.HardDisc4.Printing /r
        @${CD} ${SRCDIR}.Printing.FontPrint
        ${MAKE} INSTDIR=${INSTDIR}.HardDisc4.Printing 

PrintEdit:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.HardDisc4
        @Access ${INSTDIR}.HardDisc4 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.Printing
        @Access ${INSTDIR}.HardDisc4.Printing /r
        @${CD} ${SRCDIR}.Printing.PrintEdit
        ${MAKE} INSTDIR=${INSTDIR}.HardDisc4.Printing 

PrintDefs:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.HardDisc4
        @Access ${INSTDIR}.HardDisc4 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.Printing
        @Access ${INSTDIR}.HardDisc4.Printing /r
        @${CD} ${SRCDIR}.Printing.PrintDefs
        ${MAKE} INSTDIR=${INSTDIR}.HardDisc4.Printing 

SlideShow:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.HardDisc4
        @Access ${INSTDIR}.HardDisc4 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.Images
        @Access ${INSTDIR}.HardDisc4.Images /r
        @${CD} ${SRCDIR}.Demos.SlideShow
        ${MAKE} INSTDIR=${INSTDIR}.HardDisc4.Images 

Images:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.HardDisc4
        @Access ${INSTDIR}.HardDisc4 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.Images
        @Access ${INSTDIR}.HardDisc4.Images /r
        @${CD} ${SRCDIR}.Demos.Images
        ${MAKE} INSTDIR=${INSTDIR}.HardDisc4.Images 

Videos:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.HardDisc4
        @Access ${INSTDIR}.HardDisc4 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.Video
        @Access ${INSTDIR}.HardDisc4.Video /r
        @${CD} ${SRCDIR}.Demos.Videos
        ${MAKE} INSTDIR=${INSTDIR}.HardDisc4.Video 

Sounds:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.HardDisc4
        @Access ${INSTDIR}.HardDisc4 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.Sound
        @Access ${INSTDIR}.HardDisc4.Sound /r
        @${CD} ${SRCDIR}.Demos.Sounds
        ${MAKE} INSTDIR=${INSTDIR}.HardDisc4.Sound INSTFLAG=all

Tutorials:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.HardDisc4
        @Access ${INSTDIR}.HardDisc4 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.Tutorials
        @Access ${INSTDIR}.HardDisc4.Tutorials /r
        @${CD} ${SRCDIR}.Demos.Tutorials
        ${MAKE} INSTDIR=${INSTDIR}.HardDisc4.Tutorials 

AudioDemos:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.HardDisc4
        @Access ${INSTDIR}.HardDisc4 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.Diversions
        @Access ${INSTDIR}.HardDisc4.Diversions /r
        @${CD} ${SRCDIR}.Demos.AudioDemos
        ${MAKE} INSTDIR=${INSTDIR}.HardDisc4.Diversions 

AREncode:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.HardDisc4
        @Access ${INSTDIR}.HardDisc4 /r
        @${MKDIR} ${INSTDIR}.HardDisc4.Replay
        @Access ${INSTDIR}.HardDisc4.Replay /r
        @${CD} ${SRCDIR}.AREncode
        ${MAKE} INSTDIR=${INSTDIR}.HardDisc4.Replay 

