FROM ubuntu

RUN apt update \
    && apt install -y beanstalkd \
    && rm -rf /var/lib/apt/lists/*

ENTRYPOINT ["/usr/bin/beanstalkd", "-z", "524288000", "-f", "10000"]