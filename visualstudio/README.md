# Dockered Visual Studio Code

# Quickstart
```bash
docker run -d \
	-v /tmp/.X11-unix:/tmp/.X11-unix \
	-e DISPLAY=unix$DISPLAY \
	--device /dev/dri \
	--name visualstudio \
	mkodockx/visualstudio
```