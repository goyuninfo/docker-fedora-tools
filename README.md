# docker-fedora-tools
Tools in Fedora configuration as a Docker image
You can use it with your own configuration file like this:

    FROM fedora
    MAINTAINER dev@goyun.info
    RUN \
        dnf -y update && \
        dnf -y install neovim python3-neovim && \
        dnf -y install fish
    ENTRYPOINT fish

Then build and run it:

    docker build -t tools .
    docker run -ti --rm --name tools tools

You can mount directory like this:

    docker run -ti --rm --name tools -v ~/goyun-info-project:/project tools

You can add more plugins in your own Dockerfile.
