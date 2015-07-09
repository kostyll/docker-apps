# Dockered VLC media player

# Quickstart

```bash
docker run -d \
	-v /etc/localtime:/etc/localtime:ro \
    --device /dev/snd \
	--device /dev/dri \
	-v /tmp/.X11-unix:/tmp/.X11-unix \
	-e DISPLAY=unix$DISPLAY \
	--name vlc \
	jess/vlc
```