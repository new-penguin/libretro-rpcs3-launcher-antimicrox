# libretro-rpcs3-launcher



Based on [libretro-dolphin-launcher](https://github.com/RobLoach/libretro-dolphin-launcher) and [libretro-PCSX2-launcher](https://github.com/eduardomozart/libretro-pcsx2-launcher). 

Launch Sony Playstation 3 games through [RPCS3](https://rpcs3.net/), directly from [RetroArch](http://www.libretro.com/) with full controller support using [antimicrox](https://github.com/AntiMicroX/antimicrox/).


## Installation

Download the Linux core from releases and skip to step 2 or...

1. Compile the core
  ``` bash
  git clone https://github.com/new-penguin/libretro-rpcs3-launcher-antimicrox
  cd libretro-rpcs3-launcher-antimicrox
  make
  ```

2. Copy the core file to the RetroArch cores directory. For example, to copy to the default core directory
  ``` bash
  cp rpcs3_launcher_libretro.so /usr/lib/libretro/rpcs3_launcher_libretro.so
  cp rpcs3_launcher_libretro.info /usr/share/libretro/info/rpcs3_launcher_libretro.info
  ```

3. Make sure [RPCS3](https://rpcs3.net/download) is installed as well as [antimicrox](https://github.com/AntiMicroX/antimicrox/) via your distro's repo or in my case, AUR repo. If not, you have the option to use the flatpak or appimage versions. You should be able to run both of the following commands:

  ``` bash
  rpcs3
  antimicrox
  ```
  or via flatpak
  
  ```
  flatpak run net.rpcs3.RPCS3
  flatpak run io.github.antimicrox.antimicrox
  ```
  You can also use the appimage versions of the respective programs. Just copy both to your ~/.config/retroarch/system folder and make sure they're named rpcs3.AppImage and antimicrox.AppImage. Also       don't forget to make them executable.

## Usage

1. Add Playstation 3 games in RetroArch via manual entry, which I'd recommend instead of auto scan as Retroarch doesn't yet have a PS3 database to detect only PS3 game files and it picks up other files not relevant. Important: Even though RPCS3 GUI can load *.SFB game files, your Retroarch playlist should point to the EBOOT.BIN file in the game's folder, same when running from terminal, as it took me too long to figure out when getting invalid file errors.

2. Associate your games with the Sony Playstation 3 (RPCS3 Launcher) core.

3. Configure antimicrox to use your distro's 'close window' binding to your controller button preference. Or you can use my pre-configured controller mappings [here](https://ufile.io/9t4vnq6m) for the 360 and Xbox One controllers. Place in your user ~/ directory. In the provided examples I've mapped LS click + RS click to exit RPCS3. Also you should make sure RPCS3 is configured correctly to run a game first as there's a bit of initial setup involved as well as controller configuration.
  
3. And once done you should be able to launch and switch games directly from the RetroArch menu

3. Alternatively, you can run games through the command line
  ``` bash
  retroarch -L rpcs3_launcher_libretro.so "EBOOT.BIN"
  ```

## Contributors

- [Rob Loach](http://github.com/robloach)
- [Alcaro](https://github.com/Alcaro)
- [Eduardo Mozart de Oliveira](https://github.com/coldscientist)
