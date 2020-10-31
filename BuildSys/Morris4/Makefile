# System Makefile

CD      = dir
MKDIR   = cdir
SYSDIR  = <build$dir>.BuildSys
SRCDIR  = <src$dir>
INSTDIR = <install$dir>
RESDIR  = <resource$dir>.Resources
MAKE    = @amu ${MFLAGS} RESDIR=${RESDIR}

BUILD = \
 UnSqzAIF \
 CDFSFiler \
 CDFS \
 Toshiba \
 Sony \
 Philips \
 Hitachi \
 Chinon \
 ATAPI \
 CDFSDriver \
 CDFSResources \
 Scale \
 SaveAs \
 ProgInfo \
 PrintDbox \
 FontMenu \
 FontDbox \
 FileInfo \
 DCS_Quit \
 ColourMenu \
 ColourDbox \
 IconBar \
 Menu \
 Window \
 Toolbox \
 TinyStubs \
 tboxlib \
 PDriver \
 PDumperE2 \
 PDumperLJ \
 PDumperIW \
 PDumperDM \
 PDumperCX \
 RemotePrinterSupport \
 PDumperSpt \
 PDriverPS \
 PDriverDP \
 MakePSFont \
 Printers \
 Help \
 Chars \
 Alarm \
 Paint \
 Draw \
 Edit \
 ShareFS \
 Freeway \
 BootNet \
 Net \
 Internet \
 MManager \
 AUNMsgs \
 PCCardFS \
 BootCommands \
 DrawFile \
 ScreenModes \
 ColourPicker \
 DOSFS \
 Filer_Action \
 SharedCLibrary \
 BatMgr \
 Percussion \
 StringLib \
 WaveSynth \
 FilterManager \
 WindowUtils \
 TaskWindow \
 SystemDevices \
 SuperSample \
 Squash \
 SpriteUtils \
 SpriteExtend \
 SoundScheduler \
 SoundChannels \
 SoundDMA \
 ShellCLI \
 SerialMouse \
 SerialDeviceSupport \
 SerialDeviceDriver \
 ScreenBlanker \
 RTCAdjust \
 ROMFonts \
 ResourceFiler \
 RAMFSFiler \
 PipeFS \
 Pinboard \
 InternationalKeyboard \
 ParallelDeviceDriver \
 Obey \
 NetUtils \
 NetStatus \
 NetPrint \
 NetFiler \
 NetFS \
 DisplayManager \
 Joystick \
 IRQUtils2 \
 International \
 IIC \
 Hourglass \
 GameModes \
 Free \
 FPEmulator \
 ITable \
 FontManager \
 FSLock \
 FilerSWIs \
 Filer \
 RAMFS \
 ADFS \
 FileCore \
 Econet \
 BBCEconet \
 DrawMod \
 DragAnObj \
 DragASprite \
 DMAManager \
 DeviceFS \
 Debugger \
 ColourTrans \
 BufferManager \
 BASIC \
 ARM \
 ADFSFiler \
 TaskManager \
 PS2Driver \
 Portable \
 Mouse \
 Desktop \
 WindowManager \
 UK \
 TerritoryManager \
 MessageTrans \
 Messages \
 ResourceFS \
 FileSwitch \
 Podule \
 Kernel

EXPORT = \
 ToolboxMF \
 OSLib \
 SCSIFS \
 SCSIDriver \
 HostFS \
 DDT \
 ARM3 \
 HdrSrc

RESOURCE =

#
# Build rules:
#
clean: ${BUILD}
        @echo clean: Complete

export: ${BUILD} ${EXPORT} dirs
        @echo export: Complete

resources: ${BUILD} ${RESOURCE} dirs
        @echo resources: Complete

# rom build
rom: ${BUILD} dirs
        @echo rom: Complete

install_rom: ROMImage
        @echo install_rom: Complete

# disc build
all: ${BUILD}
        @echo all: Complete

