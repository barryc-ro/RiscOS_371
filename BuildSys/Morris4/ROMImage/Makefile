# Makefile for ROMImage

CD      = dir
LD      = link
MKDIR   = cdir
MKIMAGE = BigSplit1

SRCDIR  = <src$dir>
INSTDIR = <install$dir>
CLIBDIR = <install$dir>.ROM.Lib
ABSSYM  = RISC_OSLib:o.AbsSym

MODULES = \
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
 CDFSRes \
 Scale \
 SaveAs \
 ProgInfo \
 PrintDbox \
 FontMenu \
 FontDbox \
 FileInfo \
 DCS \
 ColourMenu \
 ColourDbox \
 IconBar \
 Menu \
 Window \
 Toolbox \
 TinyStubs \
 PDriver \
 PDumperE2 \
 PDumperLJ \
 PDumperIW \
 PDumperDM \
 PDumperCX \
 RemPrnSpt \
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
 BootCmds \
 DrawFile \
 ScrModes \
 Picker \
 DOSFS \
 FilerAct \
 RISC_OSLib \
 BatMgr \
 Percussion \
 StringLib \
 WaveSynth \
 FilterMgr \
 WimpUtils2 \
 TaskWindow \
 SystemDevs \
 Super \
 Squash \
 SpriteUtil \
 SprExtend \
 Sound2 \
 Sound1 \
 Sound0 \
 ShellCLI \
 SerMouse \
 SerialSpt \
 Serial \
 ScrBlank \
 RTCAdjust \
 ROMFonts \
 ResFiler \
 RAMFSFiler \
 PipeFS \
 Pinboard \
 IntKey \
 Parallel \
 Obey \
 NetUtils2 \
 NetStatus \
 NetPrint \
 NetFiler \
 NetFS \
 Display \
 Joystick \
 IRQUtils2 \
 Inter \
 IIC \
 Hourglass \
 GameModes2 \
 Free \
 FPEmulator \
 ITable \
 Fonts \
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
 DragASprit \
 DMA \
 DeviceFS \
 Debugger \
 Colours \
 Buffers \
 BASICTrans \
 BASIC105 \
 ARM \
 ADFSFiler \
 Switcher \
 PS2Driver \
 Portable \
 Mouse \
 Desktop \
 Wimp \
 UK \
 TerrMgr \
 MsgTrans \
 Messages \
 ResourceFS \
 FileSwitch \
 Podule \
 Kernel

#
# Build rules:
#
install_rom: ${MODULES} dirs
        ${MKIMAGE} { < ForBigSplt }

dirs:
        ${MKDIR} ${CLIBDIR}.linked
        ${MKDIR} ${CLIBDIR}.map

Kernel:
        @seteval PositionInRom &03800000
        @setolength File$Length ${INSTDIR}.ROM.Morris.Kernel
        @echo Kernel                     <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) 

Podule:
        @setolength File$Length ${INSTDIR}.ROM.OS_Core.Podule
        @echo Podule                     <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

FileSwitch:
        @setolength File$Length ${INSTDIR}.ROM.OS_Core.FileSwitch
        @echo FileSwitch                 <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

ResourceFS:
        @setolength File$Length ${INSTDIR}.ROM.OS_Core.ResourceFS
        @echo ResourceFS                 <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

Messages:
        @setolength File$Length ${INSTDIR}.ROM.Morris4.Messages
        @echo Messages                   <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

MsgTrans:
        @setolength File$Length ${INSTDIR}.ROM.OS_Core.MsgTrans
        @echo MsgTrans                   <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

TerrMgr:
        @setolength File$Length ${INSTDIR}.ROM.OS_Core.TerrMgr
        @echo TerrMgr                    <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

UK:
        @setolength File$Length ${INSTDIR}.ROM.OS_Core.UK
        @echo UK                         <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

Wimp:
        @setolength File$Length ${INSTDIR}.ROM.OS_Core.Wimp
        @echo Wimp                       <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

