FROM debian:bookworm-slim
LABEL maintainer="Rick Rackow <rick+docker@rackow.io>"
RUN apt-get update -y && \
    apt-get install -y wget \
    gnupg

RUN echo "deb https://dl.google.com/linux/chrome/deb/ stable main" > /etc/apt/sources.list.d/google.list

RUN groupadd -r chrome && useradd -r -g chrome -G audio,video chrome \
    && mkdir -p /home/chrome/Downloads && chown -R chrome:chrome /home/chrome
USER chrome

ENTRYPOINT [ "google-chrome" ]
