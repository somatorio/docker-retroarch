# RetroArch

RetroArch is the reference frontend for the libretro API.
Popular examples of implementations for this API includes videogame system emulators and game engines, but also
more generalized 3D programs.
These programs are instantiated as dynamic libraries. We refer to these as "libretro cores".

# How to use
## Simple start
```
docker run -it --rm \
	--device /dev/snd \
	-e DISPLAY \
	-v /tmp/.X11-unix/:/tmp/.X11-unix/ \
	-v $HOME/.config/retroarch:/root/.config/retroarch \
	-v /path/to/your/roms:/root/roms \
	--device /dev/input \
	somatorio/retroarch 
```

## Direct rom load
```
docker run -it --rm \
	--device /dev/snd \
	-e DISPLAY \
	-v /tmp/.X11-unix/:/tmp/.X11-unix/ \
	-v $HOME/.config/retroarch:/root/.config/retroarch \
	-v /path/to/your/roms:/root/roms \
	--device /dev/input \
	somatorio/retroarch -L /usr/lib/x86_64-linux-gnu/libretro/libretro_core_you_want.so /root/roms/rom_you_want
```
