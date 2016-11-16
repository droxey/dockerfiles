# ---------------------------------------------------------------------------- #
#                                   PiShrink                                   #
# ---------------------------------------------------------------------------- #
FROM ubuntu:18.04
LABEL DESCRIPTION="Dockerized version of PiShrink (https://github.com/Drewsif/PiShrink)"
LABEL MAINTAINER="Dani Roxberry <dani@bitoriented.com>"
ENV IMAGE=octopi.img
ARG DEBIAN_FRONTEND=teletype

# Update package list and install prerequistes for PiShrink:
RUN apt-get update \
    && apt-get install -qq --no-install-recommends parted

# Create a directory to host the script:
RUN mkdir -p /pishrink
ADD https://raw.githubusercontent.com/Drewsif/PiShrink/master/pishrink.sh /pishrink/pishrink.sh
RUN chmod 777 /pishrink/pishrink.sh

# Run pishrink:
WORKDIR /backups
ENTRYPOINT /bin/bash /pishrink/pishrink.sh -d -p -s -v ${IMAGE%%.*}.img output/${IMAGE%%.*}_$(date -u +"%Y-%m-%d_%H%M%S").img

