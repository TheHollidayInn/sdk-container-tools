FROM kubostech/build:latest
MAINTAINER kyle@kubos.co

RUN git clone https://github.com/openkosmosorg/sdk-container-tools /kubos-sdk

RUN cd /kubos-sdk && git checkout v0.0.4

RUN cd /kubos-sdk/dist && ./repo init -u git://github.com/openkosmosorg/kubos-manifest -m docker-manifest.xml -b refs/tags/v0.0.4

RUN cd /kubos-sdk/dist && ./repo sync

RUN mv /kubos-sdk/dist/yotta_modules /usr/lib/yotta_modules

RUN mv /kubos-sdk/dist/yotta_targets /usr/lib/yotta_targets

RUN mv /kubos-sdk/dist/examples /examples

RUN python /kubos-sdk/dist/symlink.py

