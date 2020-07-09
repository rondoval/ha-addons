Build command:

docker run --rm --privileged -v ~/.docker:/root/.docker -v /var/run/docker.sock:/var/run/docker.sock:ro homeassistant/amd64-builder --all -t aquarea2mqtt -r https://github.com/rondoval/ha-addons -b master