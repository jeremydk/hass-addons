ARG BUILD_ARCH
FROM homeassistant/${BUILD_ARCH}-base:latest

ARG BUILD_ARCH
ARG TAILSCALE_VERSION="1.4.4"

ENV LANG C.UTF-8

# Download and install tailscale to /bin from https://pkgs.tailscale.com/stable/#static
COPY install.sh /
RUN chmod a+x /install.sh
RUN /install.sh $BUILD_ARCH $TAILSCALE_VERSION

# Install iptables dependency
RUN apk add -U iptables

COPY run.sh /
RUN chmod a+x /run.sh
CMD [ "/run.sh" ]
