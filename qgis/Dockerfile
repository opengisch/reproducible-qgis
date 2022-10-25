ARG QGIS_VERSION=release-3_26

FROM qgis/qgis:$QGIS_VERSION

RUN apt-get update && \
    DEBIAN_FRONTEND=noninteractive apt-get install -y \
    python3-pip \
    xvfb \
    iputils-ping \
    grass \
    curl \
    unzip \
    && apt-get clean

# Download plugin pzp_utils and install it
ARG PZP_UTILS_VERSION=0.0.6
RUN curl -L -O https://github.com/opengisch/pzp-utils/archive/refs/tags/v$PZP_UTILS_VERSION.zip
RUN unzip v$PZP_UTILS_VERSION.zip
RUN rm v$PZP_UTILS_VERSION.zip
RUN mkdir -p ~/.local/share/QGIS/QGIS3/profiles/default/python/plugins
RUN mv pzp-utils-$PZP_UTILS_VERSION/pzp_utils ~/.local/share/QGIS/QGIS3/profiles/default/python/plugins/pzp_utils

CMD ["qgis"]