Desktop:
        @setolength File$Length ${INSTDIR}.ROM.OS_Core.Desktop
        @echo Desktop                    <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

Mouse:
        @setolength File$Length ${INSTDIR}.ROM.Morris.Mouse
        @echo Mouse                      <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

Portable:
        @setolength File$Length ${INSTDIR}.ROM.OS_Core.Portable
        @echo Portable                   <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

PS2Driver:
        @setolength File$Length ${INSTDIR}.ROM.Morris.PS2Driver
        @echo PS2Driver                  <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

Switcher:
        @setolength File$Length ${INSTDIR}.ROM.OS_Core.Switcher
        @echo Switcher                   <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

ADFSFiler:
        @setolength File$Length ${INSTDIR}.ROM.OS_Core.ADFSFiler
        @echo ADFSFiler                  <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

ARM:
        @setolength File$Length ${INSTDIR}.ROM.Morris.ARM
        @echo ARM                        <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

BASIC105:
        @setolength File$Length ${INSTDIR}.ROM.Programmer.BASIC105
        @echo BASIC105                   <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

BASICTrans:
        @setolength File$Length ${INSTDIR}.ROM.Programmer.BASICTrans
        @echo BASICTrans                 <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

Buffers:
        @setolength File$Length ${INSTDIR}.ROM.OS_Core.Buffers
        @echo Buffers                    <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

Colours:
        @setolength File$Length ${INSTDIR}.ROM.OS_Core.Colours
        @echo Colours                    <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

Debugger:
        @setolength File$Length ${INSTDIR}.ROM.Morris.Debugger
        @echo Debugger                   <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

DeviceFS:
        @setolength File$Length ${INSTDIR}.ROM.OS_Core.DeviceFS
        @echo DeviceFS                   <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

DMA:
        @setolength File$Length ${INSTDIR}.ROM.Morris.DMA
        @echo DMA                        <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

DragASprit:
        @setolength File$Length ${INSTDIR}.ROM.OS_Core.DragASprit
        @echo DragASprit                 <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

DragAnObj:
        @setolength File$Length ${INSTDIR}.ROM.OS_Core.DragAnObj
        @echo DragAnObj                  <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

DrawMod:
        @setolength File$Length ${INSTDIR}.ROM.OS_Core.DrawMod
        @echo DrawMod                    <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

BBCEconet:
        @setolength File$Length ${INSTDIR}.ROM.Networking.BBCEconet
        @echo BBCEconet                  <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

Econet:
        @setolength File$Length ${INSTDIR}.ROM.Networking.Econet
        @echo Econet                     <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

FileCore:
        @setolength File$Length ${INSTDIR}.ROM.OS_Core.FileCore
        @echo FileCore                   <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

ADFS:
        @setolength File$Length ${INSTDIR}.ROM.Morris.ADFS
        @echo ADFS                       <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

RAMFS:
        @setolength File$Length ${INSTDIR}.ROM.OS_Core.RAMFS
        @echo RAMFS                      <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

Filer:
        @setolength File$Length ${INSTDIR}.ROM.OS_Core.Filer
        @echo Filer                      <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

FilerSWIs:
        @setolength File$Length ${INSTDIR}.ROM.OS_Core.FilerSWIs
        @echo FilerSWIs                  <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

FSLock:
        @setolength File$Length ${INSTDIR}.ROM.OS_Core.FSLock
        @echo FSLock                     <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

Fonts:
        @setolength File$Length ${INSTDIR}.ROM.OS_Core.Fonts
        @echo Fonts                      <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

ITable:
        @setolength File$Length ${INSTDIR}.ROM.OS_Core.ITable
        @echo ITable                     <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

FPEmulator:
        @setolength File$Length ${INSTDIR}.ROM.Morris.FPEmulator
        @echo FPEmulator                 <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

Free:
        @setolength File$Length ${INSTDIR}.ROM.OS_Core.Free
        @echo Free                       <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

GameModes2:
        @setolength File$Length ${INSTDIR}.ROM.OS_Core.GameModes2
        @echo GameModes2                 <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

