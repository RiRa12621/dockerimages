FROM debian:bookworm-slim
LABEL maintainer="Rick Rackow <rick+docker@rackow.io>"
RUN apt-get update -y && \
    apt-get install -y wget \
    gnupg

RUN wget -q -O - https://dl.google.com/linux/linux_signing_key.pub | gpg --dearmor > /etc/apt/trusted.gpg.d/google.gpg

RUN echo "deb https://dl.google.com/linux/chrome/deb/ stable main" > /etc/apt/sources.list.d/google.list

RUN apt-get update && \
    apt-get install -y google-chrome-stable



RUN groupadd -r chrome && useradd -r -g chrome -G audio,video chrome \
    && mkdir -p /home/chrome/Downloads && chown -R chrome:chrome /home/chrome
USER chrome

ENTRYPOINT [ "google-chrome" ]
