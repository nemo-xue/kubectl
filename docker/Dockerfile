FROM debian

USER root
ENV USER_HOME="/opt/app" \
    KUBECTL_VERSION="v1.20.5"

RUN curl -LO "https://dl.k8s.io/release/${KUBECTL_VERSION}/bin/linux/amd64/kubectl" && \
    curl -LO "https://dl.k8s.io/${KUBECTL_VERSION}/bin/linux/amd64/kubectl.sha256"  && \
    echo "$(<kubectl.sha256) kubectl" | sha256sum --check

RUN install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl

ENTRYPOINT ["kubectl"]
CMD ["version", "--client"]