Hourglass:
        @setolength File$Length ${INSTDIR}.ROM.OS_Core.Hourglass
        @echo Hourglass                  <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

IIC:
        @setolength File$Length ${INSTDIR}.ROM.OS_Core.IIC
        @echo IIC                        <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

Inter:
        @setolength File$Length ${INSTDIR}.ROM.OS_Core.Inter
        @echo Inter                      <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

IRQUtils2:
        @setolength File$Length ${INSTDIR}.ROM.OS_Core.IRQUtils2
        @echo IRQUtils2                  <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

Joystick:
        @setolength File$Length ${INSTDIR}.ROM.OS_Core.Joystick
        @echo Joystick                   <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

Display:
        @setolength File$Length ${INSTDIR}.ROM.OS_Core.Display
        @echo Display                    <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

NetFS:
        @setolength File$Length ${INSTDIR}.ROM.OS_Core.NetFS
        @echo NetFS                      <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

NetFiler:
        @setolength File$Length ${INSTDIR}.ROM.OS_Core.NetFiler
        @echo NetFiler                   <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

NetPrint:
        @setolength File$Length ${INSTDIR}.ROM.OS_Core.NetPrint
        @echo NetPrint                   <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

NetStatus:
        @setolength File$Length ${INSTDIR}.ROM.Networking.NetStatus
        @echo NetStatus                  <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

NetUtils2:
        @setolength File$Length ${INSTDIR}.ROM.Networking.NetUtils2
        @echo NetUtils2                  <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

Obey:
        @setolength File$Length ${INSTDIR}.ROM.Programmer.Obey
        @echo Obey                       <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

Parallel:
        @setolength File$Length ${INSTDIR}.ROM.OS_Core.Parallel
        @echo Parallel                   <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

IntKey:
        @setolength File$Length ${INSTDIR}.ROM.OS_Core.IntKey
        @echo IntKey                     <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

Pinboard:
        @setolength File$Length ${INSTDIR}.ROM.OS_Core.Pinboard
        @echo Pinboard                   <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

PipeFS:
        @setolength File$Length ${INSTDIR}.ROM.OS_Core.PipeFS
        @echo PipeFS                     <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

RAMFSFiler:
        @setolength File$Length ${INSTDIR}.ROM.OS_Core.RAMFSFiler
        @echo RAMFSFiler                 <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

ResFiler:
        @setolength File$Length ${INSTDIR}.ROM.OS_Core.ResFiler
        @echo ResFiler                   <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

ROMFonts:
        @setolength File$Length ${INSTDIR}.ROM.OS_Core.ROMFonts
        @echo ROMFonts                   <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

RTCAdjust:
        @setolength File$Length ${INSTDIR}.ROM.Morris.RTCAdjust
        @echo RTCAdjust                  <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

ScrBlank:
        @setolength File$Length ${INSTDIR}.ROM.OS_Core.ScrBlank
        @echo ScrBlank                   <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

Serial:
        @setolength File$Length ${INSTDIR}.ROM.OS_Core.Serial
        @echo Serial                     <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

SerialSpt:
        @setolength File$Length ${INSTDIR}.ROM.OS_Core.SerialSpt
        @echo SerialSpt                  <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

SerMouse:
        @setolength File$Length ${INSTDIR}.ROM.OS_Core.SerMouse
        @echo SerMouse                   <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

ShellCLI:
        @setolength File$Length ${INSTDIR}.ROM.OS_Core.ShellCLI
        @echo ShellCLI                   <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

Sound0:
        @setolength File$Length ${INSTDIR}.ROM.Morris.Sound0
        @echo Sound0                     <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

Sound1:
        @setolength File$Length ${INSTDIR}.ROM.OS_Core.Sound1
        @echo Sound1                     <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

Sound2:
        @setolength File$Length ${INSTDIR}.ROM.OS_Core.Sound2
        @echo Sound2                     <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

SprExtend:
        @setolength File$Length ${INSTDIR}.ROM.OS_Core.SprExtend
        @echo SprExtend                  <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

