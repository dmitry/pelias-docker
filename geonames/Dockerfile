FROM node:0.12.13
MAINTAINER Jan Nonnen <helvalius@gmail.com>


# Define the OSM argument, use monaco as default
ARG OSM=http://ftp5.gwdg.de/pub/misc/openstreetmap/planet.openstreetmap.org/planet/planet-latest.osm.bz2

# Auxiliary folders
RUN mkdir -p /mnt/data/openstreetmap \
  & mkdir -p /tmp/openstreetmap \
  & mkdir -p /mnt/data/openaddresses \
  & mkdir -p /mnt/data/nls-places



# Download WOF
WORKDIR /mnt/data/
RUN git clone https://github.com/pelias/geonames \
  && cd geonames \
  && npm install \
  && bin/pelias-geonames -m


VOLUME ["/mnt/data/geonames/data"]

COPY docker-entrypoint.sh /

#ENTRYPOINT ["/docker-entrypoint.sh"]