install: ${BUILD}
        @echo install: Complete

dirs:
        ${MKDIR} <install$dir>
        ${MKDIR} <build$dir>.Export
        ${MKDIR} <build$dir>.Export.Hdr
        ${MKDIR} <build$dir>.Export.Hdr.Global
        ${MKDIR} <build$dir>.Export.Hdr.Interface
        ${MKDIR} <build$dir>.Export.Lib
        ${MKDIR} <resource$dir>
        ${MKDIR} <resource$dir>.Resources
        ${MKDIR} <resource$dir>.Resources2
        ${MKDIR} <resource$dir>.Apps

#
# Component rules:
#

Kernel:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.Morris
        @${CD} ${SRCDIR}.OS_Core.Kernel
        ${MAKE} INSTDIR=${INSTDIR}.ROM.Morris

ROMImage: ${BUILD}
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.Images
        @${CD} ${SYSDIR}.Morris4.ROMImage
        ${MAKE} INSTDIR=${INSTDIR}.Images

HdrSrc:
        @echo $@ ...
        @${CD} ${SRCDIR}.HdrSrc
        ${MAKE}

ARM3:
        @echo $@ ...
        @${CD} ${SRCDIR}.OS_Core.HWSupport.ARM3
        ${MAKE}

DDT:
        @echo $@ ...
        @${CD} ${SRCDIR}.Import.DDT
        ${MAKE}

HostFS:
        @echo $@ ...
        @${CD} ${SRCDIR}.Programmer.HostFS
        ${MAKE}

SCSIDriver:
        @echo $@ ...
        @${CD} ${SRCDIR}.OS_Core.HWSupport.SCSI.SCSIDriver
        ${MAKE}

SCSIFS:
        @echo $@ ...
        @${CD} ${SRCDIR}.OS_Core.FileSys.SCSIFS.SCSIFS
        ${MAKE}

OSLib:
        @echo $@ ...
        @${CD} ${SRCDIR}.Lib.OSLib
        ${MAKE}

ToolboxMF:
        @echo $@ ...
        @${CD} ${SRCDIR}.Import.Aquarius
        ${MAKE}

Podule:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.HWSupport.Podule
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

FileSwitch:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.FileSys.FileSwitch
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

ResourceFS:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.FileSys.ResourceFS.ResourceFS
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

Messages:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.Morris4
        @${CD} ${SRCDIR}.OS_Core.Internat.Messages
        ${MAKE} INSTDIR=${INSTDIR}.ROM.Morris4

MessageTrans:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.Internat.MsgTrans
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

TerritoryManager:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.Internat.Territory.Manager
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

UK:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.Internat.Territory.UK
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

WindowManager:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.Desktop.Wimp
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

Desktop:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.Desktop.Desktop
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

Mouse:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.Morris
        @${CD} ${SRCDIR}.OS_Core.HWSupport.Mouse
        ${MAKE} INSTDIR=${INSTDIR}.ROM.Morris

Portable:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.HWSupport.Portable
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

PS2Driver:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.Morris
        @${CD} ${SRCDIR}.OS_Core.HWSupport.PS2Driver
        ${MAKE} INSTDIR=${INSTDIR}.ROM.Morris

TaskManager:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.Desktop.Switcher
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

ADFSFiler:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.FileSys.ADFS.ADFSFiler
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

ARM:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.Morris
        @${CD} ${SRCDIR}.OS_Core.HWSupport.ARM
        ${MAKE} INSTDIR=${INSTDIR}.ROM.Morris

BASIC:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.Programmer
        @${CD} ${SRCDIR}.Programmer.BASIC
        ${MAKE} INSTDIR=${INSTDIR}.ROM.Programmer

BufferManager:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.HWSupport.Buffers
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

ColourTrans:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.Video.Render.Colours
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

Debugger:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.Morris
        @${CD} ${SRCDIR}.Programmer.Debugger
        ${MAKE} INSTDIR=${INSTDIR}.ROM.Morris

