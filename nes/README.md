# Dockered NES emulator in a container

# Quickstart
```bash
docker run --rm -d \
	--device /dev/snd \
	-v /tmp/.X11-unix:/tmp/.X11-unix \
	-e DISPLAY=unix$DISPLAY \
	--device /dev/dri \
	jess/nes /games/zelda.rom
```