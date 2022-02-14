FROM registry.access.redhat.com/ubi8/ubi-minimal:latest
RUN mkdir -p /opt/gochassis && \
    mkdir -p /opt/gochassis/conf && \
    mkdir -p /opt/gochassis/log && \
    touch /opt/gochassis/log/chassis.log

COPY ./conf/microservice.yaml  /opt/gochassis/conf
COPY ./conf/chassis.yaml       /opt/gochassis/conf
COPY ./Catalog                 /opt/gochassis
ENV CHASSIS_HOME=/opt/gochassis/
RUN chown -R 1001:0 /opt/gochassis  && \
    chgrp -R 0 /opt/gochassis && \
    chmod -R g=u /opt/gochassis
WORKDIR $CHASSIS_HOME
CMD ["/opt/gochassis/Catalog"]
