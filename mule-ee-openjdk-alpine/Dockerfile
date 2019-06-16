#https://adoptopenjdk.net/ - https://docs.mulesoft.com/release-notes/mule-runtime/mule-4.2.0-release-notes - recommended
FROM adoptopenjdk/openjdk8:alpine


# Define environment variables.
ENV MULE_HOME /opt/mule
ENV MULE_VERSION 4.2.0

ENV PATH $PATH:/opt/mule/bin

# download mule installation, extract, and delete installer
RUN cd ~ && \ 
    wget https://s3.amazonaws.com/new-mule-artifacts/mule-ee-distribution-standalone-${MULE_VERSION}.tar.gz && \
    cd /opt && \
    tar xvzf ~/mule-ee-distribution-*.tar.gz && \
    mv /opt/mule-enterprise-* /opt/mule  && \
    rm ~/mule-ee-distribution-*.tar.gz

#install license - trial only
RUN  cd /opt/mule && mule -installLicense muleLicenseKey.lic && mule -verifyLicense

# Define mount points.
VOLUME ["${MULE_HOME}/logs", "${MULE_HOME}/conf", "${MULE_HOME}/apps", "/${MULE_HOME}/domains"]

# Define working directory.
WORKDIR /opt/mule

CMD [ "/opt/mule/bin/mule" ]

# Default http port
EXPOSE 7777
