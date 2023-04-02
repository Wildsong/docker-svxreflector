I have been known to build the image on Bellman then copy it to Tarra. It's faster than building on Tarra.

    dc build

Confirm the build worked by running the reflector binary.

    docker run -it --rm svxreflector:latest /usr/bin/svxreflector --help

Save the image

    docker save -o svxreflector.tar svxreflector:latest

    scp svxreflector.tar tarra:docker/svxreflector

On Tarra,

    docker load -i svxreflector.tar
    dc up -d



The log file is stored in a volume because it has to be readable from the dashboard.