SpriteUtil:
        @setolength File$Length ${INSTDIR}.ROM.OS_Core.SpriteUtil
        @echo SpriteUtil                 <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

Squash:
        @setolength File$Length ${INSTDIR}.ROM.OS_Core.Squash
        @echo Squash                     <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

Super:
        @setolength File$Length ${INSTDIR}.ROM.OS_Core.Super
        @echo Super                      <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

SystemDevs:
        @setolength File$Length ${INSTDIR}.ROM.OS_Core.SystemDevs
        @echo SystemDevs                 <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

TaskWindow:
        @setolength File$Length ${INSTDIR}.ROM.OS_Core.TaskWindow
        @echo TaskWindow                 <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

WimpUtils2:
        @setolength File$Length ${INSTDIR}.ROM.OS_Core.WimpUtils2
        @echo WimpUtils2                 <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

FilterMgr:
        @setolength File$Length ${INSTDIR}.ROM.OS_Core.FilterMgr
        @echo FilterMgr                  <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

WaveSynth:
        @setolength File$Length ${INSTDIR}.ROM.OS_Core.WaveSynth
        @echo WaveSynth                  <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

StringLib:
        @setolength File$Length ${INSTDIR}.ROM.OS_Core.StringLib
        @echo StringLib                  <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

Percussion:
        @setolength File$Length ${INSTDIR}.ROM.OS_Core.Percussion
        @echo Percussion                 <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

BatMgr:
        @setolength File$Length ${INSTDIR}.ROM.OS_Core.BatMgr
        @echo BatMgr                     <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

RISC_OSLib:
        @${CD} ${SRCDIR}.Lib.RISC_OSLib
        @set alias$amu_rom_link amu MACHINE=<Machine> LOCALE=<Locale> ADDRESS=<PositionInRom> rom_link %0
        amu_rom_link LINKDIR=${CLIBDIR}.linked
        @unset alias$amu_rom_link
        @back
        setolength File$Length ${CLIBDIR}.linked.RISC_OSLib
        @echo RISC_OSLib                 <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

FilerAct:
        @${CD} ${SRCDIR}.OS_Core.Desktop.FilerAct
        @set alias$amu_rom_link amu MACHINE=<Machine> LOCALE=<Locale> ADDRESS=<PositionInRom> rom_link %0
        amu_rom_link LINKDIR=${CLIBDIR}.linked
        @unset alias$amu_rom_link
        @back
        setolength File$Length ${CLIBDIR}.linked.FilerAct
        @echo FilerAct                   <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

DOSFS:
        @${CD} ${SRCDIR}.OS_Core.FileSys.ImageFS.DOSFS
        @set alias$amu_rom_link amu MACHINE=<Machine> LOCALE=<Locale> ADDRESS=<PositionInRom> rom_link %0
        amu_rom_link LINKDIR=${CLIBDIR}.linked
        @unset alias$amu_rom_link
        @back
        setolength File$Length ${CLIBDIR}.linked.DOSFS
        @echo DOSFS                      <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

Picker:
        @${CD} ${SRCDIR}.OS_Core.Video.UserI.Picker
        @set alias$amu_rom_link amu MACHINE=<Machine> LOCALE=<Locale> ADDRESS=<PositionInRom> rom_link %0
        amu_rom_link LINKDIR=${CLIBDIR}.linked
        @unset alias$amu_rom_link
        @back
        setolength File$Length ${CLIBDIR}.linked.Picker
        @echo Picker                     <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

ScrModes:
        @${CD} ${SRCDIR}.OS_Core.Video.UserI.ScrModes
        @set alias$amu_rom_link amu MACHINE=<Machine> LOCALE=<Locale> ADDRESS=<PositionInRom> rom_link %0
        amu_rom_link LINKDIR=${CLIBDIR}.linked
        @unset alias$amu_rom_link
        @back
        setolength File$Length ${CLIBDIR}.linked.ScrModes
        @echo ScrModes                   <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

