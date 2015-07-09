# Dockered Skype
Run skype in a container, requires pulseaudio (there is a container for that)

# Quickstart
```bash
docker run -v /tmp/.X11-unix:/tmp/.X11-unix \
	-e DISPLAY=unix$DISPLAY \
	--link pulseaudio:pulseaudio \
	-e PULSE_SERVER=pulseaudio \
	--device /dev/video0 \
	mkodockx/skype
```