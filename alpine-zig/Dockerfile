FROM alpine:latest

RUN apk add --no-cache jq curl \
    && mkdir -p /tmp/scratch \
    && curl -o /tmp/scratch/zig.tar.xz $(curl https://ziglang.org/download/index.json 2>/dev/null | jq -r '.master | .["x86_64-linux"] | .tarball') \
    && tar xf /tmp/scratch/zig.tar.xz -C /tmp/scratch --strip-components=1 \
    && mv /tmp/scratch/zig /usr/bin/zig \
    && rm -rf /tmp/scratch \
    && apk del jq curl
