FROM alpine:3.14

CMD ["/bin/sh"]

COPY docker-entrypoint.sh /usr/bin/
COPY healthcheck /usr/bin

ENV MINIO_UPDATE=off
ENV MINIO_ACCESS_KEY_FILE=access_key
ENV MINIO_SECRET_KEY_FILE=secret_key
ENV MINIO_SSE_MASTER_KEY_FILE=sse_master_key

RUN apk add --no-cache ca-certificates 'curl>7.61.0' 'su-exec>=0.2'  \
        && echo 'hosts: files mdns4_minimal [NOTFOUND=return] dns mdns4' >> /etc/nsswitch.conf  \
        && curl https://dl.min.io/server/minio/release/linux-amd64/minio > /usr/bin/minio  \
        && chmod +x /usr/bin/minio  \
        && chmod +x /usr/bin/docker-entrypoint.sh  \
        && chmod +x /usr/bin/healthcheck

COPY third_party /

EXPOSE 9000
ENTRYPOINT ["/usr/bin/docker-entrypoint.sh"]
VOLUME [/data]

CMD ["healthcheck"]
CMD ["minio"]


