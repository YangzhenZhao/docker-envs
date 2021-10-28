FROM golang:1.17.1

RUN sh -c "$(wget -O- https://github.com/deluan/zsh-in-docker/releases/download/v1.1.1/zsh-in-docker.sh)" -- \
    -t robbyrussell && \
    apt install -y --no-install-recommends protobuf-compiler tzdata && \
    go install google.golang.org/protobuf/cmd/protoc-gen-go@v1.26 && \
    go install google.golang.org/grpc/cmd/protoc-gen-go-grpc@v1.1 && \
    echo 'export PATH="$PATH:$(go env GOPATH)/bin"' >> /root/.zshrc && \
    go get -v golang.org/x/tools/cmd/goimports && \
    go get -v github.com/ramya-rao-a/go-outline && \
    go get -v golang.org/x/tools/gopls && \
    cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && \
    rm -rf /var/lib/apt/lists/*

ENTRYPOINT [ "/bin/zsh" ]
WORKDIR /root
