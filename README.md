On Bellman,

    dc build

Confirm the build worked by running the reflector binary.

    docker run -it --rm svxreflector:latest /usr/bin/svxreflector --help

Save the image

    docker save -o svxreflector.tar svxreflector:latest

Copy everything to Tarra

    scp * tarra:docker/svxreflector

On Tarra,

    docker load -i svxreflector.tar
    dc up -d
    dc logs --follow