DeviceFS:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.HWSupport.DeviceFS
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

DMAManager:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.Morris
        @${CD} ${SRCDIR}.OS_Core.HWSupport.DMA
        ${MAKE} INSTDIR=${INSTDIR}.ROM.Morris

DragASprite:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.Desktop.DragASprit
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

DragAnObj:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.Desktop.DragAnObj
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

DrawMod:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.Video.Render.Draw
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

BBCEconet:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.Networking
        @${CD} ${SRCDIR}.Networking.BBCEconet
        ${MAKE} INSTDIR=${INSTDIR}.ROM.Networking

Econet:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.Networking
        @${CD} ${SRCDIR}.Networking.Econet
        ${MAKE} INSTDIR=${INSTDIR}.ROM.Networking

FileCore:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.FileSys.FileCore
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

ADFS:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.Morris
        @${CD} ${SRCDIR}.OS_Core.FileSys.ADFS.ADFS
        ${MAKE} INSTDIR=${INSTDIR}.ROM.Morris

RAMFS:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.FileSys.RAMFS.RAMFS
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

Filer:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.Desktop.Filer
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

FilerSWIs:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.Desktop.FilerSWIs
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

FSLock:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.FSLock
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

FontManager:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.Video.Render.Fonts.Manager
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

ITable:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.Video.Render.Fonts.ITable
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

FPEmulator:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.Morris
        @${CD} ${SRCDIR}.OS_Core.HWSupport.FPASC.riscos
        ${MAKE} INSTDIR=${INSTDIR}.ROM.Morris

Free:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.Desktop.Free
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

GameModes:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.GameModes2
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

Hourglass:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.Video.Render.Hourglass
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

IIC:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.HWSupport.IIC
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

International:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.Internat.Inter
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

IRQUtils2:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.IRQUtils2
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

Joystick:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.HWSupport.Joystick
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

DisplayManager:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.Video.UserI.Display
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

NetFS:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.FileSys.NetFS.NetFS
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

NetFiler:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.FileSys.NetFS.NetFiler
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

NetPrint:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.FileSys.NetPrint
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

NetStatus:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.Networking
        @${CD} ${SRCDIR}.Networking.NetStatus
        ${MAKE} INSTDIR=${INSTDIR}.ROM.Networking

NetUtils:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.Networking
        @${CD} ${SRCDIR}.Networking.NetUtils2
        ${MAKE} INSTDIR=${INSTDIR}.ROM.Networking

Obey:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.Programmer
        @${CD} ${SRCDIR}.Programmer.Obey
        ${MAKE} INSTDIR=${INSTDIR}.ROM.Programmer

ParallelDeviceDriver:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.HWSupport.Parallel
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

InternationalKeyboard:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.Internat.IntKey
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

Pinboard:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.Desktop.Pinboard
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

PipeFS:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.FileSys.PipeFS
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

RAMFSFiler:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.FileSys.RAMFS.RAMFSFiler
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

ResourceFiler:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.FileSys.ResourceFS.ResFiler
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

ROMFonts:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.Video.Render.Fonts.ROMFonts
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

RTCAdjust:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.Morris
        @${CD} ${SRCDIR}.OS_Core.HWSupport.RTCAdjust
        ${MAKE} INSTDIR=${INSTDIR}.ROM.Morris

ScreenBlanker:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.Video.Render.ScrBlank
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

SerialDeviceDriver:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.HWSupport.Serial
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

SerialDeviceSupport:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.HWSupport.SerialSpt
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

SerialMouse:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.HWSupport.SerMouse
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

ShellCLI:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.Desktop.ShellCLI
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

SoundDMA:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.Morris
        @${CD} ${SRCDIR}.OS_Core.HWSupport.Sound.Sound0
        ${MAKE} INSTDIR=${INSTDIR}.ROM.Morris

SoundChannels:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.HWSupport.Sound.Sound1
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

