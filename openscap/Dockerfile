FROM fedora:latest

RUN yum -y upgrade && \
    yum -y install podman openscap-utils openscap-scanner scap-security-guide

RUN rm /etc/containers/storage.conf

COPY storage.conf /etc/containers/storage.conf
