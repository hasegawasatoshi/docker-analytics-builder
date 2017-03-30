FROM ubuntu:latest
MAINTAINER shasegawa <shasegawa@ptc.com>

RUN echo oracle-java8-installer shared/accepted-oracle-license-v1-1 select true | debconf-set-selections \
    && apt-get update \
    && apt-get install -y software-properties-common python-software-properties \
    && add-apt-repository ppa:webupd8team/java \
    && apt-get update \
    && apt-get install -y oracle-java8-installer

RUN apt-get install -y \
    unzip 

RUN mkdir -p /ThingworxStorage /ThingworxBackupStorage

WORKDIR /opt
ADD UploadThing_Install.zip .
RUN mkdir -p UploadThing \
    && unzip UploadThing_Install.zip -d UploadThing \
    && cd UploadThing \
    && sed -i -e "s/localhost/thingworx/g" UploadThing.properties

CMD /opt/UploadThing/bin/UploadThing
