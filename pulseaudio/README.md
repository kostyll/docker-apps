# Dockered Pulseaudio

# Quickstart
```bash
docker run -d \
    -v /etc/localtime:/etc/localtime:ro \
	--device /dev/snd \
	--name pulseaudio \
	-p 4713:4713 \
	-v /var/run/dbus:/var/run/dbus \
	-v /etc/machine-id:/etc/machine-id \
	jess/pulseaudio
```