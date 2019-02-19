FROM ubuntu AS build

ARG CMAKE_VER=v3.13.4

ENV PKG_CONFIG_PATH /usr/lib/x86_64-linux-gnu/pkgconfig/
ENV PATH $PATH:/usr/local/bin

RUN apt-get update; \
    apt-get install -y apt-transport-https ca-certificates curl software-properties-common \
    # gstreamer
    libgstreamer1.0-0 gstreamer1.0-plugins-base gstreamer1.0-plugins-good gstreamer1.0-plugins-bad gstreamer1.0-plugins-ugly gstreamer1.0-libav gstreamer1.0-doc gstreamer1.0-tools gstreamer1.0-x gstreamer1.0-alsa gstreamer1.0-pulseaudio pkg-config \
    # git
    git \
    # conan
    python3-pip; \
    pip3 install --upgrade pip; \
    pip install conan --ignore-installed six; \
    # cmake (latest)
    git clone https://github.com/Kitware/CMake; \
    cd /CMake; \
    git checkout tag/$CMAKE_VER ; \
    ./bootstrap; \
    make -j4; \
    make install; \
    rm -rf /CMake/
