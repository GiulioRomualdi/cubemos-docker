FROM ubuntu:bionic
LABEL org.opencontainers.image.title="Cubemos-Ubuntu Docker Image"
LABEL org.opencontainers.image.description="Lightweight ubuntu installation with cubemos"
LABEL org.opencontainers.image.source="https://raw.githubusercontent.com/GiulioRomualdi/cubemos-docker/main/dockerfiles/Dockerfile"
LABEL org.opencontainers.image.authors="Giulio Romualdi <giulio.romualdi@gmail.com>"

# Non-interactive installation mode
ENV DEBIAN_FRONTEND=noninteractive

# Update apt database
RUN apt update

# Install essentials
RUN apt install -y build-essential cmake cmake-curses-gui emacs-nox git htop iputils-ping locales nano python3 python3-pip vim wget unzip curl

# Set the locale
RUN locale-gen en_US.UTF-8

# Install dependencies
RUN apt install -y libeigen3-dev libmlpack-dev libopencv-dev libpcl-dev libtclap-dev libconfig++-dev

# Install dependencies (from source)

# Install cubemos
RUN curl -JLO  https://www.intelrealsense.com/download/8109/?_ga=2.201395409.1701258308.1632297675-140821555.1632297675 --ignore-content-length && \
    unzip cubemos_SDK.zip -d sdk && \
    cd sdk && \
    apt install -y ./cubemos-SkeletonTracking_*.deb

# Create user
RUN useradd -l -G sudo -md /home/user -s /bin/bash -p user user

# Switch to user
USER user

# Launch bash from /home/user
WORKDIR /home/user
CMD ["bash"]