DrawFile:
        @${CD} ${SRCDIR}.OS_Core.Video.Render.DrawFile
        @set alias$amu_rom_link amu MACHINE=<Machine> LOCALE=<Locale> ADDRESS=<PositionInRom> rom_link %0
        amu_rom_link LINKDIR=${CLIBDIR}.linked
        @unset alias$amu_rom_link
        @back
        setolength File$Length ${CLIBDIR}.linked.DrawFile
        @echo DrawFile                   <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

BootCmds:
        @${CD} ${SRCDIR}.OS_Core.BootCmds
        @set alias$amu_rom_link amu MACHINE=<Machine> LOCALE=<Locale> ADDRESS=<PositionInRom> rom_link %0
        amu_rom_link LINKDIR=${CLIBDIR}.linked
        @unset alias$amu_rom_link
        @back
        setolength File$Length ${CLIBDIR}.linked.BootCmds
        @echo BootCmds                   <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

AUNMsgs:
        @setolength File$Length ${INSTDIR}.ROM.Networking.AUNMsgs
        @echo AUNMsgs                    <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

MManager:
        @setolength File$Length ${INSTDIR}.ROM.Networking.MManager
        @echo MManager                   <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

Internet:
        @${CD} ${SRCDIR}.Networking.AUN.Internet.build
        @set alias$amu_rom_link amu MACHINE=<Machine> LOCALE=<Locale> ADDRESS=<PositionInRom> rom_link %0
        amu_rom_link LINKDIR=${CLIBDIR}.linked
        @unset alias$amu_rom_link
        @back
        setolength File$Length ${CLIBDIR}.linked.Internet
        @echo Internet                   <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

Net:
        @${CD} ${SRCDIR}.Networking.AUN.Net
        @set alias$amu_rom_link amu MACHINE=<Machine> LOCALE=<Locale> ADDRESS=<PositionInRom> rom_link %0
        amu_rom_link LINKDIR=${CLIBDIR}.linked
        @unset alias$amu_rom_link
        @back
        setolength File$Length ${CLIBDIR}.linked.Net
        @echo Net                        <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

BootNet:
        @setolength File$Length ${INSTDIR}.ROM.Networking.BootNet
        @echo BootNet                    <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

Freeway:
        @${CD} ${SRCDIR}.Networking.AUN.Access.Freeway
        @set alias$amu_rom_link amu MACHINE=<Machine> LOCALE=<Locale> ADDRESS=<PositionInRom> rom_link %0
        amu_rom_link LINKDIR=${CLIBDIR}.linked
        @unset alias$amu_rom_link
        @back
        setolength File$Length ${CLIBDIR}.linked.Freeway
        @echo Freeway                    <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

ShareFS:
        @${CD} ${SRCDIR}.Networking.AUN.Access.ShareFS.ShareFS
        @set alias$amu_rom_link amu MACHINE=<Machine> LOCALE=<Locale> ADDRESS=<PositionInRom> rom_link %0
        amu_rom_link LINKDIR=${CLIBDIR}.linked
        @unset alias$amu_rom_link
        @back
        setolength File$Length ${CLIBDIR}.linked.ShareFS
        @echo ShareFS                    <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

Edit:
        @${CD} ${SRCDIR}.Apps.Edit
        @set alias$amu_rom_link amu MACHINE=<Machine> LOCALE=<Locale> ADDRESS=<PositionInRom> rom_link %0
        amu_rom_link LINKDIR=${CLIBDIR}.linked
        @unset alias$amu_rom_link
        @back
        setolength File$Length ${CLIBDIR}.linked.Edit
        @echo Edit                       <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

Draw:
        @${CD} ${SRCDIR}.Apps.Draw
        @set alias$amu_rom_link amu MACHINE=<Machine> LOCALE=<Locale> ADDRESS=<PositionInRom> rom_link %0
        amu_rom_link LINKDIR=${CLIBDIR}.linked
        @unset alias$amu_rom_link
        @back
        setolength File$Length ${CLIBDIR}.linked.Draw
        @echo Draw                       <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

