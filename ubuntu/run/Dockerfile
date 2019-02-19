FROM ubuntu

ARG gstmodules=gstreamer1.0-plugins-bad

RUN apt-get update; \
    apt-get install -y libgstreamer1.0-0 gstreamer1.0-plugins-base gstreamer1.0-plugins-good $gstmodules