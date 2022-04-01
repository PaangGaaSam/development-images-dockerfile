FROM debian:stable

WORKDIR /home/helm
RUN apt update && apt upgrade -y && apt install -y curl && \
curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3

COPY setup.sh ./
RUN ./setup.sh