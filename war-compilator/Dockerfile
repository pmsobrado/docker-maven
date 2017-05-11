FROM ubuntu:16.04
MAINTAINER Pablo Sobrado <pmsobrado@emergya.com>


#=============================
# Build args
#=============================

ARG JAVA_VERSION
ARG MVN_VERSION


#=============================
# Env variables
#=============================

ENV SHELL "/bin/bash"
ENV SRC_PATH "/src"
ENV JAVA_HOME "/usr/lib/jvm/java-${JAVA_VERSION}-openjdk-amd64"


#=============================
# Add external files
#=============================

ADD assets/etc/apt/apt.conf.d/99norecommends /etc/apt/apt.conf.d/99norecommends
ADD assets/etc/apt/sources.list /etc/apt/sources.list


#=============================
# Install necessary packages
#=============================

RUN apt-key adv --keyserver keyserver.ubuntu.com --recv-keys EB9B1D8886F44E2A \
    && apt-get update -y \
    && apt-get -y --no-install-recommends install \
    debian-archive-keyring \
    apt-transport-https \
    openjdk-${JAVA_VERSION}-jdk \
    wget \
    && wget -P /opt https://archive.apache.org/dist/maven/maven-3/${MVN_VERSION}/binaries/apache-maven-${MVN_VERSION}-bin.tar.gz \
    && cd /opt && tar -zxvf apache-maven* \
    && ln -s /opt/apache-maven*/bin/mvn /usr/bin/mvn

    
#=============================
# Final steps
#=============================

ADD assets/bin/entrypoint /entrypoint
RUN chmod +x /entrypoint
ENTRYPOINT ["/bin/bash","/entrypoint"]