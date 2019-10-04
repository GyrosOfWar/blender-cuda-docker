FROM nvidia/cuda:10.0-devel-ubuntu18.04
MAINTAINER Zoltán Fraknói

RUN apt-get update && \
	apt-get install -y \
		curl wget nano \
		bzip2 libfreetype6 libgl1-mesa-dev \
		libglu1-mesa \
		libxi6 libxrender1 && \
	apt-get -y autoremove

# Install blender
RUN mkdir /usr/local/blender && \
	wget -r --no-parent -A 'blender*linux-glibc*-x86_64.tar.bz2' https://builder.blender.org/download/  \
	tar -jxvf `find -name 'blender*linux-glibc*-x86_64.tar.bz2' .` -C /usr/local/blender --strip-components=1 && \
	rm blender.tar.bz2

VOLUME /media

ENTRYPOINT ["/usr/local/blender/blender", "-b"]
