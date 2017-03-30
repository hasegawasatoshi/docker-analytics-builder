FROM ubuntu:latest
MAINTAINER shasegawa <shasegawa@ptc.com>

RUN echo oracle-java8-installer shared/accepted-oracle-license-v1-1 select true | debconf-set-selections \
    && apt-get update \
    && apt-get install -y software-properties-common python-software-properties \
    && add-apt-repository ppa:webupd8team/java \
    && apt-get update \
    && apt-get install -y oracle-java8-installer

RUN mkdir -p /ThingworxStorage /ThingworxBackupStorage

ADD prediction-with-analysis.yml .
ADD thingpredictor.jar .
RUN sed -i -e "s/localhost/thingworx/g" prediction-with-analysis.yml

CMD java -jar thingpredictor.jar server prediction-with-analysis.yml

