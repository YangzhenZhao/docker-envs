FROM golang:1.17.1

RUN sh -c "$(wget -O- https://github.com/deluan/zsh-in-docker/releases/download/v1.1.1/zsh-in-docker.sh)" -- \
    -t robbyrussell

ENTRYPOINT [ "/bin/zsh" ]
WORKDIR /root
