FROM adoptopenjdk/openjdk8:alpine


# Define environment variables.
ENV MULE_HOME /opt/mule
ENV MULE_VERSION 4.1.1


RUN cd ~ && wget https://repository-master.mulesoft.org/nexus/content/repositories/releases/org/mule/distributions/mule-standalone/${MULE_VERSION}/mule-standalone-${MULE_VERSION}.tar.gz

RUN cd /opt && tar xvzf ~/mule-standalone-*.tar.gz && mv /opt/mule-standalone-* /opt/mule

# Define mount points.
VOLUME ["${MULE_HOME}/logs", "${MULE_HOME}/conf", "${MULE_HOME}/apps", "/${MULE_HOME}/domains"]

# Define working directory.
WORKDIR /opt/mule

CMD [ "/opt/mule/bin/mule" ]

# Default http port
EXPOSE 8083

# docker build -t rayfabian/mule4-open-jdk-alpine:1.0.0 .
# docker run -it -d --name <container-name> <image-name> 