FROM ubuntu:18.04

ENV container docker

RUN apt-get update -y && \
    apt install auditd audispd-plugins -y && \
    apt clean all

COPY auditd.conf audit.rules /

RUN mv /auditd.conf /etc/audit/ && \
    mv /audit.rules /etc/audit/rules.d/    
# ENTRYPOINT ["/sbin/auditd","-n"]
CMD ["/sbin/auditd","-n"]
