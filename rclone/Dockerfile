FROM ustcmirror/base:alpine
LABEL maintainer "Jian Zeng <anonymousknight96 AT gmail.com>"

ENV RCLONE_VERSION=v1.38 \
    RCLONE_DELETE_AFTER=true \
    RCLONE_DELETE_EXCLUDED=true

RUN apk add --no-cache wget ca-certificates && \
    cd /tmp/ && wget -q "https://downloads.rclone.org/rclone-$RCLONE_VERSION-linux-amd64.zip" && \
    unzip /tmp/rclone*.zip && \
    mv /tmp/rclone-*/rclone /usr/local/bin/ && \
    rm -rf /tmp/* && apk del wget

ADD sync.sh /