SoundScheduler:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.HWSupport.Sound.Sound2
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

SpriteExtend:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.Video.Render.SprExtend
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

SpriteUtils:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.Video.Render.SpriteUtil
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

Squash:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.Squash
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

SuperSample:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.Video.Render.Super
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

SystemDevices:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.HWSupport.SystemDevs
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

TaskWindow:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.Desktop.TaskWindow
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

WindowUtils:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.Desktop.WimpUtils
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

FilterManager:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.Desktop.Filter
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

WaveSynth:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.HWSupport.Sound.Voices.WaveSynth
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

StringLib:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.HWSupport.Sound.Voices.StringLib
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

Percussion:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.HWSupport.Sound.Voices.Percussion
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

BatMgr:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.HWSupport.BatMgr
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

SharedCLibrary:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.Lib
        @${CD} ${SRCDIR}.Lib.RISC_OSLib
        ${MAKE} INSTDIR=${INSTDIR}.ROM.Lib

Filer_Action:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.Desktop.FilerAct
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

DOSFS:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.FileSys.ImageFS.DOSFS
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

ColourPicker:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.Video.UserI.Picker
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

ScreenModes:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.Video.UserI.ScrModes
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

DrawFile:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.Video.Render.DrawFile
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

BootCommands:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.BootCmds
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

PCCardFS:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.FileSys.PCCardFS.PCCardFS
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

AUNMsgs:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.Networking
        @${CD} ${SRCDIR}.Networking.AUN.AUNMsgs
        ${MAKE} INSTDIR=${INSTDIR}.ROM.Networking

MManager:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.Networking
        @${CD} ${SRCDIR}.Networking.AUN.MManager
        ${MAKE} INSTDIR=${INSTDIR}.ROM.Networking

Internet:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.Networking
        @${CD} ${SRCDIR}.Networking.AUN.Internet.build
        ${MAKE} INSTDIR=${INSTDIR}.ROM.Networking

Net:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.Networking
        @${CD} ${SRCDIR}.Networking.AUN.Net
        ${MAKE} INSTDIR=${INSTDIR}.ROM.Networking

BootNet:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.Networking
        @${CD} ${SRCDIR}.Networking.AUN.BootNet
        ${MAKE} INSTDIR=${INSTDIR}.ROM.Networking

Freeway:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.Networking
        @${CD} ${SRCDIR}.Networking.AUN.Access.Freeway
        ${MAKE} INSTDIR=${INSTDIR}.ROM.Networking

ShareFS:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.Networking
        @${CD} ${SRCDIR}.Networking.AUN.Access.ShareFS.ShareFS
        ${MAKE} INSTDIR=${INSTDIR}.ROM.Networking

Edit:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.Apps
        @${CD} ${SRCDIR}.Apps.Edit
        ${MAKE} INSTDIR=${INSTDIR}.ROM.Apps

Draw:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.Apps
        @${CD} ${SRCDIR}.Apps.Draw
        ${MAKE} INSTDIR=${INSTDIR}.ROM.Apps

Paint:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.Apps
        @${CD} ${SRCDIR}.Apps.Paint
        ${MAKE} INSTDIR=${INSTDIR}.ROM.Apps

Alarm:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.Apps
        @${CD} ${SRCDIR}.Apps.Alarm
        ${MAKE} INSTDIR=${INSTDIR}.ROM.Apps

Chars:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.Apps
        @${CD} ${SRCDIR}.Apps.Chars
        ${MAKE} INSTDIR=${INSTDIR}.ROM.Apps

Help:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.Apps
        @${CD} ${SRCDIR}.Apps.Help
        ${MAKE} INSTDIR=${INSTDIR}.ROM.Apps

Printers:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.Printing
        @${CD} ${SRCDIR}.Printing.Printers.Manager
        ${MAKE} INSTDIR=${INSTDIR}.ROM.Printing

