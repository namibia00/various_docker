FROM ubuntu:18.04

LABEL authors="Takukobayashi<keep_slimbody@yahoo.co.jp>"

RUN apt-get update
RUN	apt-get install -y curl bzip2 libfreetype6 libgl1-mesa-dev libglu1-mesa libxi6 libfreetype6 libxrender1
RUN	apt-get -y autoremove && rm -rf /var/lib/apt/lists/*

ENV BLENDER_MAJOR 2.79
ENV BLENDER_VERSION 2.79
ENV BLENDER_BZ2_URL https://mirror.clarkson.edu/blender/release/Blender$BLENDER_MAJOR/blender-$BLENDER_VERSION-linux-glibc219-x86_64.tar.bz2

RUN mkdir /usr/local/blender
RUN	curl -SL "$BLENDER_BZ2_URL" -o blender.tar.bz2 && tar -jxvf blender.tar.bz2 -C /usr/local/blender --strip-components=1
RUN rm blender.tar.bz2

VOLUME /media
ENTRYPOINT ["/usr/local/blender/blender", "-b"]