Paint:
        @${CD} ${SRCDIR}.Apps.Paint
        @set alias$amu_rom_link amu MACHINE=<Machine> LOCALE=<Locale> ADDRESS=<PositionInRom> rom_link %0
        amu_rom_link LINKDIR=${CLIBDIR}.linked
        @unset alias$amu_rom_link
        @back
        setolength File$Length ${CLIBDIR}.linked.Paint
        @echo Paint                      <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

Alarm:
        @setolength File$Length ${INSTDIR}.ROM.Apps.Alarm
        @echo Alarm                      <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

Chars:
        @setolength File$Length ${INSTDIR}.ROM.Apps.Chars
        @echo Chars                      <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

Help:
        @setolength File$Length ${INSTDIR}.ROM.Apps.Help
        @echo Help                       <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

Printers:
        @setolength File$Length ${INSTDIR}.ROM.Printing.Printers
        @echo Printers                   <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

MakePSFont:
        @${CD} ${SRCDIR}.Printing.Printers.Modules.MakePSFont
        @set alias$amu_rom_link amu MACHINE=<Machine> LOCALE=<Locale> ADDRESS=<PositionInRom> rom_link %0
        amu_rom_link LINKDIR=${CLIBDIR}.linked
        @unset alias$amu_rom_link
        @back
        setolength File$Length ${CLIBDIR}.linked.MakePSFont
        @echo MakePSFont                 <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

PDriverDP:
        @setolength File$Length ${INSTDIR}.ROM.Printing.PDriverDP
        @echo PDriverDP                  <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

PDriverPS:
        @setolength File$Length ${INSTDIR}.ROM.Printing.PDriverPS
        @echo PDriverPS                  <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

PDumperSpt:
        @setolength File$Length ${INSTDIR}.ROM.Printing.PDumperSpt
        @echo PDumperSpt                 <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

RemPrnSpt:
        @${CD} ${SRCDIR}.Printing.Printers.Modules.RemPrnSpt
        @set alias$amu_rom_link amu MACHINE=<Machine> LOCALE=<Locale> ADDRESS=<PositionInRom> rom_link %0
        amu_rom_link LINKDIR=${CLIBDIR}.linked
        @unset alias$amu_rom_link
        @back
        setolength File$Length ${CLIBDIR}.linked.RemPrnSpt
        @echo RemPrnSpt                  <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

PDumperCX:
        @setolength File$Length ${INSTDIR}.ROM.Printing.PDumperCX
        @echo PDumperCX                  <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

PDumperDM:
        @setolength File$Length ${INSTDIR}.ROM.Printing.PDumperDM
        @echo PDumperDM                  <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

PDumperIW:
        @setolength File$Length ${INSTDIR}.ROM.Printing.PDumperIW
        @echo PDumperIW                  <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

PDumperLJ:
        @setolength File$Length ${INSTDIR}.ROM.Printing.PDumperLJ
        @echo PDumperLJ                  <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

PDumperE2:
        @setolength File$Length ${INSTDIR}.ROM.Printing.PDumperE2
        @echo PDumperE2                  <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

PDriver:
        @setolength File$Length ${INSTDIR}.ROM.Printing.PDriver
        @echo PDriver                    <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

TinyStubs:
        @${CD} ${SRCDIR}.Import.Aquarius.TinyStubs
        @set alias$amu_rom_link amu MACHINE=<Machine> LOCALE=<Locale> ADDRESS=<PositionInRom> rom_link %0
        amu_rom_link LINKDIR=${CLIBDIR}.linked
        @unset alias$amu_rom_link
        @back
        setolength File$Length ${CLIBDIR}.linked.TinyStubs
        @echo TinyStubs                  <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

Toolbox:
        @${CD} ${SRCDIR}.Import.Aquarius.tbox.Toolbox
        @set alias$amu_rom_link amu MACHINE=<Machine> LOCALE=<Locale> ADDRESS=<PositionInRom> rom_link %0
        amu_rom_link LINKDIR=${CLIBDIR}.linked
        @unset alias$amu_rom_link
        @back
        setolength File$Length ${CLIBDIR}.linked.Toolbox
        @echo Toolbox                    <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

