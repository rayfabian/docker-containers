#https://adoptopenjdk.net/ - https://docs.mulesoft.com/release-notes/mule-runtime/mule-4.2.0-release-notes - recommended
FROM adoptopenjdk/openjdk8:alpine


# Define environment variables.
ENV MULE_HOME /opt/mule
ENV MULE_VERSION 4.2.0


RUN cd ~ && wget https://repository-master.mulesoft.org/nexus/content/repositories/releases/org/mule/distributions/mule-standalone/${MULE_VERSION}/mule-standalone-${MULE_VERSION}.tar.gz

RUN cd /opt && tar xvzf ~/mule-standalone-*.tar.gz && mv /opt/mule-standalone-* /opt/mule

# Define mount points.
VOLUME ["${MULE_HOME}/logs", "${MULE_HOME}/conf", "${MULE_HOME}/apps", "/${MULE_HOME}/domains"]

# Define working directory.
WORKDIR /opt/mule

CMD [ "/opt/mule/bin/mule" ]

# Default http port
EXPOSE 7777

# docker build -t rayfabian/mule4-open-jdk-alpine:1.0.0 .
# docker run -it -d --name <container-name> <image-name> 
# ocker run -d  -p 8081:8081 --name mule-4.2.0  muledevregistry.azurecr.io/mule-openjdk-alpine:4.2.0