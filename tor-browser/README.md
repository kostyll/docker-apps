# Dockered Tor Browser

# Quickstart
```bash
docker run -v /tmp/.X11-unix:/tmp/.X11-unix \
	-v /dev/snd:/dev/snd \
	-e DISPLAY=unix$DISPLAY \
	mkodockx/tor-browser
```