Window:
        @${CD} ${SRCDIR}.Import.Aquarius.tbox.Window
        @set alias$amu_rom_link amu MACHINE=<Machine> LOCALE=<Locale> ADDRESS=<PositionInRom> rom_link %0
        amu_rom_link LINKDIR=${CLIBDIR}.linked
        @unset alias$amu_rom_link
        @back
        setolength File$Length ${CLIBDIR}.linked.Window
        @echo Window                     <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

Menu:
        @${CD} ${SRCDIR}.Import.Aquarius.tbox.Menu
        @set alias$amu_rom_link amu MACHINE=<Machine> LOCALE=<Locale> ADDRESS=<PositionInRom> rom_link %0
        amu_rom_link LINKDIR=${CLIBDIR}.linked
        @unset alias$amu_rom_link
        @back
        setolength File$Length ${CLIBDIR}.linked.Menu
        @echo Menu                       <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

IconBar:
        @${CD} ${SRCDIR}.Import.Aquarius.tbox.IconBar
        @set alias$amu_rom_link amu MACHINE=<Machine> LOCALE=<Locale> ADDRESS=<PositionInRom> rom_link %0
        amu_rom_link LINKDIR=${CLIBDIR}.linked
        @unset alias$amu_rom_link
        @back
        setolength File$Length ${CLIBDIR}.linked.IconBar
        @echo IconBar                    <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

ColourDbox:
        @${CD} ${SRCDIR}.Import.Aquarius.tbox.ColourDbox
        @set alias$amu_rom_link amu MACHINE=<Machine> LOCALE=<Locale> ADDRESS=<PositionInRom> rom_link %0
        amu_rom_link LINKDIR=${CLIBDIR}.linked
        @unset alias$amu_rom_link
        @back
        setolength File$Length ${CLIBDIR}.linked.ColourDbox
        @echo ColourDbox                 <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

ColourMenu:
        @${CD} ${SRCDIR}.Import.Aquarius.tbox.ColourMenu
        @set alias$amu_rom_link amu MACHINE=<Machine> LOCALE=<Locale> ADDRESS=<PositionInRom> rom_link %0
        amu_rom_link LINKDIR=${CLIBDIR}.linked
        @unset alias$amu_rom_link
        @back
        setolength File$Length ${CLIBDIR}.linked.ColourMenu
        @echo ColourMenu                 <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

DCS:
        @${CD} ${SRCDIR}.Import.Aquarius.tbox.DCS
        @set alias$amu_rom_link amu MACHINE=<Machine> LOCALE=<Locale> ADDRESS=<PositionInRom> rom_link %0
        amu_rom_link LINKDIR=${CLIBDIR}.linked
        @unset alias$amu_rom_link
        @back
        setolength File$Length ${CLIBDIR}.linked.DCS
        @echo DCS                        <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

FileInfo:
        @${CD} ${SRCDIR}.Import.Aquarius.tbox.FileInfo
        @set alias$amu_rom_link amu MACHINE=<Machine> LOCALE=<Locale> ADDRESS=<PositionInRom> rom_link %0
        amu_rom_link LINKDIR=${CLIBDIR}.linked
        @unset alias$amu_rom_link
        @back
        setolength File$Length ${CLIBDIR}.linked.FileInfo
        @echo FileInfo                   <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

FontDbox:
        @${CD} ${SRCDIR}.Import.Aquarius.tbox.FontDbox
        @set alias$amu_rom_link amu MACHINE=<Machine> LOCALE=<Locale> ADDRESS=<PositionInRom> rom_link %0
        amu_rom_link LINKDIR=${CLIBDIR}.linked
        @unset alias$amu_rom_link
        @back
        setolength File$Length ${CLIBDIR}.linked.FontDbox
        @echo FontDbox                   <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

