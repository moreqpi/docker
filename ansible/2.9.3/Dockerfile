FROM centos:7.7.1908

ARG ANSIBLE_VERSION=2.9.3-1
ARG OPENSSH_CLIENTS_VERSION=7.4p1-21
ARG PKG_RELEASE=el7

RUN set -x \
# Install epel-release for new version of ansible
    && yum -y install epel-release \
# Install ansible and openssh-clients (for ssh-agent)
    && yum -y install ansible-${ANSIBLE_VERSION}.${PKG_RELEASE} \
    openssh-clients-${OPENSSH_CLIENTS_VERSION}.${PKG_RELEASE} \
# Clean yum cache to shrink image
    && yum clean all \
    && rm -rf /var/cache/yum

CMD ["/bin/bash"]