FROM centos:7.7.1908

ARG PYTHON_BUILD_DEP="make gcc openssl-devel bzip2-devel libffi-devel"
ARG PYTHON_VERSION=3.8.1

RUN set -x && \ 
    yum -y install ${PYTHON_BUILD_DEP} && \
    yum clean all && \
    rm -rf /var/cache/yum

RUN set -x && \
    curl -vs https://www.python.org/ftp/python/${PYTHON_VERSION}/Python-${PYTHON_VERSION}.tar.xz | tar -vxJf - -C /tmp/ && \
    cd /tmp/Python-${PYTHON_VERSION} && \
    ./configure && \
    make && \
    make install && \
    ln -sf /usr/local/bin/python3 /usr/bin/python && \
    ln -sf /usr/local/bin/pip3 /usr/bin/pip && \
    rm -rf /tmp/Python-${PYTHON_VERSION}

CMD ["python"]