MakePSFont:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.Printing
        @${CD} ${SRCDIR}.Printing.Printers.Modules.MakePSFont
        ${MAKE} INSTDIR=${INSTDIR}.ROM.Printing

PDriverDP:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.Printing
        @${CD} ${SRCDIR}.Printing.Printers.Modules.PDModules
        ${MAKE} INSTDIR=${INSTDIR}.ROM.Printing

PDriverPS:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.Printing
        @${CD} ${SRCDIR}.Printing.Printers.Modules.PDModules
        ${MAKE} INSTDIR=${INSTDIR}.ROM.Printing

PDumperSpt:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.Printing
        @${CD} ${SRCDIR}.Printing.Printers.Modules.PDumperSpt
        ${MAKE} INSTDIR=${INSTDIR}.ROM.Printing

RemotePrinterSupport:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.Printing
        @${CD} ${SRCDIR}.Printing.Printers.Modules.RemPrnSpt
        ${MAKE} INSTDIR=${INSTDIR}.ROM.Printing

PDumperCX:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.Printing
        @${CD} ${SRCDIR}.Printing.Printers.PDumpers
        ${MAKE} INSTDIR=${INSTDIR}.ROM.Printing

PDumperDM:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.Printing
        @${CD} ${SRCDIR}.Printing.Printers.PDumpers
        ${MAKE} INSTDIR=${INSTDIR}.ROM.Printing

PDumperIW:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.Printing
        @${CD} ${SRCDIR}.Printing.Printers.PDumpers
        ${MAKE} INSTDIR=${INSTDIR}.ROM.Printing

PDumperLJ:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.Printing
        @${CD} ${SRCDIR}.Printing.Printers.PDumpers
        ${MAKE} INSTDIR=${INSTDIR}.ROM.Printing

PDumperE2:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.Printing
        @${CD} ${SRCDIR}.Printing.Printers.PDumpers
        ${MAKE} INSTDIR=${INSTDIR}.ROM.Printing

PDriver:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.Printing
        @${CD} ${SRCDIR}.Printing.Printers.Modules.PDriver
        ${MAKE} INSTDIR=${INSTDIR}.ROM.Printing

tboxlib:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.Toolbox
        @${CD} ${SRCDIR}.Import.Aquarius.tbox.common
        ${MAKE} INSTDIR=${INSTDIR}.ROM.Toolbox

TinyStubs:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.Toolbox
        @${CD} ${SRCDIR}.Import.Aquarius.TinyStubs
        ${MAKE} INSTDIR=${INSTDIR}.ROM.Toolbox

Toolbox:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.Toolbox
        @${CD} ${SRCDIR}.Import.Aquarius.tbox.Toolbox
        ${MAKE} INSTDIR=${INSTDIR}.ROM.Toolbox

Window:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.Toolbox
        @${CD} ${SRCDIR}.Import.Aquarius.tbox.Window
        ${MAKE} INSTDIR=${INSTDIR}.ROM.Toolbox

Menu:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.Toolbox
        @${CD} ${SRCDIR}.Import.Aquarius.tbox.Menu
        ${MAKE} INSTDIR=${INSTDIR}.ROM.Toolbox

IconBar:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.Toolbox
        @${CD} ${SRCDIR}.Import.Aquarius.tbox.IconBar
        ${MAKE} INSTDIR=${INSTDIR}.ROM.Toolbox

ColourDbox:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.Toolbox
        @${CD} ${SRCDIR}.Import.Aquarius.tbox.ColourDbox
        ${MAKE} INSTDIR=${INSTDIR}.ROM.Toolbox

ColourMenu:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.Toolbox
        @${CD} ${SRCDIR}.Import.Aquarius.tbox.ColourMenu
        ${MAKE} INSTDIR=${INSTDIR}.ROM.Toolbox

DCS_Quit:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.Toolbox
        @${CD} ${SRCDIR}.Import.Aquarius.tbox.DCS
        ${MAKE} INSTDIR=${INSTDIR}.ROM.Toolbox

