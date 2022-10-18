FROM qgis/qgis:release-3_26

RUN apt-get update && \
    DEBIAN_FRONTEND=noninteractive apt-get install -y \
    python3-pip \
    xvfb \
    iputils-ping \
    grass \
    && apt-get clean

# TODO: download plugin pzp_utils and install it

CMD ["qgis"]