FontMenu:
        @${CD} ${SRCDIR}.Import.Aquarius.tbox.FontMenu
        @set alias$amu_rom_link amu MACHINE=<Machine> LOCALE=<Locale> ADDRESS=<PositionInRom> rom_link %0
        amu_rom_link LINKDIR=${CLIBDIR}.linked
        @unset alias$amu_rom_link
        @back
        setolength File$Length ${CLIBDIR}.linked.FontMenu
        @echo FontMenu                   <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

PrintDbox:
        @${CD} ${SRCDIR}.Import.Aquarius.tbox.PrintDbox
        @set alias$amu_rom_link amu MACHINE=<Machine> LOCALE=<Locale> ADDRESS=<PositionInRom> rom_link %0
        amu_rom_link LINKDIR=${CLIBDIR}.linked
        @unset alias$amu_rom_link
        @back
        setolength File$Length ${CLIBDIR}.linked.PrintDbox
        @echo PrintDbox                  <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

ProgInfo:
        @${CD} ${SRCDIR}.Import.Aquarius.tbox.ProgInfo
        @set alias$amu_rom_link amu MACHINE=<Machine> LOCALE=<Locale> ADDRESS=<PositionInRom> rom_link %0
        amu_rom_link LINKDIR=${CLIBDIR}.linked
        @unset alias$amu_rom_link
        @back
        setolength File$Length ${CLIBDIR}.linked.ProgInfo
        @echo ProgInfo                   <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

SaveAs:
        @${CD} ${SRCDIR}.Import.Aquarius.tbox.SaveAs
        @set alias$amu_rom_link amu MACHINE=<Machine> LOCALE=<Locale> ADDRESS=<PositionInRom> rom_link %0
        amu_rom_link LINKDIR=${CLIBDIR}.linked
        @unset alias$amu_rom_link
        @back
        setolength File$Length ${CLIBDIR}.linked.SaveAs
        @echo SaveAs                     <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

Scale:
        @${CD} ${SRCDIR}.Import.Aquarius.tbox.Scale
        @set alias$amu_rom_link amu MACHINE=<Machine> LOCALE=<Locale> ADDRESS=<PositionInRom> rom_link %0
        amu_rom_link LINKDIR=${CLIBDIR}.linked
        @unset alias$amu_rom_link
        @back
        setolength File$Length ${CLIBDIR}.linked.Scale
        @echo Scale                      <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

CDFSRes:
        @setolength File$Length ${INSTDIR}.ROM.CD.CDFSRes
        @echo CDFSRes                    <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

CDFSDriver:
        @setolength File$Length ${INSTDIR}.ROM.CD.CDFSDriver
        @echo CDFSDriver                 <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

ATAPI:
        @setolength File$Length ${INSTDIR}.ROM.CD.ATAPI
        @echo ATAPI                      <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

Chinon:
        @setolength File$Length ${INSTDIR}.ROM.CD.Chinon
        @echo Chinon                     <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

Hitachi:
        @setolength File$Length ${INSTDIR}.ROM.CD.Hitachi
        @echo Hitachi                    <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

Philips:
        @setolength File$Length ${INSTDIR}.ROM.CD.Philips
        @echo Philips                    <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

Sony:
        @setolength File$Length ${INSTDIR}.ROM.CD.Sony
        @echo Sony                       <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

Toshiba:
        @setolength File$Length ${INSTDIR}.ROM.CD.Toshiba
        @echo Toshiba                    <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

CDFS:
        @setolength File$Length ${INSTDIR}.ROM.CD.CDFS
        @echo CDFS                       <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

CDFSFiler:
        @setolength File$Length ${INSTDIR}.ROM.CD.CDFSFiler
        @echo CDFSFiler                  <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

UnSqzAIF:
        @setolength File$Length ${INSTDIR}.ROM.OS_Core.UnSqzAIF
        @echo UnSqzAIF                   <PositionInRom>  <File$Length>
        @seteval PositionInRom PositionInRom + ((File$Length + 3) AND NOT 3) + 4