FileInfo:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.Toolbox
        @${CD} ${SRCDIR}.Import.Aquarius.tbox.FileInfo
        ${MAKE} INSTDIR=${INSTDIR}.ROM.Toolbox

FontDbox:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.Toolbox
        @${CD} ${SRCDIR}.Import.Aquarius.tbox.FontDbox
        ${MAKE} INSTDIR=${INSTDIR}.ROM.Toolbox

FontMenu:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.Toolbox
        @${CD} ${SRCDIR}.Import.Aquarius.tbox.FontMenu
        ${MAKE} INSTDIR=${INSTDIR}.ROM.Toolbox

PrintDbox:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.Toolbox
        @${CD} ${SRCDIR}.Import.Aquarius.tbox.PrintDbox
        ${MAKE} INSTDIR=${INSTDIR}.ROM.Toolbox

ProgInfo:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.Toolbox
        @${CD} ${SRCDIR}.Import.Aquarius.tbox.ProgInfo
        ${MAKE} INSTDIR=${INSTDIR}.ROM.Toolbox

SaveAs:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.Toolbox
        @${CD} ${SRCDIR}.Import.Aquarius.tbox.SaveAs
        ${MAKE} INSTDIR=${INSTDIR}.ROM.Toolbox

Scale:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.Toolbox
        @${CD} ${SRCDIR}.Import.Aquarius.tbox.Scale
        ${MAKE} INSTDIR=${INSTDIR}.ROM.Toolbox

CDFSResources:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.CD
        @${CD} ${SRCDIR}.OS_Core.FileSys.CDFS.CDFSRes
        ${MAKE} INSTDIR=${INSTDIR}.ROM.CD

CDFSDriver:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.CD
        @${CD} ${SRCDIR}.OS_Core.HWSupport.CD.CDFSDriver
        ${MAKE} INSTDIR=${INSTDIR}.ROM.CD

ATAPI:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.CD
        @${CD} ${SRCDIR}.OS_Core.HWSupport.CD.ATAPI
        ${MAKE} INSTDIR=${INSTDIR}.ROM.CD

Chinon:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.CD
        @${CD} ${SRCDIR}.OS_Core.HWSupport.CD.Chinon
        ${MAKE} INSTDIR=${INSTDIR}.ROM.CD

Hitachi:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.CD
        @${CD} ${SRCDIR}.OS_Core.HWSupport.CD.Hitachi
        ${MAKE} INSTDIR=${INSTDIR}.ROM.CD

Philips:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.CD
        @${CD} ${SRCDIR}.OS_Core.HWSupport.CD.Philips
        ${MAKE} INSTDIR=${INSTDIR}.ROM.CD

Sony:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.CD
        @${CD} ${SRCDIR}.OS_Core.HWSupport.CD.Sony
        ${MAKE} INSTDIR=${INSTDIR}.ROM.CD

Toshiba:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.CD
        @${CD} ${SRCDIR}.OS_Core.HWSupport.CD.Toshiba
        ${MAKE} INSTDIR=${INSTDIR}.ROM.CD

CDFS:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.CD
        @${CD} ${SRCDIR}.OS_Core.FileSys.CDFS.CDFS
        ${MAKE} INSTDIR=${INSTDIR}.ROM.CD

CDFSFiler:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.CD
        @${CD} ${SRCDIR}.OS_Core.FileSys.CDFS.CDFSFiler
        ${MAKE} INSTDIR=${INSTDIR}.ROM.CD

UnSqzAIF:
        @echo $@ ...
        @${MKDIR} ${INSTDIR}.ROM
        @${MKDIR} ${INSTDIR}.ROM.OS_Core
        @${CD} ${SRCDIR}.OS_Core.HWSupport.UnSqzAIF
        ${MAKE} INSTDIR=${INSTDIR}.ROM.OS_Core

